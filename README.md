# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

# Basic Types

## Boolean

|         Type |      Minimum |      Maximum |       Memory |       prefix |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| BIT          |        FALSE |         TRUE |        1 bit |              |
| BOOL         |        FALSE |         TRUE |        8 bit |            x |

Note: A BIT element requires 1 bit of memory space, and you can use it to address individual bits of a structure or function block using its name. BIT elements, which are declared sequentially, are consolidated to bytes. This allows you to optimize memory usage compared to BOOL types, which each occupy at least 8 bits. However, bit access takes significantly longer. Therefore, you should only use the data type BIT if you want to define the data in a specified format.
 
 ## Integer Data Types
 
 ### Unsigned Integer Data Types

|         Type |      Minimum |      Maximum |       Memory |       prefix |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| BYTE         |            0 |          255 |        8 bit |            b |
| WORD         |            0 |        65535 |       16 bit |            w |
| DWORD        |            0 |   4294967295 |       32 bit |           dw |
| LWORD        |            0 |       2^64-1 |       64 bit |           lw |
| USINT        |            0 |            0 |        8 bit |          usi |
| UINT         |            0 |        65535 |       16 bit |           ui |
| UDINT        |            0 |       2^64-1 |       32 bit |          udi |
| ULINT        |            0 |       2^64-1 |       64 bit |          uli |

### Signed Integer Data Types

| Type          | Minimum       | Maximum       | Memory        | Prefix        |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| SINT          | -128          | 127           | 8 bit         | si            |
| INT           | -32768        | 32767         | 16 bit        | i             |
| DINT          | -2147483648   | 2147483647    | 32 bit        | di            |
| LINT          | -2^63         | 2^63          | 64 bit        | li            |

## Floating Point Data Types

| Type          | Minimum       | Maximum       | Memory        | Prefix        |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| REAL          | -3.402823e+38 | 3.402823e+38  | 32 bit        | r             |
| LREAL         | -1.79769e+308 | 1.79769e+308  | 64 bit        | lr            |
