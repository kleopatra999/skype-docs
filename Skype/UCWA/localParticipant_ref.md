
# localParticipant 

 **Last modified:** July 14, 2015

 _**Applies to:** Skype for Business 2015_

Represents the user as a local [participant](participant_ref.md) in a specific [conversation](conversation_ref.md). 

## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>

participant is the transient representation of the user that captures her attributes such as role or capabilities (such as promoting to leader or admitting from lobby). A localParticipant's lifetime is controlled by the server and starts when the user joins a [conversation](conversation_ref.md). It is removed when the participant leaves the [conversation](conversation_ref.md). 


### Properties





|**Name**|**Description**|
|:-----|:-----|
|anonymous|Whether the participant is anonymous.|
|name|The participant's display name.|
|organizer|Whether the participant is an organizer.An organizer can never be locked out of her own meeting.|
|otherPhoneNumber|The participant's Other Phone.|
|role|The participant's role (Role), such as Attendee or Leader.|
|sourceNetwork|The participant's source network (SourceNetwork), such as SameEnterprise or PublicCloud (for example, a Skype contact).|
|uri|The participant's URI.|
|workPhoneNumber|The participant's Phone URI.|

### Links

This resource can have the following relationships.



|**Link**|**Description**|
|:-----|:-----|
|self|The link to the current resource.|
|contact|Represents a person or service that the user can communicate and collaborate with.|
|contactPhoto|The photo of a contact.|
|contactPresence|Represents a [contact](contact_ref.md)'s availability and activity.|
|conversation|Represents the local participants perspective on a multi-modal, multi-party communication.|
|eject|Ejects the corresponding [participant](participant_ref.md) from the [onlineMeeting](onlineMeeting_ref.md).|
|me|Represents the user.|
|participantApplicationSharing|Represents whether a participant is using the application sharing modality in a conversation.|
|participantAudio|Represents whether a participant is using the audio modality in a conversation.|
|participantDataCollaboration|Represents whether a participant is using the data collaboration modality in a conversation.|
|participantMessaging|Used to determine whether a participant is using the instant messaging modality in a conversation.|
|participantPanoramicVideo|Represents whether a participant is using the panoramic video modality in a conversation.|
|participantVideo|Represents whether a participant is using the main video modality in a conversation.|

## Events
<a name="sectionSection2"> </a>




### added





|**Resource**|**Priority**|**Sender**|**Reason**|
|:-----|:-----|:-----|:-----|
|localParticipant|High|conversation|Indicates that the user has joined a [conversation](conversation_ref.md).|
Sample of returned event data.

This sample is given only as an illustration of event syntax. The semantic content is not guaranteed to correspond to a valid scenario.




```

{
 "_links" : {
 "self" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=1"
 },
 "next" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=2"
 }
 },
 "sender" : [
 {
 "rel" : "conversation",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802",
 "events" : [
 {
 "link" : {
 "rel" : "localParticipant",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/onlineMeeting/665"
 },
 "type" : "added"
 }
 ]
 }
 ]
}
					
```


### updated





|**Resource**|**Priority**|**Sender**|**Reason**|
|:-----|:-----|:-----|:-----|
|localParticipant|High|conversation|Indicates that the user has been updated.|
Sample of returned event data.

This sample is given only as an illustration of event syntax. The semantic content is not guaranteed to correspond to a valid scenario.




```

{
 "_links" : {
 "self" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=1"
 },
 "next" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=2"
 }
 },
 "sender" : [
 {
 "rel" : "conversation",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802",
 "events" : [
 {
 "link" : {
 "rel" : "localParticipant",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/onlineMeeting/665"
 },
 "type" : "updated"
 }
 ]
 }
 ]
}
					
```


### deleted





|**Resource**|**Priority**|**Sender**|**Reason**|
|:-----|:-----|:-----|:-----|
|localParticipant|High|conversation|Indicates that the user has left a conversation.|
Sample of returned event data.




```

{
 "_links" : {
 "self" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=1"
 },
 "next" : {
 "href" : "http://sample:80/ucwa/v1/applications/appId/events?ack=2"
 }
 },
 "sender" : [
 {
 "rel" : "conversation",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802",
 "events" : [
 {
 "link" : {
 "rel" : "localParticipant",
 "href" : "https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/onlineMeeting/665"
 },
 "type" : "deleted"
 }
 ]
 }
 ]
}
					
```


## Operations
<a name="sectionSection3"> </a>




### GET

Returns a representation of the user as a local [participant](participant_ref.md) in a specific [conversation](conversation_ref.md).


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
Get https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/onlineMeeting/665 HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com
Accept: application/json
									
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
 HTTP/1.1 200 OK
 Content-Type: application/json
 Content-Length: 1540
 {
 "rel" : "localParticipant",
 "anonymous" : true,
 "name" : "Joe Smith",
 "organizer" : true,
 "otherPhoneNumber" : "tel:+14251111111",
 "role" : "Attendee",
 "sourceNetwork" : "SameEnterprise",
 "uri" : "sip:john@contoso.com",
 "workPhoneNumber" : "tel:+14251111111",
 "_links" : {
 "self" : {
 "href" : "//v1/applications/833/communication/conversations/802/onlineMeeting/665"
 },
 "contact" : {
 "href" : "//v1/applications/833/people/166"
 },
 "contactPhoto" : {
 "href" : "//v1/applications/833/people/166/contactPhoto"
 },
 "contactPresence" : {
 "href" : "//v1/applications/833/people/166/contactPresence"
 },
 "conversation" : {
 "href" : "//v1/applications/833/communication/conversations/802"
 },
 "eject" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/eject"
 },
 "me" : {
 "href" : "//v1/applications/833/me"
 },
 "participantApplicationSharing" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantApplicationSharing"
 },
 "participantAudio" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantAudio"
 },
 "participantDataCollaboration" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantDataCollaboration"
 },
 "participantMessaging" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantMessaging"
 },
 "participantPanoramicVideo" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantPanoramicVideo"
 },
 "participantVideo" : {
 "href" : "//v1/applications/833/communication/conversations/802/participants/575/participantVideo"
 }
 }
}
									
```


#### XML Request


```
Get https://fe1.contoso.com:443//v1/applications/833/communication/conversations/802/onlineMeeting/665 HTTP/1.1
Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
Host: fe1.contoso.com
Accept: application/xml
									
```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```
 HTTP/1.1 200 OK
 Content-Type: application/xml
 Content-Length: 1960
 <?xml version="1.0" encoding="utf-8"?>
 <resource rel="localParticipant" href="//v1/applications/833/communication/conversations/802/onlineMeeting/665" xmlns="http://schemas.microsoft.com/rtc/2012/03/ucwa">
 <link rel="contact" href="//v1/applications/833/people/166" />
 <link rel="contactPhoto" href="//v1/applications/833/people/166/contactPhoto" />
 <link rel="contactPresence" href="//v1/applications/833/people/166/contactPresence" />
 <link rel="conversation" href="//v1/applications/833/communication/conversations/802" />
 <link rel="eject" href="//v1/applications/833/communication/conversations/802/participants/575/eject" />
 <link rel="me" href="//v1/applications/833/me" />
 <link rel="participantApplicationSharing" href="//v1/applications/833/communication/conversations/802/participants/575/participantApplicationSharing" />
 <link rel="participantAudio" href="//v1/applications/833/communication/conversations/802/participants/575/participantAudio" />
 <link rel="participantDataCollaboration" href="//v1/applications/833/communication/conversations/802/participants/575/participantDataCollaboration" />
 <link rel="participantMessaging" href="//v1/applications/833/communication/conversations/802/participants/575/participantMessaging" />
 <link rel="participantPanoramicVideo" href="//v1/applications/833/communication/conversations/802/participants/575/participantPanoramicVideo" />
 <link rel="participantVideo" href="//v1/applications/833/communication/conversations/802/participants/575/participantVideo" />
 <property name="rel">localParticipant</property>
 <property name="anonymous">True</property>
 <property name="name">Joe Smith</property>
 <property name="organizer">True</property>
 <property name="otherPhoneNumber">tel:+14251111111</property>
 <property name="role">Attendee</property>
 <property name="sourceNetwork">SameEnterprise</property>
 <property name="uri">sip:john@contoso.com</property>
 <property name="workPhoneNumber">tel:+14251111111</property>
</resource>
									
```

