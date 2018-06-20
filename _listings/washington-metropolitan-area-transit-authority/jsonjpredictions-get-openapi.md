---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 0
info:
  title: WMATA Real-Time Bus Predictions Get Predictions
  description: "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray
    containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull
    name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
    a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction,
    but a different value for the same\r\nroute signifies that the buses are traveling
    in opposite\r\ndirections. Use the DirectionText element to show the actual\r\ndestination
    of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly description
    of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes
    until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase
    route name as shown on the bus. This can be used in other\r\nbus-related methods.
    Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1
    and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier.
    This can be correlated with the data in our\r\nbus schedule information as well
    as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This can be
    correlated with results returned\r\nfrom bus positions."
  version: "1.0"
host: api.wmata.com
basePath: /NextBusService.svc
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /Predictions:
    get:
      summary: Get Predictions
      description: "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse
        Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray
        containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull
        name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
        a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to
        direction, but a different value for the same\r\nroute signifies that the
        buses are traveling in opposite\r\ndirections. Use the DirectionText element
        to show the actual\r\ndestination of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly
        description of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes
        until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase
        route name as shown on the bus. This can be used in other\r\nbus-related methods.
        Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1
        and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier.
        This can be correlated with the data in our\r\nbus schedule information as
        well as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This
        can be correlated with results returned\r\nfrom bus positions."
      operationId: Predictions.get
      x-api-path-slug: predictions-get
      parameters:
      - in: query
        name: StopID
        description: 7-digit regional stop ID
      responses:
        200:
          description: OK
      tags:
      - Predictions
  /json/jPredictions:
    get:
      summary: Get Predictions
      description: "Description\r\n\r\nReturns next bus arrival times at a stop.\r\n\r\nResponse
        Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nPredictions\r\n\r\n\r\nArray
        containing bus predictions (NextBusPrediction).\r\n\r\n\r\n\r\n\r\nStopName\r\n\r\nFull
        name of the given StopID.\r\n\r\n\r\n\r\n\r\n\r\nNextBusPrediction Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes
        a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to
        direction, but a different value for the same\r\nroute signifies that the
        buses are traveling in opposite\r\ndirections. Use the DirectionText element
        to show the actual\r\ndestination of the bus.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nCustomer-friendly
        description of direction and destination for\r\na bus.\r\n\r\n\r\n\r\nMinutes\r\n\r\nMinutes
        until bus arrival at this stop. Numeric value.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBase
        route name as shown on the bus. This can be used in other\r\nbus-related methods.
        Note that all variants will be shown as their\r\nbase route names (i.e.: 10Av1
        and 10Av2 will be shown as 10A).\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier.
        This can be correlated with the data in our\r\nbus schedule information as
        well as bus positions.\r\n\r\n\r\n\r\nVehicleID\r\n\r\nBus identifier. This
        can be correlated with results returned\r\nfrom bus positions."
      operationId: json.jPredictions.get
      x-api-path-slug: jsonjpredictions-get
      parameters:
      - in: query
        name: StopID
        description: 7-digit regional stop ID
      responses:
        200:
          description: OK
      tags:
      - Predictions
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---