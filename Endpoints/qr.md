---
title: QR
icon: dot-fill
sidebar_position: 3
---

DevMind's AI redefines QR code customization with unparalleled ease – introducing the QR code evolution. With a simple text prompt, effortlessly generate bespoke QR codes that merge seamlessly with your brand or message. Tailor the design, color scheme, and even incorporate your logo, transforming mundane QR codes into eye-catching, branded experiences. Whether for business, events, or personal use, DevMind's AI empowers you to encode information dynamically while maintaining an aesthetic edge. Say goodbye to generic QR codes and welcome a new era of personalized, visually appealing codes that captivate and convey your unique identity. Elevate your QR experience with DevMind's AI – where innovation meets customization.

## Payload
- **Field**: `url` (Required)
  - **Type**: URL
  - **Description**: URL of any website or a link
- **Field**: `q` (Required)
  - **Type**: String
  - **Description**: Define how the QR code should be

## Here is an example how to use DevMind's QR
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'url': 'https://devmind.thedevs.org',
    'q': 'A developer zone'
}

response = requests.post('https://devmind.thedevs.org/qr', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    url: "https://devmind.thedevs.org",
    q: "A developer zone"
};

axios.post('https://devmind.thedevs.org/qr', payload, { headers })
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
use serde_json::json;

#[tokio::main]
async fn main() -> Result<(), reqwest::Error> {
    let url = "https://devmind.thedevs.org/qr";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "url": "https://devmind.thedevs.org",
        "q": "A developer zone"
    });

    let client = reqwest::Client::new();
    let response = client.post(url).headers(headers).json(&payload).send().await?;

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
import com.google.gson.Gson;

public class HttpRequestExample {
    public static void main(String[] args) throws Exception {
        String url = "https://devmind.thedevs.org/qr";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "url", "https://devmind.thedevs.org",
            "q", "A developer zone"
        ));

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
[
    "QR code image URL",
    ...
]
```

## Example Image
<img src="https://media.discordapp.net/attachments/928129177654272021/1184123573397377024/qr.png?ex=658ad403&is=65785f03&hm=0be58febc96b6a395ecfab1262645d4ce3448daf2e8251c0aac301881ae9c2cc&=&format=webp&quality=lossless&width=662&height=662" />