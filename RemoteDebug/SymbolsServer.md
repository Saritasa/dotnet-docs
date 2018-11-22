# Symbols Server

- [Debugging with Symbols](https://docs.microsoft.com/en-us/windows/desktop/dxtecharts/debugging-with-symbols)
- [Deterministic builds in Roslyn](http://blog.paranoidcoding.com/2016/04/05/deterministic-builds-in-roslyn.html)

## SymStore

[SymStore](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/symstore) is a tool for creating symbol stores.

[SymStore Command-Line Options](https://docs.microsoft.com/en-us/windows/desktop/debug/symstore-command-line-options)

`C:\Program Files\Debugging Tools for Windows (x64)\symstore.exe`

Create a store and add symbols there:

```
symstore.exe add /t MyProduct /f C:\Path\To\PDB\Files /s C:\Path\To\Store
```

## SymChk

[SymChk](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/symchk) allows to verify that correct symbols files are available.

`C:\Program Files\Debugging Tools for Windows (x64)\symchk.exe`

```
symchk.exe C:\Path\To\Module.exe /s C:\Path\To\Store
```

```
symchk.exe "C:\Temp\ConsoleApp0.4.4_\ConsoleApp.exe" /s C:\Temp\oc2 /op /os
SYMCHK: ConsoleApp.exe       PASSED  - PDB: C:\Temp\oc2\ConsoleApp.pdb\518FB3130F9C49DFA0DC8D61F27771F31\ConsoleApp.pdb DBG: <N/A>

SYMCHK: FAILED files = 0
SYMCHK: PASSED + IGNORED files = 1
```

## Source Server

It's possible to get correct versions of source code from version control system.

- [Source Server](https://docs.microsoft.com/en-us/windows/desktop/debug/source-server-and-source-indexing)
- [Source Indexing is Underused Awesomeness](https://randomascii.wordpress.com/2011/11/11/source-indexing-is-underused-awesomeness/)
