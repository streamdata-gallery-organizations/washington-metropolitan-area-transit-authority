{
  "info": {
    "name": "WMATA Real-Time Bus Predictions Get Predictions",
    "_postman_id": "38dc255b-1029-404c-98a4-c9c68da48d64",
    "description": "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction, but a different value for the same\r\nroute signifies that the buses are traveling in opposite\r\ndirections. Use the DirectionText element to show the actual\r\ndestination of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly description of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase route name as shown on the bus. This can be used in other\r\nbus-related methods. Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1 and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier. This can be correlated with the data in our\r\nbus schedule information as well as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This can be correlated with results returned\r\nfrom bus positions.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Predictions",
      "item": [
        {
          "id": "b9c243f9-de41-4844-ba3b-341f8ce6604e",
          "name": "Predictions.get",
          "request": {
            "url": "http://api.wmata.com/NextBusService.svc/Predictions?StopID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction, but a different value for the same\r\nroute signifies that the buses are traveling in opposite\r\ndirections. Use the DirectionText element to show the actual\r\ndestination of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly description of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase route name as shown on the bus. This can be used in other\r\nbus-related methods. Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1 and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier. This can be correlated with the data in our\r\nbus schedule information as well as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This can be correlated with results returned\r\nfrom bus positions."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4e9df72e-1cf1-4ded-9842-9f831e06e9ea"
            }
          ]
        }
      ]
    }
  ]
}