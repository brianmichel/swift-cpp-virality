# Swift C++ Interop Virality

A small repo to demonstrate the virality of Swift's C++ interop. Unfortunately it seems that a library that might want to be C only has no way of marking itself as such when interop is enabled on a package that consumes it which has C++ interop turned on.

This feels unexpected and will have pretty dramatic behavior changes for frameworks that inlcude system header files which change type signatures and the like when compiled in a C++ context (like Windows).

## Steps to Reproduce
1. Open up the Package.swift inside of the `consuming_module` folder
2.Comment out line `26` to see the available signatures move around.

## Expected Result
A library should be able to define that it's C only and should not be compiled with a C++ context.