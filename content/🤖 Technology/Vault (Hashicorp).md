2023-02-15
 #technology #security 

HashiCorp Vault is **a secrets management tool specifically designed to control access to sensitive credentials in a low-trust environment**.

Secrets are defined as any form of sensitive credentials that need to be tightly controlled and monitored and can be used to unlock sensitive information. Secrets could be in the form of passwords, API keys, SSH keys, RSA tokens, or OTP.

When the Vault is initialized it generates an encryption key which is used to protect all the data. That key is protected by a master key. By default, Vault uses a technique known as [[Shamirs's secret sharing]] algorithm to split the master key into 5 shares, any 3 of which are required to reconstruct the master key.

![[Pasted image 20230215200349.png]]

Vault’s encryption layer, referred to as the _barrier_, is responsible for encrypting and decrypting Vault data.

When the Vault server starts, it writes data to its storage backend. Since **the storage backend resides outside the barrier, it’s considered untrusted** so Vault will encrypt the data before it sends them to the storage backend. 

When a Vault server is started, it begins in a _sealed_ state. Before any operation can be performed on Vault, it must be _unsealed_. This is done by providing the **unseal keys**. During the Vault initialization, it generates an encryption key, which is used to protect all Vault data. This key is protected by a root key that is stored alongside all other Vault data, but is encrypted by another mechanism: the unseal key.

Key to encrypt all vault data
	This key is protected by the root key that is stored as Vault data
		This key is encrypted by the unseal key
			The unseal key is split into shards

[[Shamirs's secret sharing]] is used to split the unseal key into a configured number of shards (key shares or unseal keys). A precise number of shards is needed to reconstruct the unseal key, which then decrypts the Vault root key, and that the Vault data.

The unseal process is done by running `vault operator unseal` or via the API. This process is stateful: each key can be entered via multiple mechanisms from multiple client machines and it will work. This allows each shares of the root key to be on a distinct client machine for better security.

Once a Vault node is unsealed, it remains unsealed until one of these things happens:
1.  It is resealed via the API (see below).
2.  The server is restarted.
3.  Vault's storage layer encounters an unrecoverable error.

---
# References
