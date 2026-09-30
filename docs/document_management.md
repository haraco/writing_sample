# Document Management

Manage documents and include them in the workflows you build.  

## About

In this section, you will learn how to manage a document's lifecycle in your workflow processes.  
This covers:

- [`Prerequisites`](#prerequisites): What you need to get started
- [`Authentication`](#authentication): How you access the API
- Requests: How you upload, retrieve or delete documents
- Examples: What requests and responses look like
- Responses: What you can expect from a successful request
- Error handling: What you can do if things go wrong
- Related operations: Where you can look for further guidance

## Prerequisites

To send requests, you must have the right to access the application  
and the REST right ``DocManagement``.

## Authentication

You log in via `BASIC`(https://www.rfc-editor.org/info/rfc7617/) authentication at `POST rest/app/users/login/basic`.  
If you successfully log in, the response contains a session cookie ``SessionID``  
that you must include in subsequent requests.

### Authentication Errors

The following errors can occur during authentication:

**401 Unauthorized**

: Possible reasons:
: 
: - You aren't logged in
: - The session expired.

**403 Forbidden**

: Possible reasons:
: 
: - You don't have the necessary right.

**400 Bad Request**

: Possible reasons:
: 
: - The syntax is invalid.

## Requests

Use the following operations to manage documents throughout their lifecycle:

- [`Upload a document`](./api/upload_document.md): Add a document to a process.
- [`Retrieve a document`](./api/get_document.md): Retrieve a document via its ID.
- [`Delete a document`](./api/delete_document.md): Delete a document from a process.


