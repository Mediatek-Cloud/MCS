# API References

MediaTek Cloud Sandbox (MCS) have exposed RESTful APIs allowing you to build applications and services that is able to make meaningful communications with MCS for DataPoint upload and retrieves as well as requesting MCS to make TCP socket commands. MCS also based on the communication data uploaded, especially for time-series based data, translate into visual charts for easier reading to the users.

###Access Point

MCS has made all its RESTful API access point as below:

```
https://api.mediatek.com/v2
```

###Parameters

Parameters follows right after the access point used to identify a specific resource as part of the URL construct:

```
https://api.mediatek.com/v2/devices/{deviceId}/retrieveDataPoints

```
In the example above, the deviceId was specified in the URL. For any requests, any parameters not included as part of the URL should be encoded as JSON or CSV with a `content -Type` of `application/json` or `application/csv`.

###Client Errors

Mediatek Cloud Sandbox (MCS) uses the standard HTTP status code to indicate if an API request is succussful or fail. Here states the standard HPPT status code the user may encounter:

**200 OK** - Request Successfully.

**201 Created **- The request has been fulfilled and a new resource is being created.

**202 Accepted** - The request has been accepted for processing, but the process has not yet been completed.

**204 No Content** - The server successfully processed the request, but is not returning any content. Usually used as a response to a successful delete request.

**400 Bad Request** - The server cannot process the request due to the client given parameter is not what the server expected to receive.

**401 Unauthorized** - Authotization is required and has failed or not been provided. A header for Authorization is required.

**403 Forbidden** - The server is refusing to respond to a valid request.

**404 Not Found** - The request resource could not be found.

**405 Method Not Allowed** - The request was made of a resource using a not supported method.

**500, 502 Server Error** - Something went wrong with the MCS server.


###HTTP Verbs

The Mediatek Cloud Sandbox (MCS) provides the following types of API:


**GET** - Used for retrieving resource.

**POST** - Used for creating resouce.

**PUT** - Used for updating resource.

**DELETE** - Used for deleting resource.



###Authentication

All request sent to the API need to be authenticated. A bearer token for Authentication key in the HTTP header is required. If not provided, the server will respond with a 401 Unauthorized message.

###API Keys

Each time a product is created, a data channel is created or a device is added, there will be an unique key assigned to each product, data channel or device. This unique key is not editable, but they can be used to access data which they are associated. They cannot access data from any other resource.

The developer can define which HTTP methods(GET, POST, PUT, DELETE) can be used with each API key. For example, in the Sandnox API, if you need to GET data from a specific data channel or product, you will need to use the Key for the data channel and the product.


###Resources

Following is a shortlist of useful terms of MCS:


####DataChannels

The data channel is a logical placeholder in the cloud for data generated either coming from a specific component of a physical device, or a command coming from the cloud intended to push into a specific component of the connected physical device. Simply put, data channel is designed for one-way or two-way communications between the cloud and the connected physical device.

MCS provides several Sandbox API for the user to easily create data channel,  retrieve data from the data channels and update the data channel.

####Devices

We will have two types of devices in the MCS, the first kind is the test device. The test device is for the developer to use to test the functionality of the product before release.
The second kind of device is the batch create devices created after a product is released and is used for the end user.

MCS also provides APIs for both develoer and the user. For example, to create device, retrieve data from device and remote contol using the device.

####Product

A product is the service that you are going to deliver as a deliverable in the end. The MSC also provides several APIs for the developers to make use of regarding the product. The developer will add data channels in a product and test the product by creating the test device before release.


