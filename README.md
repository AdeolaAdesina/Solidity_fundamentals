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

## Boolean

The bool value data type is used in Solidity to illustrate cases that have binary results. A bool has two fixed values: true or false, with false being the default. This data type only takes up 1B of storage.

Solidity supports all standard Boolean operators, such as:

!= (inequality)
== (equality)
! (logical negation)
&& (logical conjunction, “AND”)
|| (logical disjunction, “OR”)

Here’s an example showing how a bool data type is declared and assigned a value in Solidity:

```
pragma solidity ^0.5.10

// example of a bool value type in solidity

Contract  SampleBool   } 

  bool public  IsVerified = False;
    bool public IsSent = True;

}
```

## Addresses
An address value type is specifically designed to hold up to 20B, or 160 bits, which is the size of an Ethereum address.

Solidity actually offers two address value types: address and address payable. The difference between the two is that address payable can send and transfer Ether.

We can use an address to acquire a balance using the .balance method and to transfer a balance using the .transfer method.

Here’s an example of an address data type in Solidity:

```
pragma solidity ^0.5.10

// example of an address value type in solidity

Contract  SampleAddress   } 
  address public  myAddress =
0xb794f5ea0ba39494ce839613fffba74279579268;

}
```

## Enums

This data type is used explicitly for constant values, such as the names of integral constants, making a smart contract easier to read and maintain. Enums can help reduce the incidence of bugs in your code.

Enums limit a variable to a few predefined values and each copy maintains its value.

Options are represented by integer values beginning with zero; you can also specify a default value for the enum.

Here’s an example declaring an enum named food_classes consisting of six constant values: carb, protein, fats-oils, water, vitamin, and minerals:

```
pragma solidity ^0.5.10
// example of an enum value type in solidity
Contract  SampleEnum   } 

 enum  < food_classes >  }
          carb, protein, fats-oils, water, vitamin, and minerals;
}
```

It’s important to note that DApps do not recognize an enum within a smart contract. An integer value that corresponds to the enum constant must be provided.


## Bytes
In Solidity, byte refers to 8-bit signed integers. Everything in memory is stored in bits with binary values 0 and 1.

The bytes value type in Solidity is a dynamically sized byte array. It is provided for storing information in binary format. Since the array is dynamic, its length can grow or shrink.

To reflect this, Solidity provides a wide range — from bytes1 to bytes32. The data type bytes1 represents one byte, while bytes32 represents 32B. 0 x 00 is the default value for byte. This value is used to prepare the default value.

Here are some examples of the bytes data type in Solidity:

```
pragma solidity ^0.5.10

// example of a byte data type in hexadecimal format in solidity

Contract  SampleByte   }

   bytes1 uu = 0 x 45;

}
```

# Solidity reference types

Two separate variables can refer to the exact location, and any change in one variable can affect the other. Several variables that point to the same address can be used to effect a change in a reference data type.

There are several reference data types in Solidity: fixed-sized arrays, dynamic-sized arrays, array members, byte arrays, string arrays, structs, and mapping.
 


## Arrays
Arrays are a group of variables of the same data type, with each variable having a unique index. Array size can be fixed or dynamic.

Arrays data structures are dependent on other data types. They keep these data in storage and simplify the process of repetition, storage, and search for variables or a subset of variables within a group.

We can retrieve a requested variable by using the unique index location.

Here’s an example of an array in Solidity:

```
pragma solidity ^0.5.10

// code illustration of array in solidity

Contract  SampleArray   } 

    uint [10] = MyIntArray ;
}
```

## Fixed-size arrays
Fixed-size arrays have a predefined size when they are declared.

Here’s an example of a fixed-size array in Solidity:

```
pragma solidity ^0.5.10

// code illustration of fixed-size array in solidity

Contract  SampleFixedSizeArray   }

uint[6] arrayName;

}
```

In Solidity, we cannot use the new keyword with a fixed-size array. Instead, the array’s data variables must be initialized inline, like so:

```
pragma solidity ^0.5.10

// code illustration of fixed-size array in solidity
Contract  SampleFixedSizeArray   }
uint [6] age =  [ unit (60), 70, 80, 90, 100, 110]  ;
```

They may also be initialized inline with a function:

```
pragma solidity ^0.5.10

// code illustration of fixed-size array in solidity

Contract  SampleFixedSizeArray   }
uint [6] age  ;
age  = [ unit (60), 7, 8, 9, 10, 11]  ;
```

## Dynamic-size arrays
Dynamic arrays do not have a predefined size when they are declared. Instead, their size is determined at run time.

Here’s an example of a dynamic-size array in Solidity:

```
pragma solidity ^0.5.10

// code illustration of fixed-size array in solidity

Contract  SampleDynamicSizeArray   }

int[] arrayName; 
```

We can initialize a dynamic array either inline or by using the new keyword like so:

```
pragma solidity ^0.5.10

// code illustration of dynamic-size array in solidity

Contract  SampleDynamicSizeArray   }

   int[5] englishMarks = [uint(50), 60,70,80,90];
   int[] scienceMarks = new int[](5);
```


## Structs
The struct reference type in Solidity refers to a new (or custom) data type. You can use the struct keyword to define a structure, made up of multiple variables, which can be both value type and reference type.

In most cases, struct is used to represent a record.

It’s important to note that because structs must be finite in size, they cannot contain members of their type. This is not to say that struct cannot contain struct; for example, struct A can contain struct B, but struct A cannot contain struct A.

Here’s an example of a struct data type in Solidity:

```
pragma solidity ^0.5.10
// code illustration of string array in solidity

Contract SampleStruct

struct patient {
            string name;
            string age;
            uint16 gender;
 }
```

## Mapping
In Solidity, mapping functions similarly to a hashtable or dictionary in other programming languages.

Mapping is the most frequently used reference type in Solidity. Mapping types are used to store data in the form of key-value pairs, where the key can be any of the inbuilt data types except for reference types, and the value can be any type.

The mapping function can retrieve stored data using the supplied key.

Because Solidity mapping only provides an option for one data storage location, this data type is permitted for state elements.

The mapping type is declared using the mapping keyword followed by data types for both key and value, separated by the => notation.

Here’s an example of a mapping type in Solidity:

```
pragma solidity ^0.5.10
// code illustration of  mapping type in solidity
Contract SampleMap 
   
mapping (unit => address)  Variables;
```

