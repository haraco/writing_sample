# Upload a document

The following request uploads a document for the specified process instance  
with the Id *{instanceId}*.

> `POST rest/app/processes/{instanceId}/documents`
>
> **Request**
>
>> **Path Parameters**
>>
>> *``{instanceId}``*  
>>
>> Specify the process instancy by Id you want to upload the document to.
>> 
>> **Body**
>>
>> *Content Type*: ``application/json``
>>
>> ```
>> {
>>    "fileName": "meeting_notes_2026-08-30.pdf",
>>    "contentType": "application/pdf"
>> }
>> 
>
> **Response**
>
>
>
>
>
>
>
>
>