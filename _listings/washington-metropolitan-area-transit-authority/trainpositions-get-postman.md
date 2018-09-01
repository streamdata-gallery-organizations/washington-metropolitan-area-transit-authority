{
  "info": {
    "name": "WMATA Train Positions Live Train Positions",
    "_postman_id": "3d84cf37-b54b-4060-8a9c-c34734099720",
    "description": "Description\n\nReturns uniquely identifiable trains in service and what track circuits they currently occupy. Will return an empty set of results when no positions are available.\n\nData is refreshed once every 7-10 seconds.\nPlease refer to this page for additional details.\n\nResponse Elements\n\n\n\n\nElement\n\nDescription\n\n\n\n\n\nTrainPositions\n\n\nArray containing train position information (TrainPosition).\n\n\n\n\n\n\nTrainPosition Elements\n\n\n\n\n\nCarCount\n\nNumber of cars.  Can sometimes be 0 when there is no data available.\n\n\n\nCircuitId\n\nThe circuit identifier the train is currently on.  This identifier can be referenced from the Standard Routes method.\n\n\n\nDestinationStationCode\n\nDestination station code. Can be NULL. Use this value in other rail-related APIs to retrieve data about a station.  Note that this value may sometimes differ from the destination station code returned by our Next Trains methods.\n\n\n\nDirectionNum\n\nThe direction of movement regardless of which track the train is on.  Valid values are 1 or 2.  Generally speaking, trains with direction 1 are northbound/eastbound, while trains with direction 2 are southbound/westbound.\n\n\n\nLineCode\n\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR, or SV). May also be NULL in certain cases.\n\n\n\nSecondsAtLocation\n\nApproximate \"dwell time\".  This is not an exact value, but can be used to determine how long a train has been reported at the same track circuit.\n\n\n\nServiceType\n\nService Type of a train, can be any of the following Service Types\n\n\n\nTrainId\n\nUniquely identifiable internal train identifier.\n\n\n\n\n\nService Types\n\n\n\n\n\nNoPassengers\n\nThis is a non-revenue train with no passengers on board.  Note that this designation of NoPassengers does not necessarily correlate with PIDS \"No Passengers\".  As of 08/22/2016, this functionality has been reinstated to include all non-revenue vehicles, with minor exceptions.\n\n\n\nNormal\n\nThis is a normal revenue service train.\n\n\n\nSpecial\n\nThis is a special revenue service train with an unspecified line and destination.  This is more prevalent during scheduled track work.\n\n\n\nUnknown\n\nThis often denotes cases with unknown data or work vehicles.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "88b65844-9bce-4681-ac54-3e66b594f565",
          "name": "getTrainpositions",
          "request": {
            "url": "http://api.wmata.com/TrainPositions/TrainPositions?contentType=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\n\nReturns uniquely identifiable trains in service and what track circuits they currently occupy. Will return an empty set of results when no positions are available.\n\nData is refreshed once every 7-10 seconds.\nPlease refer to this page for additional details.\n\nResponse Elements\n\n\n\n\nElement\n\nDescription\n\n\n\n\n\nTrainPositions\n\n\nArray containing train position information (TrainPosition).\n\n\n\n\n\n\nTrainPosition Elements\n\n\n\n\n\nCarCount\n\nNumber of cars.  Can sometimes be 0 when there is no data available.\n\n\n\nCircuitId\n\nThe circuit identifier the train is currently on.  This identifier can be referenced from the Standard Routes method.\n\n\n\nDestinationStationCode\n\nDestination station code. Can be NULL. Use this value in other rail-related APIs to retrieve data about a station.  Note that this value may sometimes differ from the destination station code returned by our Next Trains methods.\n\n\n\nDirectionNum\n\nThe direction of movement regardless of which track the train is on.  Valid values are 1 or 2.  Generally speaking, trains with direction 1 are northbound/eastbound, while trains with direction 2 are southbound/westbound.\n\n\n\nLineCode\n\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR, or SV). May also be NULL in certain cases.\n\n\n\nSecondsAtLocation\n\nApproximate \"dwell time\".  This is not an exact value, but can be used to determine how long a train has been reported at the same track circuit.\n\n\n\nServiceType\n\nService Type of a train, can be any of the following Service Types\n\n\n\nTrainId\n\nUniquely identifiable internal train identifier.\n\n\n\n\n\nService Types\n\n\n\n\n\nNoPassengers\n\nThis is a non-revenue train with no passengers on board.  Note that this designation of NoPassengers does not necessarily correlate with PIDS \"No Passengers\".  As of 08/22/2016, this functionality has been reinstated to include all non-revenue vehicles, with minor exceptions.\n\n\n\nNormal\n\nThis is a normal revenue service train.\n\n\n\nSpecial\n\nThis is a special revenue service train with an unspecified line and destination.  This is more prevalent during scheduled track work.\n\n\n\nUnknown\n\nThis often denotes cases with unknown data or work vehicles."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "00d4614d-2835-46af-8b02-52bf93e183c2"
            }
          ]
        }
      ]
    }
  ]
}