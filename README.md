# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

# Naming Conventions

## Declarations

| Object | Prefix | Description | Example |
| ------------- | ------------- | ------------- | ------------- | 
| FUNCTION_BLOCK | FB_ | Function block | FB_WriteData |
| ACTION | | Action | WriteData | 
| METHOD | | Method | ClearData | 
| PROPERTY | Type Prefix* | Property | xIsDataAvailable |
| PROGRAM | P_ | Program | P_HandleData | 
| FUNCTION | F_ | Function | F_ManipulateData | 
| STRCUT | ST_ | Structure | ST_Data | 
| ENUMERATION | E_ | Enumeration type | E_DataType |  
| TYPE | T_ | Alias type | 
| UNION | U_ | Union | 
| INTERFACE | I_ | Interface | I_DataInterface |
| GVL | GVL_ | Global variable list | GVL_Data | 
| GCL | GCL_ | Global constant list | GCL_DataConstants | 
| GVCL | GVCL_ | Global variable and constant list | GVCL_Data |

Properties should be named according to their data type.  For example, a unsigned double integer property would be name udiThisProperty.   

For readability, it is recommended to combine revelant variables and constants into a single **G**lobal **V**ariable and **C**onstant **L**ist (GVCL) instead of seperating these into distinct **G**lobal **V**ariable **L**ist (GVL) and a **G**lobal **C**onstant **L**ist (GCL) files.  

## Variables of Elementary Data Types

### Boolean Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| BIT           | FALSE         | TRUE          | 1 bit         |               |
| BOOL          | FALSE         | TRUE          | 8 bit         | x             |

Note: While a BIT only uses 1 bit of memory space, it is less efficient to access than a BOOL because of how bits are consolidated in the memory of the device.  It is recommended that BITs are only used for specific purposes and that BOOL is used for a general boolean value.  
 
### Unsigned Integer Data Types
 | Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| BYTE         | 0              | 255           | 8 bit         | b             |
| WORD         | 0              | 65535         | 16 bit        | w             |
| DWORD        | 0              | 4294967295    | 32 bit        | dw            |
| LWORD        | 0              | 2^64-1        | 64 bit        | lw            |
| USINT        | 0              | 255           | 8 bit         | usi           |
| UINT         | 0              | 65535         | 16 bit        | ui            |
| UDINT        | 0              | 2^64-1        | 32 bit        | udi           |
| ULINT        | 0              | 2^64-1        | 64 bit        | uli           |

### Signed Integer Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| SINT          | -128          | 127           | 8 bit         | si            |
| INT           | -32768        | 32767         | 16 bit        | i             |
| DINT          | -2147483648   | 2147483647    | 32 bit        | di            |
| LINT          | -2^63         | 2^63          | 64 bit        | li            |

### System Specific Integer Type Conversion

These pseudo data types are converted to a platform-compliant data type by the compiler, depending on the target system.  

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 64-bit &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | 32-bit &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  |
| ------------- | ------------- | ------------- | ------------- |
| UXINT         | ULINT         | UDINT         | uxi           |
| XINT          | LINT          | DINT          | uxi           |
| XWORD         | LWORD         | DWORD         | xw            |

### Floating Point Data Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Minimum &nbsp; &nbsp; &nbsp; | Maximum &nbsp; &nbsp; &nbsp; | Memory &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| REAL          | -3.40e+38     | 3.40e+38      | 32 bit        | r             |
| LREAL         | -1.79e+308    | 1.79e+308     | 64 bit        | lr            |

### String Types

| Type | Description | Prefix | Interpretation |
| ------------- | ------------- | ------------- | ------------- |
| STRING        | string        | s             | ASCII         |
| WSTRING       | wide string   | ws            | Unicode       |

For the STRING datatype, each character requires 1 byte,  and an additoinal string terminating byte.  For example, if a STRING(50) is declared, this will occupy 51 bytes of memory. Each STRING is automatically terminated with a null character.  

The WSTRING datatype is interpreted in Unicode format.  For this datatype, each character requires at least 1, although possibly more, WORDs, because some Unicode characters require greater than one WORD. Due to this interpretation, the number of displayed characters does not neccisarily correspond to the length.  In addition to the WORDs required for characters, each WSTRING uses one additional WORD of memory. A WSTRING is terminated with 0.  

### Date, Time Types

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Description &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- | 
| TIME | time | t |
| LTIME | time | lt |
| TIME_OF_DAY | time of day | td |
| DATE | date | d |
| DATETIME | date and time | dt |

### Instances of Objects, and User-Defined Data Types:

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Description &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | ------------- |
| FUNCTION_BLOCK | FB_ | fb |
| STRUCT | ST_ | st |
| ENUM | E_ | e | 
| TYPE (Alias) | T_ | Alias type | 
| INTERFACE | I_ | ip |
| UNION | U_ | u |

### Naming Variables

Variables are to be named using camel case.  For example, a boolean variable would be written as xThisBoolean.  From the above guide, prefix x denotes that this variable is of the BOOl datatype.  

### Naming Constants

Constatns are to be named using a capitalized snake case, with the exception of the prefix, which will be lower case.  For example, a constant pre-factor to convert radians to degrees would be named lrRADIANS_TO_DEGREES.  From the instance naming guide, the prefix lr denotes from the prefix guide that this constant is of the LREAL datatype.  

## Legacy Naming

| Type | Old | New |
| --------- | ---- | ---- |
| BOOL      | b    | x    |
| BYTE      | n    | b    |
| DINT      | n    | di   |
| DWORD     | n    | dw   |
| INT       | n    | i    |
| LINT      | n    | li   |
| LREAL     | f    | lr   | 
| LWORD     | n    | lw   |
| REAL      | f    | r    |
| UDINT     | n    | udi  |
| UINT      | n    | ui   |
| USINT     | n    | usi  | 
| ULINT     | n    | uli  |
| UXINT     | n    | uxi  |
| WORD      | n    | w    |
| XINT      | n    | xi   |
| XWORD     | n    | xw   |
 
## Special Function Types

Because these functions are used frequently and their functionality is simple, these functions are considered special and have reserved prefixes to reduce name length.  

| Type &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Prefix &nbsp; &nbsp; &nbsp; &nbsp; |
| ------------- | ------------- | 
| R_TRIG        | rt            |
| F_TRIG        | ft            | 
| E_TRIG        | et            |
| TON           | ton           | 
| TOFF          | tof           |

## Tagging

Tags are intended to start with the @ sybmol and be spelled using all capitals.  This is intended, in the codesys envirionment, to make them uniquely findable, as the @ symbol cannot be incorporated into POU, DUT, etc. names.

| Tag                | Description                                                               |
| -------------     | ------------------------------------------------------------------------- |
| ```TODO```        | Intended to note where a future action should be taken.                   |
| ```@FIXME```      | Intended to note where something needs to be fixed.                       |
| ```@FUTURE```     | Intended to reserve a name, etc., for future use.                         |
| ```@REFACTOR```   | Intended to note where a refactor is required.                            |
| ```@DEPRECATE```  | Intended to describe a name, feature, etc. that is to be depricated.      |

# Ownership

# Sources

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

[e!COCKPIT manual](https://usermanual.wiki/Document/ecockpit20manual.952137147.pdf), see section 4.5.  
