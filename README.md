# fire-calls
Python Data Loading Demo

## The Question
How often are fire trucks called out for fires?

## The Data Source

[Louisville/Jefferson County Fire Districts calls for service](https://data.louisvilleky.gov/dataset/louisvillejefferson-county-fire-districts-calls-service)

Calls for service broken down by Fire Districts which includes but not limited to Fire and Medical Emergencies.


### File Details
|Dimension | Description |
| ------ | --------|
| Columns | AGENCY NAME – Name of the fire protection agency that has jurisdiction for the event.|
| |DATE – Date the event occurred.|
| |CREATE – Time the event was entered into the 911 CAD system. |
| |DISPATCH – Time dispatchers notified responders of event. |
| |ENROUTE - Time the first unit went responding to event. |
| |ARRIVE - Time the first unit called on scene to an event.|
| |CLEAR - Time last unit left scene and the event was closed.|
| |HOUR OF – Hour of the day the event occurred (24hr clock)|
| |LOCATION – Hundred block that event took place.|
| |EVENT TYPE – Type of event that took place.|
| |PRIORITY - Numeric value for the severity of incident. The lower the number the greater the severity.|
| |FD EVENT NUMBER – Unique number for event assigned to the agency that has jurisdiction.|
| |ZIP CODE – The zip code in which the event occurred. |
| Records | 158898 items |


### Sample Data


|AGENCY_NAME|DATE|CREATE|DISPATCH|ENROUTE|ARRIVE|CLEAR|HOUR OF|LOCATION|EVENT TYPE|PRIORITY|FD EVENT NUMBER|ZIP_CODE|
|-----------|----|------|--------|-------|------|-----|-------|--------|----------|--------|---------------|---------|
|Louisville Fire Department|01/01/2020|00:07:44||||00:08:00|0000|400 BLOCK OF S 5TH ST|ALARM--Fire Alarm Sounding-Commercial|2|LF190042159|40202|
|Louisville Fire Department|01/01/2020|00:10:18|00:10:48|00:11:48|00:15:41|00:21:13|0000|1200 BLOCK OF LARCHMONT AVE|FIRE--Fire-Type Unknown|2|LF200000001|40215|
|Louisville Fire Department|01/01/2020|00:20:24|00:20:44|00:21:56|00:25:18|00:51:35|0000|1800 BLOCK OF MCCLOSKEY AVE|FIRE--Fire/Close to Structure|2|LF200000002|40210|
|Louisville Fire Department|01/01/2020|00:26:23|00:26:43|00:27:53|00:34:15|00:52:36|0000|100 BLOCK OF COLONIAL OAKS CT|MEDICAL--MEDICAL - MED_CALL|7|LF200000003|40214|
|Louisville Fire Department|01/01/2020|00:30:03|00:30:28|00:32:15|00:37:06|00:56:50|0000|3500 BLOCK OF WHEELER AVE|MEDICAL--MEDICAL - MED_CALL|7|LF200000004|40215|
|Pleasure Ridge Park FD|01/01/2020|00:33:57|00:34:11|00:36:01|00:40:22|01:08:20|0000|8200 BLOCK OF DIXIE HWY|MEDICAL--MEDICAL - MED_CALL|7|F2219007864|40258|
|St Matthews FD|01/01/2020|00:41:46|00:42:01|00:44:45|00:48:58|01:09:06|0000|800 BLOCK OF WASHBURN AVE|FIRE--Dumpster Fire|3|F2619004232|40222|
|Middletown FD|01/01/2020|00:55:51|00:56:02|00:58:47|01:02:47|02:29:05|0000|2500 BLOCK OF EVERGREEN RD|ACCIDENT--Injury Accident|2|F9919005687|40223|
|Pleasure Ridge Park FD|01/01/2020|01:11:05|01:11:26|01:13:10|01:19:38|01:35:31|0100|7800 BLOCK OF BRAMBLE LN|MEDICAL--MEDICAL - MED_CALL|7|F2220000001| |


### Data Issues
1. issue
1. issue
1. issue

### Target Clean Data Format


Call Data by Event Category
`
    {
        'FIRE' : 1234,
        'MEDICAL': 234
    }
`

Call Data by Zip
` 
    {
        '40203' = {
            'CALL_TOTAL' : 20,
            'FIRE_TOTAL' : 5,
            'OTHER_TOTAL' : 15
        },
        '40204' = {
            'CALL_TOTAL' : 21,
            'FIRE_TOTAL' : 7,
            'OTHER_TOTAL' : 14
        }
    }
`

Call Data by Priority
`
    {
        '1' : 1234,
        '2': 234
    }
`
