
# addMessaging 

 **Last modified:** July 14, 2015

 _**Applies to:** Skype for Business 2015_

Starts a [messagingInvitation](messagingInvitation_ref.md) that adds the instant messaging modality to an existing [conversation](conversation_ref.md). 

## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>

 The addMessaging resource can be used to add the [messaging](messaging_ref.md) modality to an existing peer-to-peer [conversation](conversation_ref.md) or multi-party [onlineMeeting](onlineMeeting_ref.md). 


### Properties

None


### Links

None


## Operations
<a name="sectionSection2"> </a>




### POST

Starts a [messagingInvitation](messagingInvitation_ref.md) that adds the instant messaging modality to an existing [conversation](conversation_ref.md). 


#### Request body

None


#### Response body



|**Item**|**Description**|
|:-----|:-----|
| [messagingInvitation](messagingInvitation_ref.md)|Represents an invitation to a [conversation](conversation_ref.md) for the [messaging](messaging_ref.md) modality.|

#### Synchronous errors

The errors below (if any) are specific to this resource. Generic errors that can apply to any resource are covered in [Generic synchronous errors](GenericSynchronousErrors.md).



|**Error**|**Code**|**Subcode**|**Description**|
|:-----|:-----|:-----|:-----|
|ServiceFailure|500|CallbackChannelError|The remote event channel is not reachable|
|Conflict|409|AlreadyExists|The already exists error.|
|Conflict|409|TooManyGroups|The too many groups error.|
|Conflict|409|None|Un-supported Service/Resource/API error.|

#### Examples




#### JSON Request


```
Post https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/messaging/addMessaging HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com
Content-Type: application/json
Content-Length: 130
{
"operationId" : "74cb7404e0a247d5a2d4eb0376a47dbf",
"_links" : {
"message" : {
"href" : "data:text/plain;base64,somebase64encodedmessage"
}
}
}
							
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
HTTP/1.1 201 Created
Location: //v1/applications/833/communication/invitations/700
									
```


#### XML Request


```
Post https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/messaging/addMessaging HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com
Content-Type: application/xml
Content-Length: 179
<?xml version="1.0" encoding="utf-8"?>
<input xmlns="http://schemas.microsoft.com/rtc/2012/03/ucwa">
<property name="operationId">74cb7404e0a247d5a2d4eb0376a47dbf</property>
</input>	
							
```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
HTTP/1.1 201 Created
Location: //v1/applications/833/communication/invitations/700
									
```

