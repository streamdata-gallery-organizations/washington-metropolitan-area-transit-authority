{
  "info": {
    "name": "WMATA Bus Route and Stop Methods XML - Schedule",
    "_postman_id": "3153d071-caee-4dfd-8fab-ee230b8fd9a2",
    "description": "Description\r\n\r\nReturns schedules for a given route variant for a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays containing trip information (Trip).\r\n\r\nMost routes will return content in both Direction0 and\r\nDirection1 elements, though a few (especially ones which run in\r\na loop, such as the U8) will return content only for Direction0\r\nand NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated. Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive text of where the bus is headed. This is similar,\r\nbut not necessarily identical, to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID. This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Buses",
      "item": [
        {
          "id": "fd47d999-e500-47bb-8ddf-378bfd471b24",
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
              "id": "5aee508b-d12b-4388-9f5c-0102496f411b"
            }
          ]
        },
        {
          "id": "d8792e4a-f5ca-457c-908d-45959376b9cb",
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
              "id": "5616b8c5-de78-40f7-8d5c-792846a27883"
            }
          ]
        },
        {
          "id": "776400ea-e747-40a8-94b9-114697f3ec46",
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
              "id": "84ab2b68-3445-4adb-b9a1-87931e43ae74"
            }
          ]
        },
        {
          "id": "d34dd7f6-0c5e-4a5f-901b-ffed65c8713e",
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
              "id": "92d2f7a0-79da-42ca-9f91-b45f8da9cf63"
            }
          ]
        },
        {
          "id": "bc654f3a-b13a-459d-a31c-5c3bde818828",
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
              "id": "e8c0b5fa-82cf-48bf-aecf-67396f4d6c39"
            }
          ]
        },
        {
          "id": "cb3d6c52-b432-4a46-bd92-9331d18e0967",
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
              "id": "9e1fb64b-9661-4e84-b392-821d7774a8e8"
            }
          ]
        },
        {
          "id": "40f50781-d0cc-49bf-8516-e637a34e9e98",
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
              "id": "02675bc4-b8b7-4860-9445-7c1ecf92f5cc"
            }
          ]
        },
        {
          "id": "126ce3cd-085b-4796-9b35-c20c537404f0",
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
              "id": "daefb612-60f3-45cb-a000-dca15b479ed4"
            }
          ]
        },
        {
          "id": "6d750d94-9f49-4b46-8933-b33ef858e9a7",
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
              "id": "3f958f43-f7aa-4506-b8e0-91936db243fb"
            }
          ]
        },
        {
          "id": "48fc1673-96eb-4928-a671-89f8720035ab",
          "name": "5476362a281d830c946a3d71",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/RouteSchedule?Date=%7B%7D&IncludingVariations=%7B%7D&RouteID=%7B%7D",
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
              "id": "d03494b6-8460-43ce-b9a4-fdf7bd78324d"
            }
          ]
        }
      ]
    }
  ]
}