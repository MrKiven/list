# list

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Build Status](https://travis-ci.org/MrKiven/list.svg?branch=master)](https://travis-ci.org/MrKiven/list)
[![crates.io](https://img.shields.io/crates/v/list.svg)](https://crates.io/crates/list)
[![doc.rs](https://docs.rs/list/badge.svg)](https://docs.rs/list)

A singly-linked stack like list support peek.

## Getting started

### Installing

Add this to `Cargo.toml` file of your project:

```
[dependencies]
list = "~0.1.3"
```

### Usage

```rust
extern crate list;

use list::List;

fn main() {
    let mut list = List::new();
    // Check empty list behaves right
    assert_eq!(list.pop(), None);

    // Populate list
    list.push(1);
    list.push(2);
    list.push(3);

    // Check normal removal
    assert_eq!(list.pop(), Some(3));
    assert_eq!(list.pop(), Some(2));

    // Push some more just to make sure nothing's corrupted
    list.push(4);
    list.push(5);

    // Check normal removal
    assert_eq!(list.pop(), Some(5));
    assert_eq!(list.pop(), Some(4));

    // Check exhaustion
    assert_eq!(list.pop(), Some(1));
    assert_eq!(list.pop(), None);
}
```

### Run test

`cargo test -v`


## LICENSE

[MIT](LICENSE)
