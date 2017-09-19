## Message format:


* `sender`: unique id of the sender 
* `timestamp`: unix time (in seconds)
* `msg_id`: sequence number of message (message is identified by timestamp+msg_id)
* `topic`: topic to publish
* **+oneof**:
  * `payload`: data to send
  * `update`: `true` => indicates that this is an update request message 

