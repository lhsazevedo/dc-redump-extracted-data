# Dreamcast Redump Extracted Data v1
This archive contains file listings and main binaries for the REDUMP Dreamcast
collection. 1310 releases were parsed, with 162 releases skipped due to missing
.gdi file.

## Contents
For each release, the archive includes:

1. A txt file listing the disc contents (`files.txt`).
2. The IP.BIN file.
3. The main game binary (usually `1ST_READ.BIN`), extracted from the disc. For
   WinCE games, `.EXE` and `.DLL` files in the disc root were included as well.
4. Text files (`*.strings.txt`) containing the results of running Unix `strings`
   commands on the extracted binaries.

Note that the slim version only includes text files.

## How to search
Users can perform regex searches on file lists and binary strings using the
following Unix commands:

- To search in file lists:
  ```
  # Search for `*.ELF` files in disc
  find -name files.txt -exec grep -H -i -E '\.ELF$' {} \;
  ```

- To search in strings extracted from binaries:
  ```
  # Search for `*.C` file names left in binaries
  find -name *.strings.txt -exec grep -H -i -E '\.C$' {} \;
  ```

## Disclaimer
This archive is intended for research and educational purposes only and does not
include actual game images.

## Credits
Lucas Azevedo
http://lhsazevedo.dev
