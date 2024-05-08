# sturnidae

Binding to Starling Bank's API.

[![Package Version](https://img.shields.io/hexpm/v/sturnidae)](https://hex.pm/packages/sturnidae)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/sturnidae/)

```sh
gleam add sturnidae
```
```gleam
import sturnidae
import gleam/httpc

pub fn main() {
  // Build an API request
  let request =
    sturnidae.get_feed_items_request(
      personal_access_token,
      account_uid,
      category_uid,
      "2015-01-01T01:01:00.000Z",
    )

  // Send it with a HTTP client such as gleam_httpc
  let assert Ok(response) = |> httpc.send

  // Decode the response into Gleam data
  let assert Ok(items) = sturnidae.get_feed_items_response(response)
}
```

Further documentation can be found at <https://hexdocs.pm/sturnidae>.
