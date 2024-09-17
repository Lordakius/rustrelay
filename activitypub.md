# activitypub idea

Using ActivityPub, we can create servers, holding the "blackboard" messages, optimally only for a specified amount of time and clients grabbing them whenever they want. Federation could allow custom instances with different settings for retention rate, caching and acceptance for users (both sending and receiving). 

## jobs

### server

* accept incoming new message 

The message should be encrypted so that the server cannot read the content.

* allow download of (encrypted) message by any client

How does the client know which message they should download?

* target agnostic

The server should not store who the target user is. It can store which IP connected and requested a message.

* sender agnostic

optimally, the server does not store who the sender was. We should consider a solution against DoS, which probably requires at least some kind of identification. 


### client

* send message to any server
* pull message from any server
