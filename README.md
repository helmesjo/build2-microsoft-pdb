# microsoft-pdb - Microsoft PDB and CodeView debug information C++ headers

This is a `build2` package repository for
[`microsoft-pdb`](https://github.com/microsoft/microsoft-pdb), the
information from Microsoft about the PDB (Program Database) symbol file
format: the CodeView debug information headers and the API header of the
`mspdb` DLL.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`libmicrosoft-pdb` in your `build2`-based project, then instead see the
accompanying [`PACKAGE-README.md`](libmicrosoft-pdb/PACKAGE-README.md) file.

Only the upstream headers and documentation are packaged. The `PDB/`
(`mspdb` DLL), `cvdump/`, `pdbdump/`, and `pdbtest/` sources cannot be built:
they need Microsoft-internal headers, libraries, and build files that are not
part of upstream (see
[upstream issue #14](https://github.com/microsoft/microsoft-pdb/issues/14)).

The development setup for `microsoft-pdb` uses the standard `bdep`-based
workflow. `libmicrosoft-pdb` is only supported on Windows. For example:

```
git clone .../microsoft-pdb.git
cd microsoft-pdb

bdep init -C @msvc cc config.cxx=cl
bdep update
bdep test
```
