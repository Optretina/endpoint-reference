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
curl -H "Authorization: Bearer <YOUR_TOKEN>" https://api.optretina.com/cases
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
curl -H "Authorization: Bearer <YOUR_TOKEN>" https://api.optretina.com/cases/<CASE_ID>
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
curl -H "Authorization: Bearer <YOUR_TOKEN>" https://api.optretina.com/cases/report/<CASE_ID>
```

### Create a case

**HTTP Method**: POST

**URL**: https://api.optretina.com/cases

**Authentication**: Required

**Valid params:

Param  | Type
------------- | -------------
history_number  | String
first_name  | String
last_name  | String
gender  | 0: MALE, 1: FEMALE
age  | number
diabetes  | // 0: no, 1: yes
visit_date  | YYYY-MM-DD
visit_reason  | String
ophthalmic_antecedents  | String
other_relevant_info  | String
retinologist_notes  | String
od_iop  | float
od_va  | float
od_axis  | float
od_cylinder  | float
od_sphere  | float
od_add  | float
od_prism  | float
od_prism_base  | float
os_iop  | float
os_va  | float
os_axis  | float
os_cylinder  | float
os_sphere  | float
os_add  | float
os_prism  | float
os_prism_base  | float
callback_url | URL
images | Array files

#### Example

```
#!bash
curl  -H "Authorization: Bearer <YOUR_TOKEN>" --form "images[]=@<PATH_IMAGE>;filename=<FILE_NAME>" --form "images[]=<PATH_IMAGE_2>;filename=<FILE_NAME_2>" --form first_name=<PATIENT_NAME> --form last_name=<PATIENT_LAST_NAME> --form gender=<GENDER>  --form age=<AGE> --form paramName=paramValue ... https://api.optretina.com/cases
```

Getting Help

We've done our best to write the OPTRETINA API documentation to make integrating with it as simple as possible. Should you have questions, contact us.
Help us make it better

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please use GitHub issues.
