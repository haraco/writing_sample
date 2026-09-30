# Upload a document

Uploads a document for the specified process instance.

To retrieve a document, see [`Retrieve a Document`](get_document.md).
To delete a document, see [`Delete a Document`](delete_document.md).

## `POST /rest/app/processes/{instanceId}/documents`

### Request

#### Path Parameters

``{instanceId}``

Specify the ID of the process instance to which you want to upload the document.

#### Body

*Content Type*: ``application/json``

```json
{
   "fileName": "meeting_notes_2026-08-20.pdf",
   "contentType": "application/pdf",
   "content": "<base64-encoded-content>"
}
```

The field `content` must contain the document's Base64-encoded content.  
Base64 is an encoding method and doesn't provide security. We sanitize all imported files before they're uploaded.

### Example

```
curl -X POST \
  "https://api.example.com/rest/app/processes/12345/documents" \
  -H "Content-Type: application/json" \
  -H "Cookie: SessionID=<session-id>" \
  -d '{
    "fileName": "meeting_notes_2026-08-20.pdf",
    "contentType": "application/pdf",
    "content": "<base64-encoded-content>"
  }'
```

### Response

#### Body

*Content Type*: ``application/json``

```json
{
   "documentId": "3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f",
   "url": "https://www.example.com/doc/meeting_notes_2026-08-20.pdf",
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
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>You aren't logged in.</li>
    <li>The session expired.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>403 Forbidden</dt>
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>You don't have the necessary right.</li>
    <li>You don't have permission to modify the specified process instance.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>404 Not Found</dt>
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>The specified process instance ID doesn't exist.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>400 Bad Request</dt>
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>The request body contains malformed JSON.</li>
    <li>Your request is invalid because a required field is missing or contains an invalid value.</li>
    </ul>
  </dd>
</dl>