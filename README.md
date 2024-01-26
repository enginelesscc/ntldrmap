# ntldrmap
Maps DLLs from Memory like a real Module

# notes
- Can load dlls/exe/any_pe from any in-memory buffer, does not rely on disk/fs/kernel_image
- Currently works (tested) from Windows XP..7..8..10 up to current upstream Windows 11 Canary (Build 26020)!
- Works on Wine!
- Does NOT work on Proton (Because its ldr doesnt use ntdll), but it likely doesnt verify anything, so any mapper would do
- Requires no private symbols!
- Exceptions work fine (SEH, C++ eh, etc..), on both x86 and amd64!
- No issues/conflicts with cf guards
- Mapped modules are visible via winapi, can be enumerated/queried like any other dll!
- Modules are present in peb, recognized as real modules!
- No deps besides ntdll (Makes use of syscalls directly)
- Works exactly like LoadLibrary, which is how it achieves compat
- dlls like openssl dont have breaking side effects (manualmapped openssl does fail to initialize, but works fine with ntldrmap)

# release plans
- atm none, keeping bits private for now. repo only exists for contact purpose.
