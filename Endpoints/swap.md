---
title: Swap
icon: dot-fill
sidebar_position: 3
---

With DevMind's Swap AI feature, swapping faces in images is a breeze. Simply log in to the DevMind platform and head to the Swap AI tab. Upload your source and target images, and let the AI technology work its magic. The advanced algorithms accurately map and swap the faces, ensuring realistic and impressive transformations. Whether you're looking to create fun images or explore creative possibilities, DevMind's Swap AI feature offers a quick and easy way to achieve unique results. Try it out today and see for yourself the endless possibilities it brings!

#### Features:
- Looks realistic 
- Quick replacement

## Payload
- **Field**: `source_image` (Required)
  - **Type**: URL
  - **Description**: The image URL to swap face from.
- **Field**: `target_image` (Required)
  - **Type**: URL
  - **Description**: The image URL to swap face to.

## Here is an example how to use DevMind's Swap
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'source_image': 'https://devmind.thedevs.org/something.png',
    'target_image': 'https://devmind.thedevs.org/something-2.png'
}

response = requests.post('https://devmind.thedevs.org/swap', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    source_image: "https://devmind.thedevs.org/something.png",
    target_image: "https://devmind.thedevs.org/something-2.png"
};

axios.post('https://devmind.thedevs.org/swap', payload, { headers })
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
    let url = "https://devmind.thedevs.org/swap";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "source_image": "https://devmind.thedevs.org/something.png",
        "target_image": "https://devmind.thedevs.org/something-2.png"
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
        String url = "https://devmind.thedevs.org/swap";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "source_image", "https://devmind.thedevs.org/something.png",
            "target_image", "https://devmind.thedevs.org/something-2.png"
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
{
  "code": 200,
  "image": "Image URL",
  "msg": "succeed",
  "status": "succeed"
}
```

## Example Image
<img src="https://media.discordapp.net/attachments/928129177654272021/1184123574051676220/swap.png?ex=658ad404&is=65785f04&hm=5a226128042689f6f02f28d301e64a3d1bc3b906f894dfbfa61cb61071cbef42&=&format=webp&quality=lossless&width=1280&height=640" />