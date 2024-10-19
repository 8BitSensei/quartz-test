2023-08-16
Tags: #networking #constellix

A GeoProximityId is connected to a lat-long in the GeoProximity model
There is an array of GeoProximity models that we can pull from constellix API
Details required to query constellix will be in the appsettings for the data center service

```json
 "Constellix": {
            "ApiKey": "f569419d-5da0-49e9-b7aa-1ec5705e3560",
            "ApiSecret": "bb85ba12-22f0-4def-8289-5af47bf43dae",
            "BaseAddress": "https://api.dns.constellix.com",
            "DomainId": "493018",
            "GeoProximityPrefix": "dcstag_",
            "CNameRecordName": "ping-dtk",
            "CNameRecordTTL": 60
        } 
```

GET to `https://api.dns.constellix.com/v1/geoProximities`



---
# References
