# Brands API Testing with Postman

## Description

This project automates API testing for the Brands endpoint of the Toolshop demo application (https://api.practicesoftwaretesting.com).
It uses Postman to perform all CRUD operations on the Brand resource. Tests validate that POST, GET, PUT, DELETE methods behave as expected, including checking HTTP status codes and response data. JSON schema validation ensures the response structure and data types match the defined requirements. The suite includes: positive and negative scenarios to cover edge cases, error handling.

## Prerequisites

Postman (v11+) + environment with `baseURL`
Node.js v18+
Newman CLI (`npm install -g newman`)

## Quick Start

newman run collections/ToolshopAPI.postman_collection.json -e environment/dev.json

## Folder Structure
/
├── collections/

  		└── BrandAPI.postman_collection.json    ...# Postman collection for Brands tests

├── environments/

		└── BrandAPI.postman_environment.json  	...# Postman environment (baseURL)

├── schemas/

		└── brandSchema.json                    ...# JSON schema for Brand resource // will be added

├── README.md                          		   	...# Documentation (this file)

├── CONTRIBUTING.md                   	    	...# Guidelines on how to contribute

├── .gitignore                          	   ... # Git ignore rules
	
## Test Strategy

- **CRUD & End-to-End flows:** POST→GET→PUT→DELETE sequences  
- **Schema:** `brandSchema.json` requirements checks        // will be added
- **Pos/Neg cases:** missing fields or values, duplicates, error messages (all described error codes), not exist data (id, name, slug), max length value, without SSL, invalid data format (symbol, integer), not well formed JSON format
- **Assumptions:** in case endpoint behavior was not described (e.g. max length fields value), reasonable assumptions were made and documented in test script comments. The tests can be updated if the API specification changes.
- **Performance** (Load testing with >100 RPS) and **Security** testing will be added in the future

## Contributing
See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on how to contribute.

## Known Issues

- No auth; demo only  
- Not described in swagger API behaviors were assumed and documented in the test scripts
- There is no info in swagger about response time, but on average the response time is less than 1000ms, so in my tests I check exactly this time
