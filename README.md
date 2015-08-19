# BlockChain Demonstration

A very simple BlockChain implementation intended to illustrate the concept.

Marty Anstey (https://marty.anstey.ca/)

The block index simply maps a block to a disk offset for convenience.
It's not necessary, but it makes it much easier to quickly locate any
block within the chain.

### File Formats
All values are stored as little-endian.

##### ISAM Index

_Header_

type     | size | description
:---------|:---:|:-------------
uint_32t | 4 | Record count

_Records_

type     | size | description
:---------|:---:|:-------------
uint_32t | 4 | Offset
uint_32t | 4 | Length


##### BlockChain

type     | size | description
:---------|:---:|:-------------
uint32 | 4 | Magic
uint8 | 1 | Block format
uint32 | 4 | Timestamp
uint8[32] | 32 | Previous hash
uint32 | 4 | Data length
data | ? | Arbitrary data


