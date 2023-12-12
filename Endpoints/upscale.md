---
title: Upscale
icon: dot-fill
sidebar_position: 4
---

DevMind's Upscale is a revolutionary solution that transforms low-quality images into stunning, good-resolution masterpieces. Using cutting-edge artificial intelligence and advanced upscaling algorithms, this innovative tool analyzes and enhances every pixel, bringing out intricate details and vibrant colors. Whether it's restoring old photographs or refining compressed images, DevMind's Upscale delivers unparalleled image quality. Say goodbye to pixelation and hello to clarity with this powerful image enhancement tool. Elevate your visual content effortlessly, ensuring that every image captures the essence in breathtaking detail. Upscale your expectations with DevMind's transformative technology.

## Payload
- **Field**: `image` (Required)
  - **Type**: URL
  - **Description**: The image URL.

## Here is an example how to use DevMind's Upscale
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'image': 'https://devmind.thedevs.org/something.png'
}

response = requests.post('https://devmind.thedevs.org/upscale', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    image: "https://devmind.thedevs.org/something.png"
};

axios.post('https://devmind.thedevs.org/upscale', payload, { headers })
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
    let url = "https://devmind.thedevs.org/upscale";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "image": "https://devmind.thedevs.org/something.png"
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
        String url = "https://devmind.thedevs.org/upscale";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "image", "https://devmind.thedevs.org/something.png"
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
"Upscalled image"
```

## Example Image
<img src="/Public/img/upscale.png" />