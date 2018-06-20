{
  "info": {
    "name": "WMATA Bus Route and Stop Methods JSON - Stop Search",
    "_postman_id": "5cdd3d06-c2cb-4994-8abd-a1300590cb70",
    "description": "Description\r\n\r\nReturns a list of nearby bus stops based on latitude, longitude, and radius.\r\nOmit all parameters to retrieve a list of all stops.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray containing stop information (Stop).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString array of route variants which provide service at this\r\nstop. Note that these are not date-specific; any route variant\r\nwhich stops at this stop on any day will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or NULL.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Buses",
      "item": [
        {
          "id": "75ab4054-1341-4c27-9bb3-a39cfafb6803",
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
              "id": "30a74a55-f180-4c4f-9359-d9d026583422"
            }
          ]
        },
        {
          "id": "590f581c-4e71-4dcc-80ce-955858e18297",
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
              "id": "f0224c1b-99c0-41c3-ac11-c2f4f68325e5"
            }
          ]
        },
        {
          "id": "3808d5a9-0768-4004-bad7-cdd729ba1145",
          "name": "5476362a281d830c946a3d6a",
          "request": {
            "url": "http://api.wmata.com/Bus.svc/json/jRoutes",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns a list of all bus route variants (patterns). For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique identifier for a given route variant. Can be used in\r\nvarious other bus-related methods.\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant’s grouping – lines are a combination of routes which lie in the same corridor and which have significant portions of their paths along the same roadways."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4a2386ac-6b49-41ca-ba9d-9f213b7a1f35"
            }
          ]
        },
        {
          "id": "c177ad0e-30d4-47e1-8824-978761219b1b",
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
              "id": "4493cc85-151a-4327-a9b6-46758b14b8cb"
            }
          ]
        },
        {
          "id": "1d270750-e381-4675-b1d5-c6a6e23057b8",
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
              "id": "010a81b5-b176-498c-bafc-6118936a01cd"
            }
          ]
        },
        {
          "id": "6aa39b01-084f-44d2-839a-0ea6c7a10cbd",
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
              "id": "5e167f90-00c1-4491-aa08-56a59996bb60"
            }
          ]
        }
      ]
    }
  ]
}