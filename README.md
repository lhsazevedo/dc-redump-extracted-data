# Dreamcast Redump Extracted Data v1 (slim)
This archive contains file listings, ~~main binaries~~, and strings found in the
main binaries from the REDUMP Dreamcast collection. 1310 releases were parsed,
with 162 releases skipped due to missing .gdi file.

> [!WARNING]
> This archive is intended for research and educational purposes only and does not
> include actual game images.

## Contents
For each release, the archive includes:

1. A txt file listing the disc contents (`files.txt`).
2. ~~The IP.BIN file.~~
3. ~~The main game binary (usually `1ST_READ.BIN`), extracted from the disc. For
   WinCE games, `.EXE` and `.DLL` files in the disc root were included as well.~~
4. Text files (`*.strings.txt`) containing the results of running Unix `strings`
   commands on the extracted binaries.

Note that the slim version only includes text files.

## How to search
Users can perform regex searches on file lists and binary strings using the
following Unix commands:

- To search in file lists:
  ```sh
  # Search for `*.ELF` files in disc
  $ find -name files.txt -exec grep -H -i -E '\.ELF$' {} \;
  ```
  Sample result:
  ```
  ./South Park Rally (USA)/files.txt:/CDIMAGE.ELF
  ./Dragons Blood (Europe) (En,Fr,De)/files.txt:/DIE2/DATA/RELEASE.ELF
  ./South Park Rally (Europe) (En,Fr,De,Es)/files.txt:/CDIMAGE.ELF
  ./Atsumare! Guru Guru Onsen BB (Japan)/files.txt:/GAME/BFRONT.ELF
  (...)
  ```

- To search in strings extracted from binaries:
  ```sh
  # Search for `*.C` file names left in binaries
  find -name *.strings.txt -exec grep -H -i -E '\.C$' {} \;
  ```
  Sample result:
  ```
  ./Rayman 2 - The Great Escape (Europe) (En,Fr,De,Es,It)/bins/1ST_READ.BIN.strings.txt:WinMain.c
  ./Rayman 2 - The Great Escape (Europe) (En,Fr,De,Es,It)/bins/1ST_READ.BIN.strings.txt:src/DevVpt.c
  ./Rayman 2 - The Great Escape (Europe) (En,Fr,De,Es,It)/bins/1ST_READ.BIN.strings.txt:src/Material.c
  ./Rayman 2 - The Great Escape (Europe) (En,Fr,De,Es,It)/bins/1ST_READ.BIN.strings.txt:FileMng.c
  ./Rayman 2 - The Great Escape (Europe) (En,Fr,De,Es,It)/bins/1ST_READ.BIN.strings.txt:Engine.c
  ```

## Credits
Lucas Azevedo
http://lhsazevedo.dev
