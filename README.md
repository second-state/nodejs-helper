# Call Node.js functions from Rust

![Crates.io](https://img.shields.io/crates/d/nodejs-helper)
![Crates.io](https://img.shields.io/crates/l/nodejs-helper)
![Crates.io](https://img.shields.io/crates/v/nodejs-helper)

## Prerequisite

Must have Node.js installed with the following packages.

```
npm i ssvm sync-request better-sqlite3
npm i -g ssvmup
npm i -g wasm-pack
```

## How to use

Add cargo dependency

```
[dependencies]
nodejs-helper = "0.0.3"
```

Make Node.js Javascript API calls from Rust code!

```
#[wasm_bindgen]
pub fn utc_now() {
  let now: String = nodejs_helper::date::utc_string();
  nodejs_helper::console::log("UTC time: ");
  nodejs_helper::console::log(&now);
}
```

The Rust code must be compiled to WebAssembly and run from inside Node.js. [See how](https://cloud.secondstate.io/server-side-webassembly/getting-started)

## Examples

Demo code is [available here](https://github.com/second-state/wasm-learning/tree/master/nodejs/nodejs_example)

## Documentation

See [how the examples work](https://cloud.secondstate.io/server-side-webassembly/rust-and-javascript/call-javascript-functions-from-rust)

