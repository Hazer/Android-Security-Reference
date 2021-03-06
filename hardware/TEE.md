#General Info

- See [Trusty TEE](https://source.android.com/security/trusty/index.html)
- See [Mobile Platform Security: Trusted Execution Environments](http://asokan.org/asokan/Padova2014/tutorial-mobileplatsec.pdf)

From 'Android Security Internals' the Nexus 4 was TrustZone enabled, with QSEE implemented on top of that. Most likely uses a single master key-encryption key (KEK) which protects all user-generated keys but implementations may use KEK per key and / or hardware fused KEKs.

#Vulns

- 30/6/2016 [Extracting Qualcomm's KeyMaster Keys – Breaking Android Full Disk Encryption](https://news.ycombinator.com/item?id=12007923)
  - Shows how the KEK can be lifted from Android devices and claims not fixable i.e. a hardware issue. Talks about how this means FDE (full disk encryption) is not bound to the device hardware, which is bad as it could easily be brute-forced off-device. 
  - Likely to have implications to `KeyStore` use

