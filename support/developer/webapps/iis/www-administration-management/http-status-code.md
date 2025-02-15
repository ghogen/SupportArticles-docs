---
title: HTTP status code overview
description: This article provides a list of the HTTP status codes in IIS 7.0 and later versions.
ms.date: 07/21/2020
ms.custom: sap:WWW Administration and Management
ms.reviewer: v-jayc
ms.technology: iis-www-administration-management
---
# The HTTP status code in IIS 7.0 and later versions

This article provides a list of the Hypertext Transfer Protocol (HTTP) status codes in Microsoft Internet Information Services (IIS) 7.0 and later versions.

_Original product version:_ &nbsp; Internet Information Services 7.0 and later versions  
_Original KB number:_ &nbsp; 943891

## Introduction

When you try to access content on a server that is running (IIS) 7.0, 7.5 or later versions by using the HTTP protocol, IIS returns a numeric code that indicates the status of the response. The HTTP status code is recorded in the IIS log. Additionally, the HTTP status code may be displayed in the client browser.

The HTTP status code may indicate whether a request is successful or unsuccessful. The HTTP status code may also reveal the exact reason that a request is unsuccessful.

## Log file locations

IIS 7.0 and later versions put log files in the following folder by default:  
`inetpub\logs\Logfiles`

This folder contains separate directories for each World Wide Web website. The log files are created in the directories daily and are named by using the date by default. For example, a log file may be named as _exYYMMDD.log_.

## The HTTP status codes

This section describes the HTTP status codes that IIS 7.0 and later versions use.

> [!NOTE]
> This article doesn't list every possible HTTP status code as dictated in the HTTP specification. This article includes only the HTTP status codes that IIS 7.0 and later versions can send. For example, a custom Internet Server API (ISAPI) filter or a custom HTTP module can set its own HTTP status code.

### 1**xx** - Informational

These HTTP status codes indicate a provisional response. The client computer receives one or more 1**xx** responses before the client computer receives a regular response.

IIS 7.0 and later versions use the following informational HTTP status codes:

- 100 - Continue.
- 101 - Switching protocols.

### 2**xx** - Success

These HTTP status codes indicate that the server successfully accepted the request.

IIS 7.0 and later versions use the following success HTTP status codes:

- 200 - OK. The client request has succeeded.
- 201 - Created.
- 202 - Accepted.
- 203 - Nonauthoritative information.
- 204 - No content.
- 205 - Reset content.
- 206 - Partial content.

### 3**xx** - Redirection

These HTTP status codes indicate that the client browser must take more action to fulfill the request. For example, the client browser may have to request a different page on the server. Or, the client browser may have to repeat the request by using a proxy server.

IIS 7.0 and later versions use the following redirection HTTP status codes:

- 301 - Moved permanently.
- 302 - Object moved.
- 304 - Not modified.
- 307 - Temporary redirect.

### 4**xx** - Client error

These HTTP status codes indicate that an error has occurred and the client browser appears to be at fault. For example, the client browser may have requested a page that doesn't exist. Or, the client browser may not have provided valid authentication information.

IIS 7.0 and later versions use the following client error HTTP status codes:

- 400 - Bad request. The request could not be understood by the server due to malformed syntax. The client should not repeat the request without modifications.  

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 400:

  - 400.1 - Invalid Destination Header.
  - 400.2 - Invalid Depth Header.
  - 400.3 - Invalid If Header.
  - 400.4 - Invalid Overwrite Header.
  - 400.5 - Invalid Translate Header.
  - 400.6 - Invalid Request Body.
  - 400.7 - Invalid Content Length.
  - 400.8 - Invalid Timeout.
  - 400.9 - Invalid Lock Token.

- 401 - Access denied.

  IIS 7.0 and later versions define several HTTP status codes that indicate a more specific cause of an error 401. The following specific HTTP status codes are displayed in the client browser but aren't displayed in the IIS log:

  - 401.1 - Logon failed.
  - 401.2 - Logon failed due to server configuration.
  - 401.3 - Unauthorized due to ACL on resource.
  - 401.4 - Authorization failed by filter.
  - 401.5 - Authorization failed by ISAPI/CGI application.
  - 401.501 - Access Denied: Too many requests from the same client IP; Dynamic IP Restriction Concurrent request rate limit reached.
  - 401.502 - Forbidden: Too many requests from the same client IP; Dynamic IP Restriction Maximum request rate limit reached.
  - 401.503 - Access Denied: the IP address is included in the Deny list of IP Restriction
  - 401.504 - Access Denied: the host name is included in the Deny list of IP Restriction

- 403 - Forbidden.

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 403:

  - 403.1 - Execute access forbidden.
  - 403.2 - Read access forbidden.
  - 403.3 - Write access forbidden.
  - 403.4 - SSL required.
  - 403.5 - SSL 128 required.
  - 403.6 - IP address rejected.
  - 403.7 - Client certificate required.
  - 403.8 - Site access denied.
  - 403.9 - Forbidden: Too many clients are trying to connect to the web server.
  - 403.10 - Forbidden: web server is configured to deny Execute access.
  - 403.11 - Forbidden: Password has been changed.
  - 403.12 - Mapper denied access.
  - 403.13 - Client certificate revoked.
  - 403.14 - Directory listing denied.
  - 403.15 - Forbidden: Client access licenses have exceeded limits on the web server.
  - 403.16 - Client certificate is untrusted or invalid.
  - 403.17 - Client certificate has expired or is not yet valid.
  - 403.18 - Cannot execute requested URL in the current application pool.
  - 403.19 - Cannot execute CGI applications for the client in this application pool.
  - 403.20 - Forbidden: Passport logon failed.
  - 403.21 - Forbidden: Source access denied.
  - 403.22 - Forbidden: Infinite depth is denied.
  - 403.501 - Forbidden: Too many requests from the same client IP; Dynamic IP Restriction Concurrent request rate limit reached.
  - 403.502 - Forbidden: Too many requests from the same client IP; Dynamic IP Restriction Maximum request rate limit reached.
  - 403.503 - Forbidden: the IP address is included in the Deny list of IP Restriction
  - 403.504 - Forbidden: the host name is included in the Deny list of IP Restriction

- 404 - Not found.

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 404:

  - 404.0 - Not found.
  - 404.1 - Site Not Found.
  - 404.2 - ISAPI or CGI restriction.
  - 404.3 - Multipurpose Internet Mail Extensions (MIME) type restriction.
  - 404.4 - No handler configured.
  - 404.5 - Denied by request filtering configuration.
  - 404.6 - Verb denied.
  - 404.7 - File extension denied.
  - 404.8 - Hidden namespace.
  - 404.9 - File attribute hidden.
  - 404.10 - Request header too long.
  - 404.11 - Request contains double escape sequence.
  - 404.12 - Request contains high-bit characters.
  - 404.13 - Content length too large.
  - 404.14 - Request URL too long.
  - 404.15 - Query string too long.
  - 404.16 - DAV request sent to the static file handler.
  - 404.17 - Dynamic content mapped to the static file handler via a wildcard MIME mapping.
  - 404.18 - Querystring sequence denied.
  - 404.19 - Denied by filtering rule.
  - 404.20 - Too Many URL Segments
  - 404.501 - Not Found: Too many requests from the same client IP; Dynamic IP Restriction Concurrent request rate limit reached.
  - 404.502 - Not Found: Too many requests from the same client IP; Dynamic IP Restriction Maximum request rate limit reached.
  - 404.503 - Not Found: the IP address is included in the Deny list of IP Restriction
  - 404.504 - Not Found: the host name is included in the Deny list of IP Restriction

- 405 - Method Not Allowed.
- 406 - Client browser does not accept the MIME type of the requested page.
- 408 - Request timed out.
- 412 - Precondition failed.

### 5**xx** - Server error

These HTTP status codes indicate that the server can't complete the request because the server encounters an error.

IIS and later versions use the following server error HTTP status codes:

- 500 - Internal server error.

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 500:

  - 500.0 - Module or ISAPI error occurred.
  - 500.11 - Application is shutting down on the web server.
  - 500.12 - Application is busy restarting on the web server.
  - 500.13 - Web server is too busy.
  - 500.15 - Direct requests for Global.asax are not allowed.
  - 500.19 - Configuration data is invalid.
  - 500.21 - Module not recognized.
  - 500.22 - An ASP.NET `httpModules` configuration does not apply in Managed Pipeline mode.
  - 500.23 - An ASP.NET `httpHandlers` configuration does not apply in Managed Pipeline mode.
  - 500.24 - An ASP.NET impersonation configuration does not apply in Managed Pipeline mode.
  - 500.50 - A rewrite error occurred during `RQ_BEGIN_REQUEST` notification handling. A configuration or inbound rule execution error occurred.

    > [!NOTE]
    > Here is where the distributed rules configuration is read for both inbound and outbound rules.

  - 500.51 - A rewrite error occurred during GL_PRE_BEGIN_REQUEST notification handling. A global configuration or global rule execution error occurred.

    > [!NOTE]
    > Here is where the global rules configuration is read.

  - 500.52 - A rewrite error occurred during `RQ_SEND_RESPONSE` notification handling. An outbound rule execution occurred.
  - 500.53 - A rewrite error occurred during `RQ_RELEASE_REQUEST_STATE` notification handling. An outbound rule execution error occurred. The rule is configured to be executed before the output user cache gets updated.
  - 500.100 - Internal ASP error.

- 501 - Header values specify a configuration that is not implemented.
- 502 - Web server received an invalid response while acting as a gateway or proxy.

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 502:

  - 502.1 - CGI application timeout.
  - 502.2 - Bad gateway: Premature Exit.
  - 502.3 - Bad Gateway: Forwarder Connection Error (ARR).
  - 502.4 - Bad Gateway: No Server (ARR).

- 503 - Service unavailable.

  IIS 7.0 and later versions define the following HTTP status codes that indicate a more specific cause of an error 503:

  - 503.0 - Application pool unavailable.
  - 503.2 - Concurrent request limit exceeded.
  - 503.3 - ASP.NET queue full
  - 503.4 - FastCGI queue full

## Common HTTP status codes and the causes

The following table describes the causes of some common HTTP status codes.

|Code|Description|Notes|
|---|---|---|
|200|OK|IIS 7.0 and later versions successfully processed the request.|
|304|Not modified|The client browser requests a document that is already in the cache. And the document hasn't been modified since it was cached. The client browser uses the cached copy of the document instead of downloading the document from the server.|
|400|Bad request|The Hypertext Transfer Protocol Stack (_Http.sys_) file blocks IIS 7.0 and later versions from processing the request because of a problem in the request. Typically, this HTTP status code means that the request contains invalid characters or sequences, or that the request goes against the security settings in the _Http.sys_ file.|
|401.1|Logon failed|The logon attempt is unsuccessful probably because of a user name or a password that is invalid.|
|401.2|Logon failed due to server configuration|This HTTP status code indicates a problem in the authentication configuration settings on the server.|
|401.3|Unauthorized due to ACL on resource|This HTTP status code indicates a problem in the NTFS file system permissions. This problem may occur even if the permissions are correct for the file that you try to access. For example, this problem occurs if the IUSR account doesn't have access to the _C:\Winnt\System32\Inetsrv_ directory.|
|401.4|Authorization failed by filter|An Internet Server Application Programming Interface (ISAPI) filter doesn't let the request be processed because of an authorization problem.|
|401.5|Authorization failed by ISAPI/CGI application|An ISAPI application or a Common Gateway Interface (CGI) application doesn't let the request be processed because of an authorization problem.|
|403.1|Execute access forbidden|The appropriate level of the Execute permission isn't granted.|
|403.2|Read access forbidden|The appropriate level of the Read permission isn't granted. Verify that you have set up IIS 7.0 and later versions to grant the Read permission to the directory. Additionally, if you use a default document, verify that the default document exists.|
|403.3|Write access forbidden|The appropriate level of the Write permission isn't granted. Check the IIS 7.0 and later versions permissions and the NTFS file system permissions. Make sure that they are set up to grant the Write permission to the directory.|
|403.4|SSL required|The request is made over a non-secure channel. But the web application requires a Secure Sockets Layer (SSL) connection.|
|403.5|SSL 128 required|The server is configured to require a 128-bit SSL connection. But, the request isn't sent by using 128-bit encryption.|
|403.6|IP address rejected|The server is configured to deny access to the current IP address.|
|403.7|Client certificate required|The server is configured to require a certificate for client authentication. But the client browser doesn't have an appropriate client certificate installed. For more information, see [HTTP error 403.7 when you run a web application that's hosted on a server that is running IIS 7.0](/troubleshoot/iis/http-error-403-7-forbidden-web-app).|
|403.8|Site access denied|The server is configured to deny requests based on the Domain Name System (DNS) name of the client computer. For more information, see [Dynamic IP Address restrictions](/iis/get-started/whats-new-in-iis-8/iis-80-dynamic-ip-address-restrictions).|
|403.12|Mapper denied access|The page that you want to access requires a client certificate. But, the user ID that is mapped to the client certificate is denied access to the file.|
|403.13|Client certificate revoked|The client browser tries to use a client certificate that was revoked by the issuing certification authority.|
|403.14|Directory listing denied|The server isn't configured to display a content directory listing, and a default document isn't set. For more information, see [HTTP Error 403.14 - Forbidden when you open an IIS Webpage](/troubleshoot/iis/http-403-14-forbidden-webpage).|
|403.16|Client certificate is untrusted or invalid.|The client browser tries to use an invalid client certificate. Or the server that is running IIS 7.0 and later versions doesn't trust the client certificate. For more information, see [HTTP Error 403.16 when you try to access a website that's hosted on IIS 7.0](/troubleshoot/iis/http-403-forbidden-access-website).|
|403.17|Client certificate has expired or is not yet valid.|The client browser tries to use a client certificate that is expired or that isn't yet valid.|
|403.18|Cannot execute requested URL in the current application pool.|A custom error page is configured. And the application pool of the customer error page is different with the application pool of the requested URL.|
|403.19|Cannot execute CGI applications for the client browser in this application pool.|The identity of the application pool doesn't have the Replace a process level token user right.|
|404.0|Not found.|The file that you try to access is moved or doesn't exist.|
|404.2|ISAPI or CGI restriction.|The requested ISAPI resource or the requested CGI resource is restricted on the computer. For more information, see [HTTP Error 404.2 when you visit a web page that is hosted on a computer that is running IIS 7.0](/troubleshoot/iis/http-error-402-webpage).|
|404.3|MIME type restriction.|The current MIME mapping for the requested extension type is invalid or isn't configured.|
|404.4|No handler configured.|The file name extension of the requested URL doesn't have a handler that is configured to process the request on the Web server.|
|404.5|Denied by request filtering configuration.|The requested URL contains a character sequence that is blocked by the server.|
|404.6|Verb denied.|The request is made by using an HTTP verb that isn't configured or that isn't valid.|
|404.7|File extension denied.|The requested file name extension isn't allowed.|
|404.8|Hidden namespace.|The requested URL is denied because the directory is hidden.|
|404.9|Files attribute hidden.|The requested file is hidden.|
|404.10|Request header too long.|The request is denied because the request headers are too long.|
|404.11|Request contains double escape sequence.|The request contains a double escape sequence.|
|404.12|Request contains high-bit characters.|The request contains high-bit characters, and the server is configured not to allow high-bit characters.|
|404.13|Content length too large.|The request contains a `Content-Length` header. The value of the `Content-Length` header is larger than the limit that is allowed for the server. For more information, see [HTTP Error 404.13 - CONTENT_LENGTH_TOO_LARGE when you visit a web site that is hosted on a server that is running IIS 7.0](/troubleshoot/iis/http-404-13-website).|
|404.14|Request URL too long.|The requested URL exceeds the limit that is allowed for the server.|
|404.15|Query string too long.|The request contains a query string that is longer than the limit that is allowed for the server.|
|404.17|Dynamic content mapped to the static file handler.| For more information, see [Error message when you visit a Web site that is hosted on IIS 7.0: HTTP Error 404.17 - Not Found](https://support.microsoft.com/help/2019689/error-message-when-you-visit-a-web-site-that-is-hosted-on-iis-7-0-http).|
|405.0|Method not allowed.|The request is made by using an HTTP method that isn't valid. For more information, see [HTTP Error 405.0 when you visit a website that is hosted on a server that is running IIS](/troubleshoot/iis/http-error-405-website).|
|406.0|Invalid MIME type.|The request is made by using an `Accept` header that contains a MIME value that isn't valid.|
|412.0|Precondition failed.|The request is made by using an `If-Match` request header that contains a value that isn't valid.|
|500|Internal server error.|This HTTP status code may occur for many server-side reasons. For more information, see [HTTP Error 500.0 - Internal Server Error error when you you open an IIS 7.0 Webpage](https://support.microsoft.com/help/942031/http-error-500-0-internal-server-error-error-when-you-you-open-an-iis).|
|500.11|Application is shutting down on the web server.|The request isn't processed because the destination application pool is shutting down. Wait for the worker process to finish shutting down, and then try the request again. If this problem persists, the web application may be experiencing problems that prevent the web application from shutting down correctly.|
|500.12|Application is busy restarting on the web server.|The request isn't processed because the destination application pool is restarting. This HTTP status code should disappear when you refresh the page. If this HTTP status code appears again after you refresh the page, the problem may be caused by antivirus software that is scanning the Global.asa file. If this problem persists, the web application may be experiencing problems that prevent the web application from restarting correctly.|
|500.13|Web server is too busy.|The request isn't processed because the server is too busy to accept any new incoming requests. Typically, this HTTP status code means that the number of incoming concurrent requests exceeds the number that the IIS 7.0 and later versions web application can process. This problem may occur when the performance configuration settings are set too low, the hardware is insufficient, or a bottleneck occurs in the IIS 7.0 and later versions web application. A common troubleshooting method is to generate a memory dump file of the IIS 7.0 and later versions processes when the error is occurring and then to debug the memory dump file.|
|500.15|Direct requests for Global.asax aren't allowed.|A direct request for the _Global.asa_ file or for the _Global.asax_ file is made.|
|500.19|Configuration data is invalid.|This HTTP status code occurs because of a problem in the associated _applicationhost.config_ file or in the associated _Web.config_ file. For more information, see [HTTP Error 500.19 when you open an IIS Webpage](/troubleshoot/iis/http-error-500-19-webpage).|
|500.100|Internal ASP error.|An error occurs during the processing of an Active Server Pages (ASP) page. To obtain more specific information about the error, disable friendly HTTP error messages in the web browser. Additionally, the IIS log may show an ASP error number that corresponds to the error that occurs.|
|503.0|Service unavailable.|The request is sent to an application pool that is currently stopped or disabled. To resolve this issue, make sure that the destination application pool is started. The event log may give information about why the application pool is stopped or disabled.|
|503.2|Concurrent request limit exceeded.|The `appConcurrentRequestLimit` property is set to a value that is lower than the current number of concurrent requests. IIS 7.0 and later versions don't allow more concurrent requests than the value of the `appConcurrentRequestLimit` property.|
  
## HTTP substatus codes added in IIS 8.0

|Subcode|Description|
|---|---|
|400.10|Invalid X-Forwarded-For (XFF) header|
|400.11|Invalid WebSocket request|
  
## HTTP substatus codes added in ARR 3.0.1916

|Subcode|Description|
|---|---|
|400.601|Bad client request (ARR)|
|400.602|Invalid time format (ARR)|
|400.603|Parse range error (ARR)|
|400.604|Client gone (ARR)|
|400.605|Maximum number of forwards (ARR)|
|400.606|Asynchronous competition error (ARR)|
|502.2|Map request failure (ARR)|
|502.3|WinHTTP asynchronous completion failure (ARR)|
|502.4|No server (ARR)|
|502.5|WebSocket failure (ARR)|
|502.6|Forwarded request failure (ARR)|
|502.7|Execute request failure (ARR)|
  
## References

For more information about HTTP status code definitions, see [HTTP/1.1: Status Code Definitions](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html#sec10).  

[!INCLUDE [Third-party disclaimer](../../../../includes/third-party-disclaimer.md)]
