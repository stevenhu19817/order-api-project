# Order API Project

## Overview

This project implements a RESTful API for handling hotel booking orders. It provides an endpoint for creating new orders with specific JSON input format and performs various validations and transformations on the input data.

## Features

- POST endpoint at `/api/orders` for creating new orders
- JSON input validation and transformation
- Detailed error handling and reporting
- SOLID principles implementation
- Design patterns implementation

## Technology Stack

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![Django REST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)

## API Documentation

### Create Order

- **URL**: `/api/orders`
- **Method**: POST
- **Content-Type**: application/json

#### Input Format

```json
{
  "id": "A0000001",
  "name": "Melody Holiday Inn",
  "address": {
    "city": "taipei-city",
    "district": "da-an-district",
    "street": "fuxing-south-road"
  },
  "price": "2050",
  "currency": "TWD"
}
```

#### Input Validation Rules

1. `name`: Must only contain English characters and have each first letter capitalized
2. `price`: Must be a number less than 2000
3. `currency`: Must be either **TWD** or **USD**
   If currency is **USD**, multiply price by 31 and change currency to **TWD**.

### Response

The API will return appropriate status codes and error messages based on the validation results.

## Setup and Usage

### Prerequisites

- Docker and Docker Compose installed on your system

### Running the Application

1. Clone the repository:
   ```
   git clone https://github.com/stevenhu19817/order-api-project.git
   ```

2. Build and run the Docker containers:
   ```
   docker-compose up --build -d
   ```

3. The API will be available at `http://localhost:8000/api/orders`

## Testing

To run the tests, use the following command:

```
docker-compose exec web python manage.py test
```
