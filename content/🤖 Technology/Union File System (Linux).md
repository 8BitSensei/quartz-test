2023-02-27
#technology #linux

The Container Image relied on a Linux construct call the Union File System (UnionFS) which allows merging file systems. There are multiple implementations of this, but, looking at the OverlayFS file system, we can see how upper and multiple lower layers of files are merged while keeping the content separate.  If a file exists in multiple layers, the upper layer overrides the lower layer(s).

##### Adding
Adding a new file to the merged results will copy the same file into the upper file.

##### Deletion
You can delete a file deriving from the upper layer, no problem. But if you delete a file deriving from the lower layer(s), a corresponding file gets created in the upper file, which tells the file system that this file should be excluded from the merged result, while the file in the lower layer(s) still exists.

##### Modification
If you modify a file from the upper layer, it is simply modified. But, if you modify a file from a lower layer it is first copied to the upper layer, and then modified there, so that the modified file appears in the merged view while remaining unchanged in the modified lower layer.

```ad-info 
I highly reccomend working through the examples for the aboce in the '*Understanding container images - The fundamentals*' by Chaganti.
```


---
# References

 https://ravichaganti.com/blog/2022-10-18-understanding-container-images-the-fundamentals/