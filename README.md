# rustrelay

**this is a hobby project! Do not use in production!**

IRC-Server, written in Rust. Focusing on Security and Usability, while ignoring any standard there might be out there (at least for now). 

## requirements analysis

### receive messages from clients in an encrypted format 

Communication should be encrypted. The encryption should include a stable known cryptographic mechanism as well as post-quantum encryption. 

### store as little information about the message and the clients as possible 

As a server we should minimize the data we store from the clients. Preferably, we do not even store meta-data. 

### minimize the used bandwidth

e.g. don't just broadcast every message. Distribute the message only to the relevant clients. This requirement may be optimized either way, reducing the bandwidth for the server or the client(s). 


## Contributing

I am not looking for any active support, but am always happy to receive peer-reviews on both the architecture/design and the code itself. Feel free to open an issue! 
