# Cricbuzz Microservices

This project provides a microservices architecture for retrieving information about cricket series, matches, and related details. The application is divided into two services: one for domestic cricket series and another for international cricket series. Additionally, a Eureka Server is used for service discovery.

## Overview

The microservices offer endpoints to fetch cricket series categorized as domestic and international matches.

- Domestic Service: [http://localhost:8081/series/domestic](http://localhost:8081/series/domestic)
- International Service: [http://localhost:8082/series/international](http://localhost:8082/series/international)

Eureka Server: [http://localhost:8761](http://localhost:8761)

## Technologies Used

- Java
- Spring Boot
- MongoDB
- Gradle
- Eureka Server

## Setup Instructions

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Gaurang135/cricbuzz-api-microservices
    cd cricbuzz-api
    ```

2. **Run the Eureka Server:**

    ```bash
    cd ServerRegistry
    gradle bootRun
    ```

   Access the Eureka Server: [http://localhost:8761](http://localhost:8761)

3. **Run the Domestic Service:**

    ```bash
    cd cricbuzz-api - Domestic
    gradle bootRun
    ```

   Access the Domestic Service: [http://localhost:8081/series/domestic](http://localhost:8081/series/domestic)

4. **Run the International Service:**

    ```bash
    cd cricbuzz-api - International
    gradle bootRun
    ```

   Access the International Service: [http://localhost:8082/series/international](http://localhost:8082/series/international)

## API Responses

### Domestic Service

- **HTTP Method**: GET
- **Description**: Retrieve a list of domestic cricket series.
- **Response Codes**:
    - `200 OK`: Successfully retrieved the list of domestic series.
    - `204 No Content`: No domestic series available.
- **Sample Response**:

    ```json
    [
        {
            "seriesName": "IPL 2023",
            "region": "DOMESTIC",
            "matches": [
                {
                    "team1": {
                        "teamName": "Mumbai Indians",
                        "score": 180,
                        "wickets": 6,
                        "overs": 18.0
                    },
                    "team2": {
                        "teamName": "Chennai Super Kings",
                        "score": 160,
                        "wickets": 8,
                        "overs": 20.0
                    },
                    "matchNumber": 1,
                    "status": "DECLARED",
                    "schedule": {
                        "date": "2023-12-05",
                        "location": "Wankhede Stadium, Mumbai"
                    }
                }
                
            ]
        }
    ]
    ```

### International Service

- **HTTP Method**: GET
- **Description**: Retrieve a list of international cricket series.
- **Response Codes**:
    - `200 OK`: Successfully retrieved the list of international series.
    - `204 No Content`: No international series available.
- **Sample Response**:

    ```json
    [
        {
            "seriesName": "Test Series 2023",
            "region": "INTERNATIONAL",
            "matches": [
                {
                    "team1": {
                        "teamName": "India",
                        "score": 300,
                        "wickets": 7,
                        "overs": 80.0
                    },
                    "team2": {
                        "teamName": "Australia",
                        "score": 320,
                        "wickets": 5,
                        "overs": 85.0
                    },
                    "matchNumber": 1,
                    "status": "DECLARED",
                    "schedule": {
                        "date": "2023-12-10",
                        "location": "Sydney Cricket Ground"
                    }
                }
                
            ]
        }
    ]
    ```

## Contribution

Contributions are welcome! Feel free to raise issues or submit pull requests for any improvements or additional features.