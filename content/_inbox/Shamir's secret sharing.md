2023-02-15
#algorithm #security 

**(SSS)**


- Used to secure a secret in a distributed form
- Split into multiple shares which individually do not give any information about the secret
- A *threshold* of shrares is needed to reconstruct the secret
- No information about the secret can be gained with a number of shares below the threshold

```
S = 1954
n = 4
k = 3

# Choose k - 1 positive integers, place in a set with the secret
a = [S, 43, 12]

# Define the method y = 1954 + 43 * x + 12 * x^2
y(x) = {
	a[0] + (a[1] * x) + (a[2] * x^2)
}

# Create n secrets
share 1 = y(1) = 2009
share 2 = y(2) = 2088
share 3 = y(3) = 2191
share 4 = y(4) = 2318

# Plotting any three of the above shares against y(x) will result in a parabola who's intersection with the y-axis will be S
```


The above is not a full implementation as the shares can leak information about the secret, in the real algorithm there is an extra layer to obfuscate this.


---
# References

https://en.wikipedia.org/wiki/Shamir%27s_secret_sharing