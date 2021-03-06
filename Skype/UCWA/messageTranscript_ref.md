
# messageTranscript

 **Last modified:** July 14, 2015

 
Represents a message transcript within a [conversationLog](conversationLog_ref.md). 


## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>




### Properties





|**Name**|**Description**|
|:-----|:-----|
|htmlMessage|If populated, indicates an HTML message body.|
|plainMessage|If populated, indicates a plain text message body.|

### Links

This resource can have the following relationships.



|**Link**|**Description**|
|:-----|:-----|
|self|The link to the current resource.|

## Operations
<a name="sectionSection2"> </a>




### GET

Returns a representation of a message transcript in [conversationLog](conversationLog_ref.md).


#### Request body

None


#### Response body

The response from a GET request contains the properties and links shown in the Properties and Links sections at the top of this page.


#### Synchronous errors

The errors below (if any) are specific to this resource. Generic errors that can apply to any resource are covered in [Generic synchronous errors](GenericSynchronousErrors.md).



|**Error**|**Code**|**Subcode**|**Description**|
|:-----|:-----|:-----|:-----|
|ServiceFailure|500|InvalidExchangeServerVersion|Invalid exchange server version.The exchange mailbox of the server might have moved to an unsupported version for the required feature.|
|Conflict|409|AlreadyExists|The already exists error.|
|Conflict|409|TooManyGroups|The too many groups error.|
|Conflict|409|None|Un-supported Service/Resource/API error.|

#### Examples




#### JSON Request


```

 Get https://fe1.contoso.com:443//v1/applications/833/communication/conversationLogs/conversationLog/conversationLogTranscripts/conversationLogTranscript/messageTranscript HTTP/1.1
 Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
 Host: fe1.contoso.com
 Accept: application/json
 
									
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

 HTTP/1.1 200 OK
 Content-Type: application/json
 Content-Length: 349
 {
 "rel" : "messageTranscript",
 "_links" : {
 "self" : {
 "href" : "//v1/applications/833/communication/conversationLogs/conversationLog/conversationLogTranscripts/conversationLogTranscript/messageTranscript"
 },
 "htmlMessage" : {
 "href" : "data:text/html;base64,base64-encoded-htmlmessage"
 },
 "plainMessage" : {
 "href" : "data:text/plain;charset=utf8,URLEncodedMessageString"
 }
 }
}
									
```


#### XML Request


```

 Get https://fe1.contoso.com:443//v1/applications/833/communication/conversationLogs/conversationLog/conversationLogTranscripts/conversationLogTranscript/messageTranscript HTTP/1.1
 Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
 Host: fe1.contoso.com
 Accept: application/xml
 
									
```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

 HTTP/1.1 200 OK
 Content-Type: application/xml
 Content-Length: 502
 <?xml version="1.0" encoding="utf-8"?>
<resource rel="messageTranscript" href="//v1/applications/833/communication/conversationLogs/conversationLog/conversationLogTranscripts/conversationLogTranscript/messageTranscript" xmlns="http://schemas.microsoft.com/rtc/2012/03/ucwa">
 <link rel="htmlMessage" href="data:text/html;base64,base64-encoded-htmlmessage" />
 <link rel="plainMessage" href="data:text/plain;charset=utf8,URLEncodedMessageString" />
 <property name="rel">messageTranscript</property>
</resource>
									
```

