# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

# Basic Types

## Boolean

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  | Minimum       | Maximum       | Memory        | Prefix        |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| BIT           | FALSE         | TRUE          | 1 bit         |               |
| BOOL          | FALSE         | TRUE          | 8 bit         | x             |

Note: While a BIT only uses 1 bit of memory space, it is less efficient to access than a BOOL because of how bits are consolidated in the memory of the device.  It is recommended that BITs are only used for specific purposes and that BOOL is used for a general boolean value.  
 
 ## Integer Data Types
 
 ### Unsigned Integer Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  | Minimum       | Maximum       | Memory        | Prefix        |
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

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  | Minimum       | Maximum       | Memory        | Prefix        |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| SINT          | -128          | 127           | 8 bit         | si            |
| INT           | -32768        | 32767         | 16 bit        | i             |
| DINT          | -2147483648   | 2147483647    | 32 bit        | di            |
| LINT          | -2^63         | 2^63          | 64 bit        | li            |

## Floating Point Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  | Minimum       | Maximum       | Memory        | Prefix        |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| REAL          | -3.402823e+38 | 3.402823e+38  | 32 bit        | r             |
| LREAL         | -1.79769e+308 | 1.79769e+308  | 64 bit        | lr            |
