# Airdrop API Documentation

## Overview
The Airdrop API provides access to a list of all available airdrops. Users can retrieve data about these airdrops by making a GET request to the specified endpoint. The API requires an API key for authentication. You can get an API key from Zloadr at https://zloadr.com

## Endpoint

### Get All Airdrops

- **URL:** `https://zloadr.com/paid_api/airdrop/all.php?api_key=****`
- **Method:** `GET`
- **Description:** Returns a list of all airdrops currently available.

## Example Request
```http
GET /airdrop/all.php?api_key=**** HTTP/1.1
Host: (https://zloadr.com/paid_api/)
```

## Example Responses

### Success Response (Status: 200 OK)
**Example:**
```json
{
    "status": {
        "timestamp": "2024-07-28 12:34:56",
        "error_code": 0,
        "error_message": "",
        "credit_count": "5249",
        "valid_till": "2024-08-28"
    },
    "data": {
        "airdrops": [
            {
                "id": "1",
                "title": "Sample Airdrop",
                "description": "Description of the airdrop",
                "start_date": "2024-07-01",
                "end_date": "2024-08-01"
            }
        ]
    }
}
```

### Error Response (Status: 400 Bad Request)
**Example:**
```json
{
    "status": {
        "timestamp": "2024-07-28 12:34:56",
        "error_code": 400,
        "error_message": "Invalid request.",
        "credit_count": 0
    }
}
```

## Details

### Input Attributes
- **None**: This endpoint does not require any additional input attributes beyond the API key.

### Output Attributes
- **data** (Required): Contains a list of airdrops.
  - **airdrops**: An array of airdrop objects.
    - **id**: Unique identifier for the airdrop.
    - **title**: Title of the airdrop.
    - **description**: A brief description of the airdrop.
    - **start_date**: The start date of the airdrop.
    - **end_date**: The end date of the airdrop.
- **status** (Required): Metadata about the response.
  - **timestamp**: The time the response was generated.
  - **error_code**: Numeric code indicating success or the type of error.
  - **error_message**: Message providing details on the error, if any.
  - **credit_count**: Number of credits remaining.
  - **valid_till**: The expiration date of the current API key.

## Response Codes
- **200**: Successful request, returning data as specified.
- **400**: Bad request, typically due to invalid input or missing parameters.
- **401**: Unauthorized, indicating an invalid API key.
- **404**: Not Found, the requested resource was not found.
- **406**: Not Acceptable, the requested format is not supported.
- **409**: Conflict, indicating a conflict that prevents processing.
- **422**: Unprocessable Entity, indicating the server understands the request but cannot process it.

## Additional Information
To access the API, ensure you include the correct API key in your request URL. If you encounter any issues or errors, refer to the `status` object in the response for more details. For comprehensive API usage guidelines, please consult the official [API Documentation](https://zloadr.com/paid_api/docs).
`
