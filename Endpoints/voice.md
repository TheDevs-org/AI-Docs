---
title: Voice
icon: dot-fill
sidebar_position: 3
---

DevMind's Voice – the ultimate audio metamorphosis tool. Seamlessly alter the tone of any audio file, adding a touch of uniqueness to your recordings. Whether you desire the charisma of Trump, the whimsy of Mr. Krabs, the intrigue of Obama, or the rhythm of a guitar or violin, DevMind's Voice offers a spectrum of presets for instant, captivating modifications. Elevate your audio projects with ease, injecting personality and flair effortlessly. From podcasts to music tracks, DevMind's Voice empowers you to curate an auditory experience that stands out, making every sound your own in just a few clicks.

#### Voices:
- Squidward
- MrKrabs
- Plankton
- Drak
- Vader
- Trump
- Biden
- Obama
- Guitar
- Voilin
- CUSTOM (Must need to provide URL)

## Payload
- **Field**: `song` (Required)
  - **Type**: URL
  - **Description**: URL of the audio file
- **Field**: `model` (Required)
  - **Type**: Voices
  - **Description**: The type of model voice you want, mentioned above
- **Field**: `url` (Required only when model is `CUSTOM`)
  - **Type**: URL
  - **Description**: URL of the custom model source

## Here is an example how to use DevMind's Voice
+++ Python
```python
import requests
import json

headers = {
    'Authorization': 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}
payload = {
    'song': 'https://devmind.thedevs.org/something.mp3',
    'model': 'Trump'
}

response = requests.post('https://devmind.thedevs.org/voice', json=payload, headers=headers)

print(response.json())
```
+++Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};
const payload = {
    song: "https://devmind.thedevs.org/something.mp3",
    model: "Trump"
};

axios.post('https://devmind.thedevs.org/voice', payload, { headers })
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
    let url = "https://devmind.thedevs.org/voice";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];
    let payload = json!({
        "song": "https://devmind.thedevs.org/something.mp3",
        "model": "Trump"
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
        String url = "https://devmind.thedevs.org/voice";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");
        con.setRequestMethod("POST");
        con.setRequestProperty("Content-Type", "application/json");

        // Set payload
        String payload = new Gson().toJson(Map.of(
            "song", "https://devmind.thedevs.org/something.mp3",
            "model", "Trump"
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
"Audio URL"
```

## Example Audio
[!embed](/Public/img/voice.mp3)