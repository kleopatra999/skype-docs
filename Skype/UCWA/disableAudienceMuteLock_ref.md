
# disableAudienceMuteLock 

 **Last modified:** July 14, 2015

 _**Applies to:** Skype for Business 2015_

Disables the forced mute of attendees in a [conversation](conversation_ref.md). 

## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>

The presence of this resource indicates that the user has the ability to remove the forced mute from attendees. Using this ability will not actually unmute attendees; however, they will be able to unmute themselves. 


### Properties

None


### Links

None


## Operations
<a name="sectionSection2"> </a>




### POST

Disables the forced mute of attendees in a [conversation](conversation_ref.md).


#### Request body

None


#### Response body

None


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
Post https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/disableAudienceMuteLock HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com
									
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
HTTP/1.1 204 No Content

```


#### XML Request


```
Post https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/disableAudienceMuteLock HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com

```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
HTTP/1.1 204 No Content

```

