# Stellatravelservices-Api
The StellaTravelGateway (STG) is a integrated multi product webservice providing Air,Ground and Tours Product. It's architecture allows simple and rapid integration to any third party system supporting SOAP webservice calls. 

This document will guide you through the webservice call flow and defines the fields within the messaging protocol. 

All methods work on a request/response message format using standard SOAP messaging. 

Every calling system must initially authenticate using the Authenticate method in the DirectoryService webservice. When successfully authenticated, a token will be returned that must be submitted in every subsequent call. The Token has an expiry time and date that is also returned. Systems must only call authenticate once and reuse the token for all calls for that user. Repeatedly calling authenticate when a token is still avaiable may lead to that system being banned. 

All development and testing should be carried out against following url. You will need to have credentials provided to you by your Business Development Manager.

http://devapi.stellatravelgateway.stellatravelservices.co.uk

DirectoryService 
http://devapi.stellatravelgateway.stellatravelservices.co.uk/DirectoryService.svc



Authenticate

Authenticates the calling system to the gateway.

AirService 
http://devapi.stellatravelgateway.stellatravelservices.co.uk/AirService.svc



Search

Main search method for flights.

CheckAvailability

Checks the availability of flights from a fares search.

ConfirmFlightDetails

Confirms the availability and price of an availability flight result.

Book

Books an availability result.

GetAirportOrCityList

Returns a list of Airports or Cities supported using a prefix.

GetAllAirlines

Returns a list of supported Airlines that can be used in the search.

GetConditions

Returns the flight conditions for an availability result.

AvailableOnDeposit

Returns Deposit information (including whether or not that deposit is available) for the BookFlightDetails request

GetOSIMessages

Returns OSI Messages for the given request - including if the message should be treated as dynamic

Timeout information:

CloseTimeout="00:01:00" OpenTimeout="00:03:00" ReceiveTimeout="00:10:00" SendTimeout="00:03:00"

GroundService 
http://devapi.stellatravelgateway.stellatravelservices.co.uk/GroundService.svc



SearchHotels

Main method to search for hotels.

SearchTransfers

Main method to search for transfers, can be standalone or associtated with a hotel search result.

GetHotelDetails

Returns detailed information on the hotel.

GetCancellationPolicies

Returns the hotel dynamic cancellation policy.

Book

Books hotels and tranfers from the search results.

GetGeography

Returns the complete set of geography data applicable to ground.

AvailableOnDeposit

Returns Deposit information (including whether or not that deposit is available) for the GroundBookingDetails request

Timeout information:

CloseTimeout="00:01:00" OpenTimeout="00:01:00" ReceiveTimeout="00:10:00" SendTimeout="00:01:00"

CRMService 
http://devapi.stellatravelgateway.stellatravelservices.co.uk/CRMService.svc



GetBookingDocument

Retrieves a pdf voucher for the requested booking

RetrieveBooking

Retrieves the details of the requested booking

GetUpdatedBookingList

Retrieves the details of the bookings which have been updated
