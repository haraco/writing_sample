# Retrieve a Document

Retrieve a document from the specified process instance.  
To upload a document, see [`Upload a Document`](upload_document.md).

## `GET rest/app/processes/{instanceId}/documents/{documentId}`

### Request

**Path Parameters**

*``{instanceId}``*  

Specify the ID of the process instance from which you want to retrieve the document.

*``{documentId}``*  

Specify the ID of the document you want to retrieve.

### Example

```
curl -X GET \
  "https://api.example.com/rest/app/processes/12345/documents/3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f" \
  -H "Cookie: SessionID=<session-id>"
```

### Response

**Body**

*Content Type*: ``application/octet-stream``

Returns the requested document as a download stream.

### Errors

> **401 Unauthorized**
>
> Possible reasons:
> 
> - You aren't logged in
> - The session expired.

> **403 Forbidden**
> 
> Possible reasons:
>
> - You don't have the necessary right.
> - You don't have permission to access the specified process instance.

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





