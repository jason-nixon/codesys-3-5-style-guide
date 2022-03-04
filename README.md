# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

# Identifiers for Variable and Instance Names

# Identifiers of POU and DUTs

## Variables of Elementary Data Types

### Boolean Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| BIT           | FALSE         | TRUE          | 1 bit         |               |
| BOOL          | FALSE         | TRUE          | 8 bit         | x             |

Note: While a BIT only uses 1 bit of memory space, it is less efficient to access than a BOOL because of how bits are consolidated in the memory of the device.  It is recommended that BITs are only used for specific purposes and that BOOL is used for a general boolean value.  
 
### Unsigned Integer Data Types
 | Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| BYTE         | 0              | 255           | 8 bit         |            b |
| WORD         | 0              | 65535         | 16 bit        |            w |
| DWORD        | 0              | 4294967295    | 32 bit        |           dw |
| LWORD        | 0              | 2^64-1        | 64 bit        |           lw |
| USINT        | 0              | 255           | 8 bit         |          usi |
| UINT         | 0              | 65535         | 16 bit        |           ui |
| UDINT        | 0              | 2^64-1        | 32 bit        |          udi |
| ULINT        | 0              | 2^64-1        | 64 bit        |          uli |

### Signed Integer Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| SINT          | -128          | 127           | 8 bit         | si            |
| INT           | -32768        | 32767         | 16 bit        | i             |
| DINT          | -2147483648   | 2147483647    | 32 bit        | di            |
| LINT          | -2^63         | 2^63          | 64 bit        | li            |

### System Specific Type Conversion

These psuedo data types are converted to a platform-compliant data type by the compiler, depending on the target system.  

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 64-bit &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 32-bit &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- |
| UXINT         | ULINT         | UDINT         | uxi           |
| XINT          | LINT          | DINT          | uxi           |
| XWORD         | LWORD         | DWORD         | xw            |

### Floating Point Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| REAL          | -3.40e+38     | 3.40+38       | 32 bit        | r             |
| LREAL         | -1.79e+308    | 1.79e+308     | 64 bit        | lr            |

## Naming Conventions for Types

## Naming Variables

Variables are to be named using camel case.  For example, a boolean variable would be written as xThisBoolean.  The prefix x denotes from the above prefix guide that this variable is type BOOL.  

## Naming Constants

Constants, unlike variables, are named using a capitalized snake case, with the exception of the prefix, which will be lower case.  For example, a constant to convert radians to degrees would be named lrRADIANS_TO_DEGREES.  The prefix lr denotes from the prefix guide that this constant is type LREAL.  

# Special Function Types

Because these functions are used frequently and their funcitonality is simple, these functions are considered special and have reserved prefixes to reduce name length.  

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | 
| R_TRIG        | rt            |
| F_TRIG        | ft            | 
| TON           | ton           | 
| TOFF          | tof           |

