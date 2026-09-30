# Document Management

Manage documents and include them in the workflows you build.  

## About

This section explains how to manage a document's lifecycle in your workflow processes.  
This covers:

- [`Prerequisites`](#prerequisites): What you need to get started
- [`Authentication`](#authentication): How you access the API
- [`Requests`](#requests): How you upload, retrieve, or delete documents
- Examples: What requests and responses look like
- Error handling: What you can do if things go wrong

## Prerequisites

To send requests, you must have the right to access the application and the REST right ``DocManagement``.

## Authentication

You log in via [BASIC](https://www.rfc-editor.org/info/rfc7617/) authentication at `POST rest/app/users/login/basic`.  
If you successfully log in, the response contains a session cookie ``SessionID``  
that you must include in subsequent requests.

### Authentication errors

The following errors can occur during authentication:

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
    </ul>
  </dd>
</dl>

<dl>
  <dt>400 Bad Request</dt>
  <dd>
    Possible reasons:
    <ul>
      <li>The syntax is invalid.</li>
    </ul>
  </dd>
</dl>

## Requests

Use the following operations to manage documents throughout their lifecycle:

- [`Upload a document`](./api/upload_document.md): Add a document to a process.
- [`Retrieve a document`](./api/get_document.md): Retrieve a document via its ID.
- [`Delete a document`](./api/delete_document.md): Delete a document from a process.


