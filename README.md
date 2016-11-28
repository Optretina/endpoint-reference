![](http://www.optretina.com/wp-content/uploads/2014/11/logo-optretina.png)

# Web API Endpoint Reference

Our Web API provides client applications access to OPTretina. Please notice the API still won't cover all situations and features that our platform offers.

Web API Base URL: https://api.optretina.com

## Endpoints

This package provides tools for the following:

- Authentication: [POST] https://api.optretina.com/authorize
- Retrieving a collection of cases: [GET] https://api.optretina.com/cases
- Retrieving a single case: [GET] https://api.optretina.com/cases/{id}
- Getting a report: [GET] https://api.optretina.com/cases/report/{id}
- Creating a case: [POST] https://api.optretina.com/cases

### Authentication

**HTTP Method**: POST

**URL**: https://api.optretina.com/authorize

Param  | Description
------------- | -------------
client_id  | Client identifier
client_secret  | Client Secret hash
grant_type | Constant string 'client_credentials'


#### Example

```
#!bash
curl --data "client_id=<YOUR_CLIENT_ID>&client_secret=<YOUR_CLIENT_SECRET>&grant_type=client_credentials" https://api.optretina.com/authorize
```

### Retrieving a collection of cases

**HTTP Method**: GET

**URL**: https://api.optretina.com/cases

**Authentication**: Required

Param  | Description
------------- | -------------


#### Example

```
#!bash
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://api.optretina.com/cases
```

### Retrieving a single case

**HTTP Method**: GET

**URL**: https://api.optretina.com/cases/{id}

**Authentication**: Required

Param  | Description
------------- | -------------
ID  | Case ID



#### Example

```
#!bash
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://api.optretina.com/cases/<CASE_ID>
```
### Getting a report

**HTTP Method**: GET

**URL**: https://api.optretina.com/cases/report/{id}

**Authentication**: Required

**Returns**: PDF file

Param  | Description
------------- | -------------
ID  | Case ID



#### Example

```
#!bash
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://api.optretina.com/cases/report/<CASE_ID>
```

### Create a case

**HTTP Method**: POST

**URL**: https://api.optretina.com/cases

**Authentication**: Required


#### Example

```
#!bash
curl -H 'Content-Type: application/json' -X POST -d '{"param": "value", "anotherparam": "anotervalue", ..}' https://api.optretina.com/cases
```

Getting Help

We've done our best to write the OPTRETINA API documentation to make integrating with it as simple as possible. Should you have questions, contact us.
Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues.
