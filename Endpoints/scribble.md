---
title: Scribble
icon: dot-fill
sidebar_position: 5
---

DevMind's Scribble, a groundbreaking tool that effortlessly transforms your hand-drawn sketches into captivating digital images. With its state-of-the-art image recognition and conversion technology, Scribble bridges the gap between traditional artistry and modern digital expression. Simply sketch your ideas on paper, and let Scribble seamlessly convert them into high-quality digital images, preserving the authenticity of your hand-drawn charm. Whether you're an artist, designer, or hobbyist, unleash your creativity with Scribble, turning your imaginative strokes into polished, shareable masterpieces. Redefine the art of digital creation with DevMind's Scribble – where every stroke tells a story, and every drawing becomes a work of digital art.

## Payload
- **Field**: `image` (Required)
  - **Type**: URL
  - **Description**: The image URL.
- **Field**: `prompt` (Required)
  - **Type**: String
  - **Description**: The prompt of the scribble image

## Here is an example how to use DevMind's Scribble
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'image': 'https://devmind.thedevs.org/something.png',
    'prompt': 'An Apple in a fruit basket'
}

response = requests.post('https://devmind.thedevs.org/scribble', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    image: "https://devmind.thedevs.org/something.png",
    prompt: "An Apple in a fruit basket"
};

axios.post('https://devmind.thedevs.org/scribble', payload, { headers })
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
    let url = "https://devmind.thedevs.org/scribble";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "image": "https://devmind.thedevs.org/something.png",
        "prompt": "An Apple in a fruit basket"
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
        String url = "https://devmind.thedevs.org/scribble";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "image", "https://devmind.thedevs.org/something.png",
            "prompt", "An Apple in a fruit basket"
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
  "input": "Input Image URL",
  "output": "Output Image URL"
}
```

## Example Image
<img src="https://media.discordapp.net/attachments/928129177654272021/1184123573732917329/scribble.png?ex=658ad403&is=65785f03&hm=73906b27c7725b37774ad372da23d5759a456376c3911fba4a9b470ed68f4f60&=&format=webp&quality=lossless&width=1280&height=640" />