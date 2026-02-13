# gleam_json

Encode and decode JSON in Gleam.

**Package:** [gleam_json on Hex](https://hex.pm/packages/gleam_json)  
**Docs:** [HexDocs](https://hexdocs.pm/gleam_json/)

## When to use

- Parsing JSON request/response bodies or config files.
- Producing JSON for APIs (encoding custom types to JSON strings).

## Entrypoints

- **gleam/json** — `json.parse(from: string, using: decoder)` returns `Result(Dynamic, DecodeError)`. Build decoders with `gleam/dynamic/decode`: `decode.field("name", decode.string)`, `decode.list(decode.int)`, etc., then `decode.success(MyType(...))`.
- **Encoding:** Build `json.Object` / `json.Array` / `json.String` etc. from your types, then `json.to_string(...)`.

## Pattern

Decoding: parse string → get `Dynamic` → run a `decode.Decoder(a)` built from `decode.*` combinators. Encoding: build JSON value from your type, then `json.to_string`.
