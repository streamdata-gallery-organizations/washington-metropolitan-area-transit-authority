{
  "info": {
    "name": "WMATA Bus Route and Stop Methods XML - Routes",
    "_postman_id": "5d604111-6dfb-4a7c-a1ff-0245c2278cb7",
    "description": "Description\r\n\r\nReturns a list of all bus route variants (patterns). For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique identifier for a given route variant. Can be used in\r\nvarious other bus-related methods.\r\n\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant???s grouping ??? lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Buses",
      "item": [
        {
          "id": "3f2bb8b4-ee64-41e4-bb7f-3de484b4373f",
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
              "id": "1d113520-3782-4bb4-9220-a6872a248600"
            }
          ]
        },
        {
          "id": "4a545c74-6505-4736-a108-c543512ce6a6",
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
              "id": "87d4dcc2-b2ab-424d-a494-d52915589790"
            }
          ]
        },
        {
          "id": "b82df0eb-b2e1-4959-b0bd-f27ca1af4a6a",
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
              "id": "8bec260e-ddbe-4975-994a-1ed012483387"
            }
          ]
        },
        {
          "id": "b98adf53-1a8e-40c8-90d5-eb3f5d8b3cae",
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
              "id": "505b1dc7-006b-4678-a846-aa33c434e4ee"
            }
          ]
        },
        {
          "id": "58a8f444-fecb-4336-8bce-3b1caca7f8d7",
          "name": "5476362a281d830c946a3d6c",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jStopSchedule?Date=%7B%7D&StopID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a set of buses scheduled at a stop for a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrivals\r\n\r\n\r\nArray containing scheduled arrival information (ScheduleArrival).\r\n\r\n\r\n\r\n\r\nStop\r\n\r\n\r\nStructure describing stop information.\r\n\r\n\r\n\r\n\r\n\r\n\r\nScheduleArrival Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDenotes a binary direction (0 or 1) of the bus. There is no\r\nspecific mapping to direction, but a different value for the same\r\nroute signifies that the buses are traveling in opposite\r\ndirections. Use the TripDirectionText element to show the actual\r\ndestination of the bus.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant identifier (pattern). This variant can be\r\nused in several other bus methods which accept variants. Note that\r\ncustomers will never see anything other than the base route name,\r\nso variants 10A, 10Av1, 10Av2, etc. will be displayed as 10A on the\r\nbus.\r\n\r\n\r\n\r\nScheduleTime\r\n\r\nDate and time (Eastern Standard Time) when the bus is scheduled\r\nto stop at this location. Will be in YYYY-MM-DDTHH:mm:ss format\r\n(e.g.: 2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral direction of the trip (e.g.: NORTH, SOUTH, EAST,\r\nWEST).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDestination of the bus.\r\n\r\n\r\n\r\nTripID\r\n\r\nTrip identifier. This can be correlated with the data in our\r\nbus schedule information as well as bus positions.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e1629c3f-7dae-4f68-a403-e97a2b7bce78"
            }
          ]
        },
        {
          "id": "055d0282-023d-4e06-87d3-a69de8e4ca57",
          "name": "5476362a281d830c946a3d6d",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jStops?Lat=%7B%7D&Lon=%7B%7D&Radius=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of nearby bus stops based on latitude, longitude, and radius.\r\nOmit all parameters to retrieve a list of all stops.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e6c0195a-e363-4ba1-9b0a-4c1dfea79479"
            }
          ]
        },
        {
          "id": "501fb210-2a29-440b-814c-a52fd31eaad9",
          "name": "5476362a281d830c946a3d6e",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/BusPositions?Lat=%7B%7D&Lon=%7B%7D&Radius=%7B%7D&RouteID=%7B%7D",
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
              "id": "297699c8-8897-4923-a5a2-708032e76eae"
            }
          ]
        },
        {
          "id": "5c10ffaa-c40e-471b-ac0f-1dc9587300b9",
          "name": "5476362a281d830c946a3d6f",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/RouteDetails?Date=%7B%7D&RouteID=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\nFor a given date, returns the set of ordered latitude/longitude points along route variant along with the list of stops served.\r\nResponse Elements\r\n\r\n\r\n\r\nElement\r\nDescription\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\nStructures describing path/stopinformation.\r\n\r\nMost routes will return content in both Direction0 and Direction1 elements, though a few will return NULL for Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to direction, but a different value for the same route signifies that the route is in an opposite direction.\r\n\r\n\r\n\r\nName\r\nDescriptive name for the route.\r\n\r\n\r\nRouteID\r\nBus route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\nDirection0/Direction1 Elements\r\n\r\n\r\n\r\n\r\nDirectionNum\r\nDeprecated. Use the DirectionText element to denote the general direction of the route variant.\r\n\r\n\r\nDirectionText\r\nGeneral direction of the route variant (NORTH, SOUTH, EAST, WEST, LOOP, etc.).\r\n\r\n\r\nShape\r\n\r\nArray containing shape point information (ShapePoint).\r\n\r\n\r\n\r\nStops\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\nTripHeadsign\r\nDescriptive text of where the bus is headed. This is similar, but not necessarily identical, to what is displayed on the bus.\r\n\r\n\r\n\r\n\r\nShapePoint Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nSeqNum\r\nOrder of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n \r\nStop Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nName\r\nStop name. May be slightly different from what is spoken or displayed in the bus.\r\n\r\n\r\nRoutes\r\nString array of route variants which provide service at this stop. Note that these are not date-specific; any route variant which stops at this stop on any day will be listed.\r\n\r\n\r\nStopID\r\n7-digit regional ID which can be used in various bus-related methods. If unavailable, the StopID will be 0 or NULL."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "bc49af68-16bc-449b-8159-5adc3963f052"
            }
          ]
        },
        {
          "id": "5022b1d5-0607-41ba-8a5f-23ebf047b6c7",
          "name": "5476362a281d830c946a3d70",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/Routes",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of all bus route variants (patterns). For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique identifier for a given route variant. Can be used in\r\nvarious other bus-related methods.\r\n\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant???s grouping ??? lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b382d328-f971-49e2-a179-d5e1b2606f87"
            }
          ]
        }
      ]
    }
  ]
}