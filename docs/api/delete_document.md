# Delete a Document

Delete a document from the specified process instance.  

To upload a document, see [`Upload a Document`](upload_document.md).  
To retrieve a document, see [`Retrieve a Document`](get_document.md).

## `DELETE /rest/app/processes/{instanceId}/documents/{documentId}`

### Request

**Path Parameters**

*``{instanceId}``*  

Specify the ID of the process instance from which you want to delete the document.

*``{documentId}``*  

Specify the ID of the document you want to delete.

### Example

```
curl -X DELETE \
  "https://api.example.com/rest/app/processes/12345/documents/3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f" \
  -H "Cookie: SessionID=<session-id>"
```

### Response

**Body**

*Content Type*: ``application/json``

Returns the metadata of the document that was deleted.

```json
{
   "processId": "12345",
   "documentId": "3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f",
   "fileName": "meeting_notes_2026-08-20.pdf",
   "contentType": "application/pdf",
   "createdBy": {
     "userId": "1234",
     "userName": "testuser"
   },
   "createdOn": "2026-08-25T09:47:11+00:00",
   "modifiedBy": {
     "userId": "1234",
     "userName": "testuser"
   },
   "modifiedOn": "2026-08-25T09:47:11+00:00"
}
```

### Errors

> **401 Unauthorized**
>
> Possible reasons:
> 
> - You aren't logged in.
> - The session expired.

> **403 Forbidden**
> 
> Possible reasons:
>
> - You don't have the necessary right.
> - You don't have permission to access the specified process instance.
> - The process instance doesn't allow the deletion of documents.
> - The document is currently in use and can't be deleted.

> **404 Not Found**
> 
> Possible reasons:
>
> - The specified process instance ID doesn't exist.
> - The specified document ID doesn't exist.

> **400 Bad Request**
> 
> Possible reasons:
>
> - The ``instanceId`` or ``documentId`` is invalid.
