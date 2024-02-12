# Web Crawler in Rust

This project is a simple web crawler written in Rust. It uses the `html5ever` and `surf` libraries to parse HTML and make HTTP requests, respectively.

## Overview

The main file `main.rs` contains the implementation of the web crawler. The crawler starts from a given URL and follows links up to a specified depth.

## Key Components

- `LinkQueue`: A struct that implements the `TokenSink` trait from `html5ever`. It processes HTML tokens and stores links found in `<a href="link">` tags.

- `get_links`: A function that takes a URL and a string of HTML, and returns a vector of URLs found in the HTML. It uses `html5ever` to parse the HTML and `LinkQueue` to store the links.

- `crawl`: An asynchronous function that takes a vector of URLs and a maximum depth. It fetches each URL, extracts links from the fetched HTML, and recursively crawls the extracted links up to the maximum depth.

- `box_crawl`: A helper function that boxes the future returned by `crawl`.

- `main`: The entry point of the program. It starts the web crawler at "https://www.rust-lang.org" with a maximum depth of 2.

## Usage

To run the web crawler, use the following command:

```bash
cargo run
```

## Dependencies

This project depends on the following Rust crates:

- `html5ever`
- `url`
- `async-std`
- `surf`
