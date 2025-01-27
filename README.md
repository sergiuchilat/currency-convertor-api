# Currency Conversion API Documentation

## Overview
The Currency Conversion API provides endpoints for retrieving exchange rates, converting currency amounts, and accessing the list of available currencies. This API is designed for ease of integration, scalability, and reliability.

---

## User Stories

1. **As a User**, I want to retrieve the exchange rate between two currencies so that I can see the current conversion rate.
2. **As a User**, I want to convert an amount from one currency to another so that I can determine the equivalent value in a different currency.
3. **As a User**, I want to fetch a list of all supported currencies so that I know which currencies are available for conversion.

---

## Endpoints

### 1. **Get Exchange Rate**
- **URL**: `/rate`
- **Method**: `GET`
- **Query Parameters**:
| Parameter | Type   | Required | Description                     |
|-----------|--------|----------|---------------------------------|
| `from`    | string | Yes      | The base currency (e.g., `USD`). |
| `to`      | string | Yes      | The target currency (e.g., `EUR`). |
- **Response**:
  ```json
  {
    "from": "USD",
    "to": "EUR",
    "rate": 0.9123
  }


## 2. Convert Currency

### **Description**
This endpoint allows users to convert an amount from one currency to another using the latest exchange rates.

### **Endpoint**
- **URL**: `/convert`
- **Method**: `GET`

### **Query Parameters**
| Parameter | Type   | Required | Description                     |
|-----------|--------|----------|---------------------------------|
| `from`    | string | Yes      | The base currency (e.g., `USD`). |
| `to`      | string | Yes      | The target currency (e.g., `EUR`). |
| `amount`  | float  | Yes      | The amount to convert.          |

### **Response**
The API will return the converted amount along with the input details.

#### **Example Response**
```json
{
  "from": "USD",
  "to": "EUR",
  "amount": 100,
  "converted_amount": 91.23
}
```

### 3. **List Supported Currencies**
- **URL**: `/currencies`
- **Method**: `GET`
- **Description**: Retrieves a list of all supported currencies along with their full names.

#### **Response**:
```json
{
  "currencies": {
    "USD": "United States Dollar",
    "EUR": "Euro",
    "JPY": "Japanese Yen",
    "GBP": "British Pound Sterling"
  }
}
