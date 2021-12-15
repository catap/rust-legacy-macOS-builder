# rust builds with support of legacy macOS

This repository contains daily builds for the last rust which can be used on
legacy macOS and can produce code which can run on legacy macOS.

Idea behind is simple: it uses a ptach https://reviews.llvm.org/D115250 which
was modified to always emulate TLV on macOS.

This changes allows to easy produce a rust which can run on any x86_64 macOS.
With probably relinking to actual system libraries :) Like it is done at
MacPorts, and I strongly suggest to use it as stage0 compiler.

Also, you need a clang which is build with this patch to compile anything. Yeah,
MacPorts contains such clang ;)

Anyway, this build required following PR for rust:
 - https://github.com/rust-lang/rust/pull/91765
 - https://github.com/rust-lang/rust/pull/91744
