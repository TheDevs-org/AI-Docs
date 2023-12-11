---
title: Chat
icon: dot-fill
sidebar_position: 1
---

With Chat AI, you can make your app interact with people or any subject!

### Payload
- **Field**: `q` (Required)
  - **Type**: String
  - **Description**: The query you want to send to the Bard AI.
- **Field**: `ref` (Optional)
  - **Type**: String
  - **Description**: Reference information, if applicable.

## Here is how you can setup
+++ Python
```python
import request
import json

headers={
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {"q": "Who are you?"}

response = request.post('https://devmind.thedevs.org/chat', headers=headers, body={
    q: "Who are you?"
})
print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = { q: 'Who are you?' };

axios.post('https://devmind.thedevs.org/chat', payload, { headers })
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```
+++Rust
```rust
use reqwest;

#[tokio::main]
async fn main() -> Result<(), reqwest::Error> {
    let url = "https://devmind.thedevs.org/chat";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = [("q", "Who are you?")];

    let client = reqwest::Client::new();
    let response = client.post(url).headers(headers).form(&payload).send().await?;

    let body = response.text().await?;
    println!("{}", body);

    Ok(())
}
```
+++Java
```java
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.nio.charset.StandardCharsets;

public class HttpRequestExample {
    public static void main(String[] args) throws Exception {
        String url = "https://devmind.thedevs.org/chat";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");

        // Set payload
        String payload = "q=Who+are+you?";
        con.setDoOutput(true);
        try (DataOutputStream wr = new DataOutputStream(con.getOutputStream())) {
            wr.writeBytes(payload);
            wr.flush();
        }

        int responseCode = con.getResponseCode();
        System.out.println("Response Code: " + responseCode);

        BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
        String inputLine;
        StringBuilder response = new StringBuilder();

        while ((inputLine = in.readLine()) != null) {
            response.append(inputLine);
        }
        in.close();

        System.out.println(response.toString());
    }
}

```
+++

Response:
```js
{
    "code": null,
    "content": "This is a DevMind, a cool AI",
    "status_code": 200,
    "text_query": "Who are you?",
}
```