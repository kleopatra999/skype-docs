
# onBehalfOf 

 **Last modified:** July 14, 2015

 _**Applies to:** Skype for Business 2015_

 
Represents the [contact](contact_ref.md) on whose behalf the invitation was received.

## Web Link
<a name="sectionSection0"> </a>

For more on web links, see [Web links](WebLinks.md).



|**Name**|**Description**|
|:-----|:-----|
|rel|The resource that this link points to. In JSON, this is the outer container.|
|href|The location of this resource on the server, and the target of an HTTP operation.|

## Resource description
<a name="sectionSection1"> </a>

This resource is usually present in an incoming invitation when a delegate makes a call on the behalf of someone else. 


### Properties





|**Name**|**Description**|
|:-----|:-----|
|company|The name of the contact's company.|
|department|The name of the contact's department.|
|emailAddresses|The contact's e-mail addresses.|
|homePhoneNumber|The contact's home phone number.|
|sourceNetworkIconUrl|The web URI of the icon representing the contact's source network.|
|mobilePhoneNumber|The contact's mobile phone number.|
|name|The contact's name.|
|office|The contact's office number.|
|otherPhoneNumber|The contact's other phone number.|
|sourceNetwork|The contact's source network (SourceNetwork), such as SameEnterprise or PublicCloud (such as a Skype contact).|
|title|The contact's title.|
|type|The contact's type (ContactType), such as User, Phone, or Bot.|
|uri|The contact's URI.|
|workPhoneNumber|The contact's work phone number.|

### Links

This resource can have the following relationships.



|**Link**|**Description**|
|:-----|:-----|
|self|The link to the current resource.|
|contactLocation|Represents a [contact](contact_ref.md)'s location.|
|contactNote|Represents a [contact](contact_ref.md)'s personal or out-of-office note.|
|contactPhoto|The photo of a contact.|
|contactPresence|Represents a [contact](contact_ref.md)'s availability and activity.|
|contactPrivacyRelationship|Represents the privacy relationship between the user and a [contact](contact_ref.md).|
|contactSupportedModalities|Represents the communication modalities supported by a contact.|

## Operations
<a name="sectionSection2"> </a>




### GET

Returns a representation of the [contact](contact_ref.md) on behalf of whom the invitation was received.


#### Request body

None


#### Response body

The response from a GET request contains the properties and links shown in the Properties and Links sections at the top of this page.


#### Synchronous errors

The errors below (if any) are specific to this resource. Generic errors that can apply to any resource are covered in [Generic synchronous errors](GenericSynchronousErrors.md).



|**Error**|**Code**|**Subcode**|**Description**|
|:-----|:-----|:-----|:-----|
|Forbidden|403|None|Returned when an application does not have permission to view this contact's information.|
|Forbidden|403|None|The user does not have sufficient privileges to access the contact list.|
|ServiceFailure|500|InvalidExchangeServerVersion|Invalid exchange server version.The exchange mailbox of the server might have moved to an unsupported version for the required feature.|
|Conflict|409|AlreadyExists|The already exists error.|
|Conflict|409|TooManyGroups|The too many groups error.|
|Conflict|409|None|Un-supported Service/Resource/API error.|

#### Examples




#### JSON Request


```

 Get https://fe1.contoso.com:443//v1/applications/833/people/337 HTTP/1.1
 Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
 Host: fe1.contoso.com
 Accept: application/json
 if-none-match: 8bdca23a-d6fd-4d12-a9c9-de9b24186695
 
									
```


#### JSON Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

 HTTP/1.1 200 OK
 Etag: 5074ad36-8bad-4bfe-bf41-ce5197836e9d
 Content-Type: application/json
 Content-Length: 1081
 {
 "rel" : "onBehalfOf",
 "company" : "Contoso Corp.",
 "department" : "Engineering",
 "emailAddresses" : [
 "Alex.Doe@contoso.com"
 ],
 "homePhoneNumber" : "tel:+19185550107",
 "sourceNetworkIconUrl" : "https://images.contoso.com/logo_16x16.png",
 "mobilePhoneNumber" : "tel:4255551212;phone-context=defaultprofile",
 "name" : "Alex Doe",
 "office" : "tel:+1425554321;ext=54321",
 "otherPhoneNumber" : "tel:+19195558194",
 "sourceNetwork" : "SameEnterprise",
 "title" : "Engineer 2",
 "type" : "User",
 "uri" : "sip:alex@contoso.com",
 "workPhoneNumber" : "tel:+1425554321;ext=54321",
 "_links" : {
 "self" : {
 "href" : "//v1/applications/833/people/337"
 },
 "contactLocation" : {
 "href" : "//v1/applications/833/people/166/contactLocation"
 },
 "contactNote" : {
 "href" : "//v1/applications/833/people/166/contactNote"
 },
 "contactPhoto" : {
 "href" : "//v1/applications/833/people/166/contactPhoto"
 },
 "contactPresence" : {
 "href" : "//v1/applications/833/people/166/contactPresence"
 },
 "contactPrivacyRelationship" : {
 "href" : "//v1/applications/833/people/166/contactPrivacyRelationship"
 },
 "contactSupportedModalities" : {
 "href" : "//v1/applications/833/people/166/contactSupportedModalities"
 }
 }
}
									
```


#### XML Request


```

 Get https://fe1.contoso.com:443//v1/applications/833/people/337 HTTP/1.1
 Authorization: Bearer cwt=PHNhbWw6QXNzZXJ0aW9uIHhtbG5...uZm8
 Host: fe1.contoso.com
 Accept: application/xml
 if-none-match: 57e0acc8-8554-4e5a-90a4-eeb7c1edf4fd
 
									
```


#### XML Response

This sample is given only as an illustration of response syntax. The semantic content is not guaranteed to correspond to a valid scenario.


```

 HTTP/1.1 200 OK
 Etag: 4c4c9e3f-1e97-4ca2-a623-41692905306e
 Content-Type: application/xml
 Content-Length: 1600
 <?xml version="1.0" encoding="utf-8"?>
<resource rel="onBehalfOf" href="//v1/applications/833/people/337" xmlns="http://schemas.microsoft.com/rtc/2012/03/ucwa">
 <link rel="contactLocation" href="//v1/applications/833/people/166/contactLocation" />
 <link rel="contactNote" href="//v1/applications/833/people/166/contactNote" />
 <link rel="contactPhoto" href="//v1/applications/833/people/166/contactPhoto" />
 <link rel="contactPresence" href="//v1/applications/833/people/166/contactPresence" />
 <link rel="contactPrivacyRelationship" href="//v1/applications/833/people/166/contactPrivacyRelationship" />
 <link rel="contactSupportedModalities" href="//v1/applications/833/people/166/contactSupportedModalities" />
 <property name="rel">onBehalfOf</property>
 <property name="company">Contoso Corp.</property>
 <property name="department">Engineering</property>
 <propertyList name="emailAddresses">
 <item>Alex.Doe@contoso.com</item>
 </propertyList>
 <property name="homePhoneNumber">tel:+19185550107</property>
 <property name="sourceNetworkIconUrl">https://images.contoso.com/logo_16x16.png</property>
 <property name="mobilePhoneNumber">tel:4255551212;phone-context=defaultprofile</property>
 <property name="name">Alex Doe</property>
 <property name="office">tel:+1425554321;ext=54321</property>
 <property name="otherPhoneNumber">tel:+19195558194</property>
 <property name="sourceNetwork">SameEnterprise</property>
 <property name="title">Engineer 2</property>
 <property name="type">User</property>
 <property name="uri">sip:alex@contoso.com</property>
 <property name="workPhoneNumber">tel:+1425554321;ext=54321</property>
</resource>
									
```

