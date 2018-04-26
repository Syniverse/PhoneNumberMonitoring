# PhoneNumberMonitoring
Example code to subscribe & unsubscribe for Phone Number Monitoring from Syniverse.

By downloading the attached python files, and simply adding your access token and delivery configuration Id you can quickly set up monitoring for the phone numbers in the file phonenumbers.txt.

## Dependencies

You will first need to have an account (create at https://developer.syniverse.com ).

Then follow the instructions at https://sdcdocumentation.syniverse.com/index.php/batch-automation/quick-start-batch-automation to set up the platform.

## Sample output when running the Monitor script is

python.exe PycharmProjects/QuickStart-BatchNumberMonitoring-Python2/BatchMonitor-Example-External.py
### Starting Engines ###

Creating file in Media Storage
create file response status code: 201
mss create response body: {"file_id":"fa4b9ce1-b479-416a-903f-9789c12f36bc","company-id":"589","file_status":"CREATED","file_uri":"https://api.syniverse.com/mediastorage/v1/files/fa4b9ce1-b479-416a-903f-9789c12f36bc/content","file_version":1,"file_size":0,"file_fullsize":2000000,"creation_time":"2017-10-25T18:17:14.795 +0000","modified_time":"2017-10-25T18:17:14.795 +0000","file_retention_time":30,"expire_time":"2017-11-24T18:17:14.795 +0000"}

Uploading input file to Media Storage
upload response status code: 201
upload response: 

Scheduling the Number Monitoring batch job in Batch Automation
Scheduling response status code: 201
Scheduling response: {"schedule":{"id":"5233bf88-1515-4e11-9509-f4c4381f595a","jobId":"NIS-Scrub-Monitor-fs1-v1","name":"NISScrubMonitor","inputFileId":"fa4b9ce1-b479-416a-903f-9789c12f36bc","fileRetentionDays":30,"scheduleRetentionDays":30,"outputFileNamingExpression":"DS1-NIS-Scrub-Monitor-output.txt","outputFileFolder":"/opt/apps/aba/output","outputFileTag":null,"jobRuntimeContext":{"subscribedestinationid":"676","subscribeevents":"all"}}}

Waiting 20s for job to complete

Retrieving batch job execution details
Get batch job details status code: 200
Get batch job details response: {"executions":[{"id":"9bd6cca7-dd27-4a09-a1a7-6695caca6ff2","scheduleDetail":{"id":"5233bf88-1515-4e11-9509-f4c4381f595a","jobId":"NIS-Scrub-Monitor-fs1-v1","name":"NISScrubMonitor","inputFileId":"fa4b9ce1-b479-416a-903f-9789c12f36bc","fileRetentionDays":30,"scheduleRetentionDays":30,"outputFileNamingExpression":"DS1-NIS-Scrub-Monitor-output.txt","outputFileFolder":"/opt/apps/aba/output","outputFileTag":null,"jobRuntimeContext":{"subscribedestinationid":"676","subscribeevents":"all"}},"status":"COMPLETE","statusReason":"Final Status","startTimestamp":1508955437710,"statusUpdateTimestamp":1508955444918,"outputFileId":"817f01e7-df91-46c5-9030-2a45b984d034","errorDetailFileId":"EMPTY_FILE","retryFileId":"EMPTY_FILE","recordSuccessCount":3,"recordRetryCount":0,"recordErrorCount":0,"outputFileURI":"https://api.syniverse.com/mediastorage/v1/files/817f01e7-df91-46c5-9030-2a45b984d034/content","errorDetailFileURI":"EMPTY_FILE","retryFileURI":"EMPTY_FILE"}]}

Downloading the Output file
Download output status code: 200
Download output response: 
+18132633923,true,,,M,USA,United States,310,160,,Deactivated,,16291,T-MOBILE USA INC.,2016-12-30T05:00:00Z,,,100290274651508955441949,false,
+18135041457,true,,,M,USA,United States,310,160,,Deactivated,,16291,T-MOBILE USA INC.,2016-12-30T05:00:00Z,,,100290274651508955441977,false,
+18139551760,true,1125,VERIZON WIRELESS,M,USA,United States,310,12,,None,,,,,,,100290274651508955441904,true,TestRef123

Process finished with exit code 0

## Sample output when running the Unsubscribe script is 

python.exe PycharmProjects/BatchMonitor/BatchMonitorUnsubscribe-Example.py
    Starting Engines

Creating file in Media Storage
create file response status code: 201
mss create response body: {"file_id":"08fb7e20-3dae-47ea-936f-469a17b9d6ac","company-id":"589","file_status":"CREATED","file_uri":"https://api.syniverse.com/mediastorage/v1/files/08fb7e20-3dae-47ea-936f-469a17b9d6ac/content","file_version":1,"file_checksum":0,"file_size":0,"file_fullsize":2000000,"creation_time":"2017-07-28T09:04:44.063 +0000","modified_time":"2017-07-28T09:04:44.063 +0000","file_retention_time":30,"expire_time":"2017-08-27T09:04:44.063 +0000"}

Uploading input file to Media Storage
upload response status code: 201
upload response: 

Scheduling the Number Monitoring Unsubscribe batch job in Batch Automation
Scheduling response status code: 201
Scheduling response: {"schedule":{"id":"cf5850e3-147a-4e7c-b32b-914b264fb501","jobId":"NIS-Unsubscribe-v2","name":"NISUnsubscribe","inputFileId":"08fb7e20-3dae-47ea-936f-469a17b9d6ac","fileRetentionDays":30,"scheduleRetentionDays":30,"outputFileNamingExpression":"DS1-NIS-Unsubscribe-output.txt","outputFileFolder":"/opt/apps/aba/output","outputFileTag":null,"jobRuntimeContext":{}}}

Waiting 20s for job to complete

Retrieving batch job execution details
Get batch job details status code: 200
Get batch job details response: {"executions":[{"id":"74e8e09f-224b-482e-a7f4-8189dedb939e","scheduleDetail":{"id":"cf5850e3-147a-4e7c-b32b-914b264fb501","jobId":"NIS-Unsubscribe-v2","name":"NISUnsubscribe","inputFileId":"08fb7e20-3dae-47ea-936f-469a17b9d6ac","fileRetentionDays":30,"scheduleRetentionDays":30,"outputFileNamingExpression":"DS1-NIS-Unsubscribe-output.txt","outputFileFolder":"/opt/apps/aba/output","outputFileTag":null,"jobRuntimeContext":{}},"status":"COMPLETE","statusReason":"Final Status","startTimestamp":1501232693409,"statusUpdateTimestamp":1501232698016,"outputFileId":"ba0f8c70-ab93-44eb-bd7a-2c0b2e14b0f7","errorDetailFileId":"EMPTY_FILE","retryFileId":"EMPTY_FILE","recordSuccessCount":3,"recordRetryCount":0,"recordErrorCount":0,"outputFileURI":"https://api.syniverse.com/mediastorage/v1/files/ba0f8c70-ab93-44eb-bd7a-2c0b2e14b0f7/content","errorDetailFileURI":"EMPTY_FILE","retryFileURI":"EMPTY_FILE"}]}

Downloading the Output file
Download output status code: 200
Download output response: 
+18132633923,unsubscribe,ALL,2017-07-28T09:04:55.564Z[UTC]
+18135041457,unsubscribe,ALL,2017-07-28T09:04:55.559Z[UTC]
+18139551760,unsubscribe,ALL,2017-07-28T09:04:55.564Z[UTC]

Process finished with exit code 0

## Example Phone Event Notification

Once subscribed you will receive a notification if anything happens to a subscribed phone number.

Notifications are sent by the Event Manager system (https://sdcdocumentation.syniverse.com/index.php/event-manager/overview) as a POST request to your defined end point.

The headers and payload for an example notification are shown below.

HEADERS
  "X-ESS-EVENT-KEY": "+17805199493,",
  "X-ESS-EVENT-TIMESTAMP": "2017-07-12T20:21:00.129Z",
  "CONTENT-TYPE": "application/json; charset=UTF-8"

BODY/PAYLOAD
{"topic":"NIS-Events","attempt":1,"event":{"fld-val-list":{"number":"+17805199493","previous_carrier_id":"1025","previous_carrier_name":"AT@$# T WIRELESS","tracking_id":"1655272074","deactivation_date":"2017-06-03T04:00:00Z"},"evt-tp":"deactivation_event","timestamp":"2017-07-12T20:21:00.129Z"},"event-id":"d0qgWF8ERLGn_7JJOGhqNQ"}

