---
title: Vision
icon: dot-fill
sidebar_position: 3
---

DevMind's Vision – an extraordinary AI tool that interprets images with unparalleled accuracy. Simply upload any image, and watch as our advanced artificial intelligence meticulously analyzes and defines its intricate details. From recognizing objects and scenes to discerning complex patterns, DevMind's Vision unveils the essence of your visuals. Ideal for industries ranging from e-commerce to content creation, this innovative tool harnesses the power of AI to effortlessly interpret and articulate the content of your images. Transform your imagery into actionable insights with DevMind's Vision, where every pixel tells a story and every image is understood with precision.

## Payload
- **Field**: `image` (Required)
  - **Type**: URL
  - **Description**: URL of the image to define
- **Field**: `q` (Optional)
  - **Type**: String
  - **Description**: Any string you want to add for the image

## Here is an example how to use DevMind's Vision
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

response = requests.post('https://devmind.thedevs.org/vision', json=payload, headers=headers)

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

axios.post('https://devmind.thedevs.org/vision', payload, { headers })
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
    let url = "https://devmind.thedevs.org/vision";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "song": "https://devmind.thedevs.org/something.png"
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
        String url = "https://devmind.thedevs.org/vision";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "song", "https://devmind.thedevs.org/something.png"
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
  "code": "",
  "content": "Image defination",
  "status_code": 200
}
```