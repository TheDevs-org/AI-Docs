---
title: Mascot
icon: dot-fill
sidebar_position: 2
---

DevMind's Mascot revolutionizes logo creation with simplicity and creativity. Just input a text prompt, and watch as our advanced AI seamlessly crafts a unique and vibrant mascot logo tailored to your brand. From playful characters to professional symbols, Mascot transforms your vision into a visual identity that resonates. No design skills needed; let the power of DevMind's innovation bring your brand to life. Elevate your business, project, or personal brand effortlessly with Mascot – where text sparks a world of visual possibilities, and every logo becomes an emblem of your distinctive identity. Welcome to mascot design made easy, courtesy of DevMind.

## Payload
- **Field**: `q` (Required)
  - **Type**: String
  - **Description**: The query you want to send to the DevMind AI.
- **Field**: `num_outputs` (Optional)
  - **Type**: Number
  - **Description**: Number of output you want at once. Maximum 4
- **Field**: `width` (Optional)
  - **Type**: Number
  - **Description**: Width of the image to be. Maximum 2048
- **Field**: `height` (Optional)
  - **Type**: Number
  - **Description**: Height of the image to be. Maximum 2048
- **Field**: `steps` (Optional)
  - **Type**: Number
  - **Description**: Numbers of setp to create the image. Maximum 100
- **Field**: `guidance_scale` (Optional)
  - **Type**: Number
  - **Description**: How much proper the image should be with the provided prompt. Maximum 50

## Here is an example how to use DevMind's Imagine
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'q': 'Groot is playing music and dancing',
    'num_outputs': 1,
    'width': 1048,
    'height': 1048,
    'steps': 100,
    'guidance_scale': 10
}

response = requests.post('https://devmind.thedevs.org/imagine', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    q: "Groot is playing music and dancing",
    num_outputs: 1,
    width: 1048,
    height: 1048,
    steps: 100,
    guidance_scale: 10
};

axios.post('https://devmind.thedevs.org/imagine', payload, { headers })
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
    let url = "https://devmind.thedevs.org/imagine";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "q": "Groot is playing music and dancing",
        "num_outputs": 1,
        "width": 1048,
        "height": 1048,
        "steps": 100,
        "guidance_scale": 10
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
        String url = "https://devmind.thedevs.org/imagine";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "q", "Groot is playing music and dancing",
            "num_outputs", 1,
            "width", 1048,
            "height", 1048,
            "steps", 100,
            "guidance_scale", 10
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
    "URL 1",
    ...
]
```

## Example Images
<img src="https://media.discordapp.net/attachments/928129177654272021/1184123576354361374/mascot-collage.png?ex=658ad404&is=65785f04&hm=b0b9396c7adf9df66863a97c04bd12e44d2f4921d5b2a49ba2d5031211348698&=&format=webp&quality=lossless&width=696&height=662" style="border-radius: 5px" />