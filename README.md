# DemoApiScalarGalaxy C++ API Library

This library provides convenient access to the DemoApiScalarGalaxy REST API from C++ applications.
It is generated from your OpenAPI document with typed request descriptors, models, resources, and C++20 support.

The full generated API reference is available in `api.md` and the operation inventory is available in `reference.md`.

## Installation

```sh
cmake -S . -B build
cmake --build build
```

## Usage

Create a generated client and pass request descriptors to your preferred HTTP transport.

The generated client builds request descriptors and delegates HTTP execution to an injectable transport.
This keeps the SDK portable across libcurl, Boost.Beast, platform HTTP stacks, and test transports.

```cpp
#include <demo_api_scalar_galaxy_cpp/client.hpp>

int main() {
  demo_api_scalar_galaxy::DemoApiScalarGalaxyClient client;
  auto response = client.planets.list(ListParams{});
  return 0;
}
```

## Request and Response Types

Request params and response bodies are generated as C++ types using `std::optional`, `std::variant`, and value-oriented structs where appropriate.
Wire names are preserved in request metadata while public symbols use sanitized C++ identifiers.

## Handling Errors

Generated response wrappers preserve status, headers, raw body, and typed error metadata when available.
Transport failures remain under the caller-provided transport boundary.

## Retries and Timeouts

Request descriptors carry timeout, retry, header, query, base URL, and idempotency settings so transports can apply them consistently.

## Pagination

Paginated operations expose page metadata in generated descriptors and manifests when pagination is described by the OpenAPI document.

## Raw Responses and Custom Requests

Raw response metadata is preserved through request and response descriptors.
Extra headers and query params can be attached through `RequestOptions` for undocumented API fields.

## Requirements

C++20 with CMake 3.20+.
