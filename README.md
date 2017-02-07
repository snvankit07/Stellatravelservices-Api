# Stellatravelservices-Api
The StellaTravelGateway (STG) is a integrated multi product webservice providing Air,Ground and Tours Product. It's architecture allows simple and rapid integration to any third party system supporting SOAP webservice calls. 

This document will guide you through the webservice call flow and defines the fields within the messaging protocol. 

All methods work on a request/response message format using standard SOAP messaging. 

Every calling system must initially authenticate using the Authenticate method in the DirectoryService webservice. When successfully authenticated, a token will be returned that must be submitted in every subsequent call. The Token has an expiry time and date that is also returned. Systems must only call authenticate once and reuse the token for all calls for that user. Repeatedly calling authenticate when a token is still avaiable may lead to that system being banned. 

All development and testing should be carried out against following url. You will need to have credentials provided to you by your Business Development Manager.

http://devapi.stellatravelgateway.stellatravelservices.co.uk




Ref Url:http://devapi.stellatravelgateway.stellatravelservices.co.uk/documentation/Default.aspx

