# codesys-3-5-style-guide
Colorful animal style guide for Codesys 3.5.  

[Beckhoff TwinCAT naming guide](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/3146718603.html)

# Basic Types

## Integer data types


|         Type |      Minimum |      Maximum |       Memory |       prefix |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| BYTE         |            0 |          255 |        8 bit |            b |
| WORD         |            0 |        65535 |       16 bit |            w |
| DWORD        |            0 |   4294967295 |       32 bit |           dw |
| LWORD        |            0 |       2^64-1 |       64 bit |           lw |
| SINT         |         -127 |          127 |        8 bit |           si |
| USINT        |            0 |            0 |        8 bit |          usi |
| INT          |              |              |       16 bit |            i |
| UINT         |              |              |       16 bit |           ui |
| DINT         |              |              |       32 bit |           di |
| UDINT        |            0 |       2^64-1 |       32 bit |          udi |
| LINT         |        -2^63 |         2^63 |       64 bit |           li |
| ULINT        |            0 |       2^64-1 |       64 bit |          uli |



