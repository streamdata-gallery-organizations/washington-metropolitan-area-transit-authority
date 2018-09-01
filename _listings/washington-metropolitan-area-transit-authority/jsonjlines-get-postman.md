{
  "info": {
    "name": "WMATA Rail Station Information JSON - Lines",
    "_postman_id": "ee7f1254-f8a2-479b-a8b1-336e4d783936",
    "description": "Description\r\n\r\nReturns information about all rail lines.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nLines\r\n\r\n\r\nArray containing line information (Line).\r\n\r\n\r\n\r\n\r\n\r\n\r\nLine Elements\r\n\r\n\r\n\r\n\r\n\r\nDisplayName\r\n\r\nFull name of line color.\r\n\r\n\r\n\r\nEndStationCode\r\n\r\nEnd station code. For example, will be E10 (Greenbelt) for the\r\nGreen Line, B11 (Glenmont) for the Red Line, etc. Use this value in\r\nother rail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\nInternalDestination1\r\n\r\nIntermediate terminal station code. During normal service, some\r\ntrains on some lines might end their trip prior to the\r\nStartStationCode or EndStationCode. A good example is on the Red\r\nLine where some trains stop at A11 (Grosvenor) or B08 (Silver\r\nSpring). Empty string if not defined.\r\n\r\n\r\n\r\nInternalDestination2\r\n\r\nSimilar to InternalDestination1.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV).\r\n\r\n\r\n\r\nStartStationCode\r\n\r\nStart station code. For example, will be F11 (Branch Avenue)\r\nfor the Green Line, A15 (Shady Grove) for the Red Line, etc. Use\r\nthis value in other rail-related APIs to retrieve data about a\r\nstation.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Transit",
      "item": [
        {
          "id": "9a198d59-a268-4a99-b92c-4b095774dd22",
          "name": "getJsonJlines",
          "request": {
            "url": "http://api.wmata.com/Rail.svc/json/jLines",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Description\r\n\r\nReturns information about all rail lines.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nLines\r\n\r\n\r\nArray containing line information (Line).\r\n\r\n\r\n\r\n\r\n\r\n\r\nLine Elements\r\n\r\n\r\n\r\n\r\n\r\nDisplayName\r\n\r\nFull name of line color.\r\n\r\n\r\n\r\nEndStationCode\r\n\r\nEnd station code. For example, will be E10 (Greenbelt) for the\r\nGreen Line, B11 (Glenmont) for the Red Line, etc. Use this value in\r\nother rail-related APIs to retrieve data about a station.\r\n\r\n\r\n\r\nInternalDestination1\r\n\r\nIntermediate terminal station code. During normal service, some\r\ntrains on some lines might end their trip prior to the\r\nStartStationCode or EndStationCode. A good example is on the Red\r\nLine where some trains stop at A11 (Grosvenor) or B08 (Silver\r\nSpring). Empty string if not defined.\r\n\r\n\r\n\r\nInternalDestination2\r\n\r\nSimilar to InternalDestination1.\r\n\r\n\r\n\r\nLineCode\r\n\r\nTwo-letter abbreviation for the line (e.g.: RD, BL, YL, OR, GR,\r\nor SV).\r\n\r\n\r\n\r\nStartStationCode\r\n\r\nStart station code. For example, will be F11 (Branch Avenue)\r\nfor the Green Line, A15 (Shady Grove) for the Red Line, etc. Use\r\nthis value in other rail-related APIs to retrieve data about a\r\nstation."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "dd2b1725-1dfb-4f21-8a91-d6129d3b3c47"
            }
          ]
        }
      ]
    }
  ]
}