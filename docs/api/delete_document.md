# Delete a document

Delete a document from the specified process instance.  

To upload a document, see [`Upload a document`](upload_document.md).  
To retrieve a document, see [`Retrieve a document`](get_document.md).

## `DELETE /rest/app/processes/{instanceId}/documents/{documentId}`

### Request

#### Path parameters

``{instanceId}``  

Specify the ID of the process instance from which you want to delete the document.

``{documentId}``  

Specify the ID of the document you want to delete.

#### Example

```bash
curl -X DELETE \
  "https://api.example.com/rest/app/processes/12345/documents/3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f" \
  -H "Cookie: SessionID=<session-id>"
```

### Response

#### Body

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

<dl>
  <dt>401 Unauthorized</dt>
  <dd>
    Possible reasons:
    <ul>
      <li>You aren't logged in.</li>
      <li>The session expired.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>403 Forbidden</dt>
  <dd>
    Possible reasons:
    <ul>
      <li>You don't have the necessary right.</li>
      <li>You don't have permission to access the specified process instance.</li>
      <li>The process instance doesn't allow the deletion of documents.</li>
      <li>The document is currently in use and can't be deleted.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>404 Not Found</dt>
  <dd>
    Possible reasons:
    <ul>
      <li>The specified process instance ID doesn't exist.</li>
      <li>The specified document ID doesn't exist.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>400 Bad Request</dt>
  <dd>
    Possible reasons:
    <ul>
      <li>The <code>instanceId</code> or <code>documentId</code> is invalid.</li>
    </ul>
  </dd>
</dl>