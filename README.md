
# SensAi - The Next-Level AI
### (Powered by ScribbleX and DeepNight)

SensAi is a smart conversational AI built around GPT-2 and GPT-3.5 that can search the internet and also fetch real-time data to answer your queries.

![SensAi - by ScribbleX and DeepNight](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/sensai.png)
## What Can SensAi Do?

SensAi is built around a highly trained model of GPT-2 and GPT-3.5. It can carry conversations, search the web, and also fetch real-time data.

* __Hold Conversations__: SensAi is more than just an AI system - it's your ultimate conversational companion! With the ability to hold conversations and recall context, SensAi makes interactions with users more fluid and natural. Although this feature is not yet available, stay tuned as we're working tirelessly to bring this cutting-edge capability to you in the very near future. Get ready for a whole new level of conversational AI with SensAi!

* __Search the Web__: Say goodbye to vague or inaccurate responses - SensAi is here to provide you with the most reliable information available! Thanks to its advanced web search capabilities, SensAi can quickly and efficiently scour the internet for the most relevant references to provide accurate responses to your queries. With SensAi, you can trust that the information you receive is the most up-to-date and accurate available. Get ready to experience the power of SensAi's knowledge with its advanced web search feature!

* __Fetch Real-Time Data__: SensAi isn't your average AI - it's a real-time data wizard! Although it can currently only fetch time and weather data for any location, it's just the beginning of what it's capable of. Stay tuned as we continue to add more real-time data sources to SensAi's capabilities, making it your ultimate one-stop-shop for all the latest information you need!

* __Most Precise Calculation Results__: Get ready to experience the ultimate in accuracy with SensAi's built-in calculator! While even the most advanced AI systems can sometimes make mistakes in calculations, SensAi's precise and reliable calculator ensures that every answer it provides is absolutely spot-on. With SensAi, you can trust that you're getting the most accurate calculations possible, every time. Whether you're calculating complex equations or just need a quick answer, SensAi's calculator is the perfect tool for the job. Say goodbye to calculation errors and hello to the ultimate in accuracy with SensAi!

* __The Code Expert__: Unlock the true potential of your coding skills with SensAi! With support for multiple programming languages, including popular options like JavaScript, Python, C/C++, Java, Ruby, and PHP, SensAi is the ultimate coding companion. Not only can SensAi write code for you, but it can also explain code and prepare documentation, taking your coding skills to the next level. Whether you're a seasoned pro or just starting out, SensAi's multi-language support is the perfect tool to help you code smarter, faster, and more efficiently than ever before. Get ready to revolutionize the way you code with SensAi!
## What's on the way?

We are working constantly on making SensAi more advanced and adding more functionalities to it.

Some of the upcoming features are:
* __Generate Code Documentations__: Our team is hard at work perfecting SensAi's ability to create flawless documentation for your code. Whether you need to generate a ReadMe.md file for your GitHub repositories or create comprehensive documentation for your entire project, SensAi will have you covered.

* __Store Data in Files__: We're working on bringing the ability to store data in a variety of file formats, including .txt, .docx, .pdf, and .xlsx, SensAi will make it easier than ever to access the information you need, whenever you need it.

* __Updates in Real-Time Data Fetches__: SensAi is currently capable of fetching time and weather reports of a location. In near future, SensAi will be able to fetch a lot more real-time data like News, Stock Prices, Weather Forecasts, and a lot more.

* __Updates in Web Search__: Currently SensAi searches the web via [MediaWiki](https://www.mediawiki.org/wiki/MediaWiki) but we are working on making the web searches more advanced so that we can gather a lot more than just Wikis.
## API Reference

#### Get Output

```
  GET /v1
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `memory` | `string` | **Optional**. Memory ID of Conversation |
| `prompt` | `string` | **Required**. Your Query / Prompt |
| `limit` | `string` | **Optional**. Limit of the length of Output |

| Headers | Type | Description          |
| :------ | :--- | :------------------- |
| `Authorization` | `string` | **Required**. Your API key |
| `Content-Type`  | `string` | **Optional**. application/json |

Response:
```
    JSON:
    {   "response": "SENSAI_RESPONSE",
        "processes": TOTAL_PROCESSES_CONSUMED,
        "memory": "MEMORY_ID"   }
```
* "response" - this is the response from SensAi to your Query / Prompt
* "processes" - total number of processes consumed by SensAi to process your Query / Prompt
* "memory" - this is the memory id of the particular conversation. You can pass this ID in parameters while making the call to SensAi to carry a conversation.

#

#### Get Processes

```
  GET /process
```
This is to find out how many processes your prompt values. (This doesn't include the processes of your response.)

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `prompt`      | `string` | **Required**. Your Query / Prompt |


# 
## We have more end-points ready but not released yet. (Gonna be there soon!)
* Wikipedia Search - This will search for your query on Wikipedia and return the first paragraph (__Intro__). If a related topic can't be found, it will return null.

* Sens - Sens is our personally trained Model to detect sensitive content. We personally use **Sens** at two points.
    * When The user provides the prompt. Here we check the sensitivity of the user's prompt and if the content is against our policies, we rasie a violation error.
    * When SensAi returns the response. Here we make sure that content provided by SensAi is not harmful, sensitive, or controvertial in any way. 

# 

#### SensAi is not publically accessible yet. We have only released an Early Access Model. If you want to gain access to Early Access Model of SensAi please contact us at [SensAi.slx](mailto:sensai@scribblex.net?subject=Early%20Access%20Request)

#### SensAi is an Advanced AI system that can be implemented in your own applications to run certain commands. This works on text classification, recognition, and scenario generation and understandings. With this you can train SensAi to be implemented in your own application. For business queries, please [Email Us](mainto:info@scribblex.net).
## Implementation Examples

#### Python
![Python Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/python.png)
```Python
import requests
import json

url = "https://*********/v1"
headers = {
    "Content-Type": "application/json",
    "Authorization": "API_KEY"
}
data = {
    "Prompt": "YOUR_PROMPT",
    "Memory": "CONVERSATION_MEMORY_ID",
    "Limit": "MAX_OUTPUT_WORDS"
}

response = requests.post(url, headers=headers, data=json.dumps(data))
print(response.content)

```

#### PHP
![PHP Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/php.png)
```PHP
<?php
$url = "https://*********/v1";
$headers = array(
    "Content-Type: application/json",
    "Authorization: API_KEY"
);
$data = array(
    "Prompt" => "YOUR_PROMPT",
    "Memory" => "CONVERSATION_MEMORY_ID",
    "Limit" => "MAX_OUTPUT_WORDS"
);

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

echo $response;
?>
```

#### JavsScript
![JavaScript Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/javascript.png)
```Javascript
const url = "https://*********/v1";
const headers = {
    "Content-Type": "application/json",
    "Authorization": "API_KEY"
};
const data = {
    "Prompt": "YOUR_PROMPT",
    "Memory": "CONVERSATION_MEMORY_ID",
    "Limit": "MAX_OUTPUT_WORDS"
};

fetch(url, {
    method: "POST",
    headers: headers,
    body: JSON.stringify(data)
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error(error));
```

#### cURL
![cURL Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/curl.png)
```cURL
curl -X POST "https://*********/v1" \
-H "Content-Type: application/json" \
-H "Authorization: API_KEY" \
-d '{"Prompt":"YOUR_PROMPT","Memory":"CONVERSATION_MEMORY_ID","Limit":"MAX_OUTPUT_WORDS"}'
```

#### Ruby
![Ruby Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/ruby.png)
```Ruby
require "net/http"
require "uri"
require "json"

url = URI("https://*********/v1")
headers = {
    "Content-Type" => "application/json",
    "Authorization" => "API_KEY"
}
data = {
    "Prompt" => "YOUR_PROMPT",
    "Memory" => "CONVERSATION_MEMORY_ID",
    "Limit" => "MAX_OUTPUT_WORDS"
}

response = Net::HTTP.post(url, data.to_json, headers)
puts response.body
```

#### Perl
![Perl Example](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/perl.png)
```Perl
use LWP::UserAgent;
use JSON;

my $url = "https://*********/v1";
my $headers = {
    "Content-Type" => "application/json",
    "Authorization" => "API_KEY"
};
my $data = {
    "Prompt" => "YOUR_PROMPT",
    "Memory" => "CONVERSATION_MEMORY_ID",
    "Limit" => "MAX_OUTPUT_WORDS"
};

my $ua = LWP::UserAgent->new;
my $response = $ua->post(
    $url,
    Content_Type => "application/json",
    Content => encode_json($data),
    %$headers
);

print $response->decoded_content;
```
# Demo

<p align="center">
  <img src="https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/images/sensai-demo.gif" alt="Demo GIF"/>
</p>

## Feedback

If you have any feedback, please reach out to us at feedback@scribblex.net
## Authors

- [@kstyagi.23](https://github.com/kstyagi23)
- [@scribblex-SDA](https://github.com/scribbleX-SDA)

![Logo](https://raw.githubusercontent.com/scribbleX-SDA/SensAi/main/sensai.png)

