---
icon: rocket
order: 2
---
# Get Started

!!!info Base URL
!!!
```js
devmind.thedevs.org
```

### Requirements

- **Auth Key**

### Lets build up a quick request to test the API!
+++ Python
```python
import request
import json

headers={
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
}

response = request.get('https://devmind.thedevs.org/get', headers=headers)
print(response.json())
```
+++ Node Js
```js
const axios = require('axios');

const headers = {
  Authorization: 'theDevs_xxxxxxxxxxxxxxxxxxxx'
};

axios.get('https://devmind.thedevs.org/get', { headers })
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
    let url = "https://devmind.thedevs.org/get";
    let headers = [("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx")];

    let response = reqwest::Client::new()
        .get(url)
        .headers(headers)
        .send()
        .await?;

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
import java.io.InputStreamReader;

public class HttpRequestExample {
    public static void main(String[] args) throws Exception {
        String url = "https://devmind.thedevs.org/get";
        URL obj = new URL(url);
        HttpURLConnection con = (HttpURLConnection) obj.openConnection();

        // Set request header
        con.setRequestProperty("Authorization", "theDevs_xxxxxxxxxxxxxxxxxxxx");

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

Response
```js
{
  "_id": "6577633846976d3e0400c3d7",
  "api_key": "theDevs_xxxxxxxxxxxxxxxxxxxx",
  "limit": 1000,
  "llmconfig": null,
  "plan": "free",
  "usage": 0,
  "username": "The Devs"
}
```
