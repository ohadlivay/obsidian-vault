data is split into blocks and stored seperatly. each block has an address but no metadata. useful for [[VM]]'s, transactional systems.
pros: 
* fast read and write
* more control over storage
cons: 
* no metadata, so need filesystem to manage
* doesnt scale easily across distributed systems
