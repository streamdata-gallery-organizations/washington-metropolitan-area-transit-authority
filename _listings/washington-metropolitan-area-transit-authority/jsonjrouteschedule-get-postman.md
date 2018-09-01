{
  "info": {
    "name": "WMATA Bus Route and Stop Methods JSON - Schedule",
    "_postman_id": "74de53b5-18f8-4593-b95d-7a0eff8f71e2",
    "description": "Description\r\n\r\nReturns schedules for a given route variant for a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays containing trip information (Trip).\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few (especially ones which run in\r\na loop, such as the U8) will return content only for Direction0\r\nand NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID. This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Buses",
      "item": [
        {
          "id": "baaa53ed-4eed-408d-8134-dea37f986168",
          "name": "5476362a281d830c946a3d68",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jBusPositions?Lat=%7B%7D&Lon=%7B%7D&Radius=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\n\nReturns bus positions for the given route, with an optional search radius.\nIf no parameters are specified, all bus positions are returned.\n\nNote that the RouteID parameter accepts only base route names and no\nvariations, i.e.: use 10A instead of 10Av1 or 10Av2.\n\nBus positions are refreshed approximately every 20 to 30 7 to 10 seconds.\n\nResponse Elements\n\n\n\n\nElement\n\nDescription\n\n\n\n\n\nBusPositions\n\n\nArray containing bus position information (BusPositions).\n\n\n\n\n\n\nBusPosition\nElements\n\n\n\n\n\nDateTime\n\nDate and time (Eastern Standard Time) of last position update.\nWill be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T13:23:40).\n\n\n\nDeviation\n\nDeviation, in minutes, from schedule. Positive values indicate\nthat the bus is running late while negative ones are for buses\nrunning ahead of schedule.\n\n\n\nDirectionNum\n\nDeprecated. Use the\nDirectionText for a customer-friendly description of\ndirection.\n\n\n\nDirectionText\n\nGeneral direction of the trip, not the bus itself (e.g.: NORTH,\nSOUTH, EAST, WEST).\n\n\n\nLat\n\nLast reported Latitude of the bus.\n\n\n\nLon\n\nLast reported Longitude of the bus.\n\n\n\nRouteID\n\nBase route name as shown on the bus. Note that the base route\nname could also refer to any variant, so a RouteID of 10A could\nrefer to 10A, 10Av1, 10Av2, etc.\n\n\n\nTripEndTime\n\nScheduled end date and time (Eastern Standard Time) of the\nbus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T13:17:00).\n\n\n\nTripHeadsign\n\nDestination of the bus.\n\n\n\nTripID\n\nUnique trip ID. This can be correlated with the data returned\nfrom the schedule-related methods.\n\n\n\nTripStartTime\n\nScheduled start date and time (Eastern Standard Time) of the\nbus's current trip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\n2014-10-27T12:40:00).\n\n\n\nVehicleID\n\nUnique identifier for the bus. This is usually visible on the\nbus itself."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "c3f7413b-098d-4361-9a58-22d541061d71"
            }
          ]
        },
        {
          "id": "d6a51bc5-251e-4334-a648-5f560ef6e6e3",
          "name": "5476362a281d830c946a3d69",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jRouteDetails?Date=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nFor a given date, returns the set of ordered latitude/longitude points along\r\na route variant along with the list of stops served.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures describing path/stop\r\ninformation.\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few will return NULL for Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4408ce51-56d0-427d-a4fd-f4987276f8f9"
            }
          ]
        },
        {
          "id": "41a1acd5-d6b7-4cea-8bbc-8b02be637fbe",
          "name": "5476362a281d830c946a3d6a",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jRoutes",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of all bus route variants (patterns). For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique identifier for a given route variant. Can be used in\r\nvarious other bus-related methods.\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant???s grouping ??? lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b2ddb087-57fe-469c-b3e4-8c52ed58ce9a"
            }
          ]
        },
        {
          "id": "a4b77a3f-5887-4232-9096-3d6c0c791cc9",
          "name": "5476362a281d830c946a3d6b",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jRouteSchedule?Date=%7B%7D&IncludingVariations=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns schedules for a given route variant for a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays containing trip information (Trip).\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few (especially ones which run in\r\na loop, such as the U8) will return content only for Direction0\r\nand NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID. This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f3b570cf-e1c7-44c7-847e-cc901da6c875"
            }
          ]
        }
      ]
    }
  ]
}