# Endpoint: Active Components List

**Description:**  
Returns a list of enabled (active) components for your OSSN installation.

---

## Endpoint

`https://www.mywebsite.com/api/v2.0/components/list_enabled`

## Methods

- `GET`
- `POST`

## Usage Example

### GET request

```http
GET https://www.mywebsite.com/api/v2.0/components/list_enabled?api_key=YOUR_API_KEY
```

### POST request

```http
POST https://www.mywebsite.com/api/v2.0/components/list_enabled
Content-Type: application/x-www-form-urlencoded

api_key=YOUR_API_KEY
```

## Response

- Returns a JSON array or object listing all enabled components.

---

## Notes

- You must include your API key as a parameter.
- This endpoint helps verify which OSSN components are currently active/enabled.

---

[← Back to API Overview](../overview.md)
