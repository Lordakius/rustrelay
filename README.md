# rustrelay

**this is a hobby project! Do not use in production!**

IRC-Server (eh, kind of), written in Rust. Focusing on Security and Usability, while ignoring any standard there might be out there (at least for now). 

## requirements analysis

### receive messages from clients in an encrypted format 

Communication should be encrypted. The encryption should include a stable known cryptographic mechanism as well as post-quantum encryption. 

### store as little information about the message and the clients as possible 

As a server we should minimize the data we store from the clients. Preferably, we do not even store meta-data. 

### minimize the used bandwidth

e.g. don't just broadcast every message. Distribute the message only to the relevant clients. This requirement may be optimized either way, reducing the bandwidth for the server or the client(s). 

## possible solutions

### billboard

One solution that should fulfill all requirements is a billboard-type of server. Clients can leave messages encrypted for other users with their public key. In a basic configuration one could just decrypt all messages, but that sounds very inefficient. As a meta information we could store the target key fingerprint (or ID), basically saying "this message is for the user X". 


#### considerations

* what about communications between multiple users? Can a key be derived by multiple keys (I think i read this somewhere)
* This architecture publishes the encrypted data, so it depends on strong (and lasting) encryption. 
* this approach should include something like ActivityPub, allowing for federation
* technically, one could implement it on top of an already existing protocol for distributing data, adding encryption (e.g. message in the fediverse) 

## Contributing

I am not looking for any active support, but am always happy to receive peer-reviews on both the architecture/design and the code itself. Feel free to open an issue! 
