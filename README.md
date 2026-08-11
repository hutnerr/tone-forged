> This project is no longer maintained.

## Overview
ToneForged is a public API that converts text into specific lingos. For example, using the "Pirate" lingo, it might convert:

Hello, Friend → Ahoy Matey!

It is built with **Spring Boot**, hosted on **AWS**, and uses the **Gemini API** for language conversion.

## Usage

Send a request to the API:

> `POST http://52.207.146.61/api/convert`

Content-Type: application/json

```json
{
    "strategy": "Pirate",
    "text": "Hello, Friend"
}
```

The response will be JSON:
```json
{
    "original": "Hello, Friend",
    "converted": "Ahoy Matey!",
    "lingo": "Pirate",
    "error": null
}
```

Below is a simple JavaScript example.

```js
const response = await fetch(`http://52.207.146.61/api/convert`, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ strategy, text })
});
```

## Endpoints

> `http://52.207.146.61/api/...`

| Endpoint              | Method | Description                              |
|-----------------------|--------|------------------------------------------|
| `/convert`        | POST   | Convert text to the specified lingo      |
| `/strategies`     | GET    | Returns a list of all available lingos/strategies     |
