# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

# Basic Types

## Unsigned Integer Data Types

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

## Signed Integer Data Types

|         Type |      Minimum |      Maximum |       Memory |       prefix |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| SINT         |         -128 |          127 |        8 bit |           si |
| INT          |       -32768 |        32767 |       16 bit |            i |
| DINT         |  -2147483648 |   2147483647 |       32 bit |           di |
| LINT         |        -2^63 |         2^63 |       64 bit |           li |

