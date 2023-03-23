## Coding Task (Use NodeJS, ExpressJs)

## Your solution may contain unit tests.

#### Expose a POST endpoint which accepts an input JSON object with payload, referenceData and returns a transformedPayload (JSON).
##### The POST API should substitute the {REF_*} values in payload using refernceData and return the transformed payload.


#### Input payload to POST API
```JSON
{
  "payload": {
    "name": "subscriber",
    "valueType": "array",
    "value": [
      {
        "name": "MN",
        "valueType": "string",
        "value": "{REF_MSISDN}"
      },
      {
        "name": "IM",
        "valueType": "string",
        "value": "{REF_IMSI}"
      },
      {
        "name": "NT",
        "valueType": "string",
        "value": "G"
      },
      {
        "name": "privateUser",
        "valueType": "array",
        "value": [
          {
            "name": "privateUserId",
            "valueType": "string",
            "value": "{REF_IMSI}@ims.mnc001.mcc505.3gppnetwork.org"
          },
          {
            "name": "roamingAllowed",
            "valueType": "string",
            "value": "false"
          },
          {
            "name": "publicUser",
            "valueType": "array",
            "value": [
              {
                "name": "publicIdValue",
                "valueType": "string",
                "value": "sip:{REF_IMSI}@ims.mnc001.mcc505.3gppnetwork.org"
              },
              {
                "name": "implicitRegSet",
                "valueType": "string",
                "value": "1"
              },
              {
                "name": "serviceProfileId",
                "valueType": "string",
                "value": "{REF_SERVPROFID}"
              },
              {
                "name": "testUser",
                "valueType": "array",
                "value": [
                  {
                    "name": "testIdValue",
                    "valueType": "string",
                    "value": "sip:{REF_IMSI}@ims.mod-connect.com"
                  },
                  {
                    "name": "implicitRegSet",
                    "valueType": "string",
                    "value": "2"
                  }
                ]
              }
            ]
          },
          {
            "name": "userImsi",
            "valueType": "string",
            "value": "{REF_IMSI}"
          }
        ]
      },
      {
        "name": "PO",
        "valueType": "string",
        "value": "0"
      }
    ]
  },
  "referenceData": {
    "REF_MSISDN": "0406679321",
    "REF_IMSI": "50002312344314",
    "REF_SERVPROFID": "2"
  }
}
```

 
#### Expected API Response
 ```JSON
 {
   "name": "subscriber",
   "valueType": "array",
   "value": [
     {
       "name": "MN",
       "valueType": "string",
       "value": "0406679321"
     },
     {
       "name": "IM",
       "valueType": "string",
       "value": "50002312344314"
     },
     {
       "name": "NT",
       "valueType": "string",
       "value": "G"
     },
     {
       "name": "privateUser",
       "valueType": "array",
       "value": [
         {
           "name": "privateUserId",
           "valueType": "string",
           "value": "50002312344314@ims.mnc001.mcc505.3gppnetwork.org"
         },
         {
           "name": "roamingAllowed",
           "valueType": "string",
           "value": "false"
         },
         {
           "name": "publicUser",
           "valueType": "array",
           "value": [
             {
               "name": "publicIdValue",
               "valueType": "string",
               "value": "sip:50002312344314@ims.mnc001.mcc505.3gppnetwork.org"
             },
             {
               "name": "implicitRegSet",
               "valueType": "string",
               "value": "1"
             },
             {
               "name": "serviceProfileId",
               "valueType": "string",
               "value": "2"
             },
             {
               "name": "testUser",
               "valueType": "array",
               "value": [
                 {
                   "name": "testIdValue",
                   "valueType": "string",
                   "value": "sip:50002312344314@ims.mod-connect.com"
                 },
                 {
                   "name": "implicitRegSet",
                   "valueType": "string",
                   "value": "2"
                 }
               ]
             }
           ]
         },
         {
           "name": "userImsi",
           "valueType": "string",
           "value": "50002312344314"
         }
       ]
     },
     {
       "name": "PO",
       "valueType": "string",
       "value": "0"
     }
   ]
 }