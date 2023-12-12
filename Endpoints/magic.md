---
title: Magic Avatar
icon: dot-fill
sidebar_position: 2
---

DevMind's Magic Avatar, where ordinary photos transcend into captivating, cool masterpieces. This cutting-edge tool harnesses the magic of artificial intelligence to elevate your selfies, portraits, and snapshots to a whole new level. Unleash a symphony of effects, from dynamic filters to artistic enhancements, transforming your images into visually stunning works of art. No complex editing skills required – just upload your photo, and let Magic Avatar weave its spell. Watch as mundane moments metamorphose into extraordinary memories. Redefine your visual narrative effortlessly with DevMind's Magic Avatar, where every photo becomes a magical tale waiting to be told.

## Payload
- **Field**: `image` (Required)
  - **Type**: URL
  - **Description**: Image URL with face.
- **Field**: `gender` (Required)
  - **Type**: male | female
  - **Description**: Which gender magic you want, male or female

## Here is an example how to use DevMind's Magic Avatar
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'image': 'Image URL',
    'gender': 'male | female'
}

response = requests.post('https://devmind.thedevs.org/magic', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    image: 'Image URL',
    gender: 'male | female'
};

axios.post('https://devmind.thedevs.org/magic', payload, { headers })
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
    let url = "https://devmind.thedevs.org/magic";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "image": "Image URL",
        "gender": "male | female"
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
        String url = "https://devmind.thedevs.org/magic";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "image", "Image URL",
            "gender", "male | female"
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

## Example Images
<img src="https://media.discordapp.net/attachments/928129177654272021/1184123575129612298/magic.png?ex=658ad404&is=65785f04&hm=2888c49759e6fbc7acc43d14769d657140181619007f20cf6f24a2aa51cbd2b4&=&format=webp&quality=lossless&width=1280&height=640" />