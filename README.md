# Solidity_fundamentals

Solidity is a high-level, object-oriented programming language that is used to write smart contracts and build DApps. It also supports inheritance, libraries, and sophisticated user-defined types.

# Data types and Variables

Solidity data types are divided into 

## 1 Solidity value types
A value type stores its data directly in the memory it owns.

Signed integers
Unsigned integers
Boolean
Addresses
Enums
Bytes


## 2 Solidity reference types
Solidity reference types differ from value types in that they do not store values directly on their own. Instead, reference types store (or “reference”) the address of the data’s location and do not directly share the data.

Fixed-size arrays
Dynamic-size arrays
Array members
Byte arrays
String arrays
Structs
Mapping

Reference data types must be handled cautiously since they deal with storage locations. Data location affects the amount of gas used in a transaction and therefore can negatively impact smart contract development performance.

When using reference types, reference variables point a user to the location of value storage, and these can take up more than 32B of memory in size.

## Signed Integers

A signed integer, declared with the ```int``` keyword, is a value data type that can be used to store either positive or negative values in smart contracts.

```int``` is an abbreviation for int256, which has a range of -2 ** 255 to 2 ** 255 - 1. 

This value type takes up to 32B by default, but we can make it smaller by specifying the number of bits in steps of 8. For example: int8, int16, int32, etc.

Here’s an example of a signed integer in Solidity:

```
pragma solidity ^0.5.10

// example of int value type in solidity

contract SampleInts }

  { int = -168; }
```

## Unsigned integers

An unsigned integer, declared with the ```uint``` keyword, is a value data type that must be non-negative; that is, its value is greater than or equal to zero.

uint is an abbreviation for uint256. Just like signed integers, this value data type takes up to 32B by default. 

Again, we can make it smaller by specifying the number of bits in steps of 8. For example: uint8, uint16, uint32, etc.

For example, uint8 has a range of 0 to 2 ** 8 -1, and uint256 has a range of 0 to 2 **256 - 1.

Here’s an example of an unsigned integer in Solidity:

```
pragma solidity ^0.5.10

// example of uint value type in solidity

Contract  SampleUints   }

  uint public  u16 = 1890;
  uint public myUint u = 256;

}
```
