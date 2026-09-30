# Retrieve a Document

Retrieve a document from the specified process instance.  

To upload a document, see [`Upload a Document`](upload_document.md).
To delete a document, see [`Delete a Document`](delete_document.md).

## `GET /rest/app/processes/_{instanceId}_/documents/_{documentId}_`

### Request

#### Path Parameters

*``{instanceId}``*  

Specify the ID of the process instance from which you want to retrieve the document.

*``{documentId}``*  

Specify the ID of the document you want to retrieve.

#### Example

```
curl -X GET \
  "https://api.example.com/rest/app/processes/12345/documents/3f7e2c91-4b8a-4d1e-9f3a-7c2e8a1b5d6f" \
  -H "Cookie: SessionID=<session-id>"
```

### Response

#### Body

*Content Type*: ``application/octet-stream``

Returns the requested document as a download stream.

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
    <li>You don't have permission to access the specified process instance.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>404 Not Found</dt>
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>The specified process instance ID doesn't exist.</li>
    <li>The specified document ID doesn't exist.</li>
    </ul>
  </dd>
</dl>

<dl>
  <dt>400 Bad Request</dt>
  <dd>Possible reasons:</dd>
  </dd>
  <dd><ul>
    <li>The <code>instanceId</code> or <code>documentId</code> is invalid.</li>
    </ul>
  </dd>
</dl>