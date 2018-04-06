# Demonstration of bug in Neomake checker for Rust

This repo contains two Rust projects:

- `no_workspaces` is just a standard binary crate.
- `workspace` is a [Cargo workspace](https://doc.rust-lang.org/book/second-edition/ch14-03-cargo-workspaces.html) with a single binary crate.

## The bug

Within `no_workspaces` `:Neomake` works just fine, but within `workspaces` it does nothing.

## Setup

Neovim:
```
$ vim -v
NVIM v0.2.2
Build type: Release
LuaJIT 2.0.5
Compilation: /usr/local/Homebrew/Library/Homebrew/shims/super/clang -Wconversion -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=1 -DNVIM_MSGPACK_HAS_FLOAT32 -DNVIM_UNIBI_HAS_VAR_FROM -DNDEBUG -DMIN_LOG_LEVEL=3 -Wall -Wextra -pedantic -Wno-unused-parameter -Wstrict-prototypes -std=gnu99 -Wimplicit-fallthrough -Wvla -fstack-protector-strong -fdiagnostics-color=auto -DINCLUDE_GENERATED_DECLARATIONS -I/tmp/neovim-20180209-66903-ukwirj/neovim-0.2.2/build/config -I/tmp/neovim-20180209-66903-ukwirj/neovim-0.2.2/src -I/usr/local/include -I/usr/local/include -I/usr/local/include -I/usr/local/include -I/usr/local/include -I/usr/local/include -I/usr/local/opt/gettext/include -I/usr/include -I/tmp/neovim-20180209-66903-ukwirj/neovim-0.2.2/build/src/nvim/auto -I/tmp/neovim-20180209-66903-ukwirj/neovim-0.2.2/build/include
Compiled by brew@Sierra-2.local

Features: +acl +iconv +jemalloc +tui
See ":help feature-compile"

   system vimrc file: "$VIM/sysinit.vim"
  fall-back for $VIM: "/usr/local/Cellar/neovim/0.2.2_1/share/nvim"

Run :checkhealth for more info
```

Neomake: The latest version as per 06 April 2018. Don't know how to see the exact version.

Rust:
```
$ rustc --version
rustc 1.25.0 (84203cac6 2018-03-25)
```

Cargo:
```
$ cargo --version
cargo 0.26.0 (41480f5cc 2018-02-26)
```

I have made no configurations to Neomake with regards to Rust. My Vim config is [here](https://github.com/davidpdrsn/dotfiles/blob/master/nvim/init.vim).
