# Upload a document

The following request uploads a document for the specified process instance  
with the Id *``{instanceId}``*.

## `POST rest/app/processes/{instanceId}/documents`

### Request

**Path Parameters**

*``{instanceId}``*  

Specify the process instance by Id to upload the document to.

**Body**

*Content Type*: ``application/json``

```
{
   "fileName": "meeting_notes_2026-08-20.pdf",
   "contentType": "application/pdf"
}

### Response

**Body**

*Content Type*: ``application/json``

```
{
   "documentId": "3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f",
   "url": "https://www.example.com/doc/meeting_notes_2026-08-20.pdf",
   "fileName": "meeting_notes_2026-08-30.pdf",
   "contentType": "application/pdf",
   "createdBy": {
     "userId": "1234",
     "userName": "testuser"
   }
   "createdOn": "2026-08-25T09:47:11+00:00"
   "modifiedBy": {
     "userId": "1234",
     "userName": "testuser"
   }
   "modifiedOn": "2026-08-25T09:47:11+00:00"
}
```







