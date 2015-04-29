# Request

The request API allows the user to perform all kinds of operation on the requests.

The attributes that are available in the input and return json for the request module are as follows.

### Base Fields

Attribute |	Type | Details
--------- | ---- | -------
requestid|Integer|Id of the request
requestType|String|Type of the request
impact|String|Impact of the request
status|String|Status of the request
impactdetails|String|Description about the impact of the request
mode|String|Mode of the request
urgency|String|Urgency of the request
level|String|Level of the request
priority|String|Priority given to the request
requesterdetails|String|Details about the requester who requested the request
category|String|Category to which the request belongs
group|String|Group to which the request belongs
subcategory|String|Subcategory to which the request belongs
technician|String|Technician assigned to the request
item|String|Item of the request
service|String|Service category to which the request belongs
emailcc|Email|Email id(s) to Notify
subject|String|Subject of the request
description|String|Description of the request
createddate|Date|Date at which the request is created
respondeddate|Date|Date at which the request is responded
duebydate|Date|Date at which the request scheduled be to completed
completeddate|Date|Date at which the request is really completed
resolveddate|Date|Date at which the request is resolved
frduebydate|Date|Date at which the response for the request is scheduled
attachment|File|Attachments associated to the request
reason|String|Reason associated to the request

### Additional Fields - examples

Additional fields alias which are given is for better understanding. The actual additional field alias name may be different in application

Attribute | Type | Details
--------- | ---- | -------
Employee ID	| Integer|Additional data with numeric type
Employee Designation|String|Additional data with string type
Site|Pick list|Additional data with pick list type
Employee Details|Multiline|Additional data with multiline type
Scheduled time|Date/time|Additional data with date/time type
Points earned|Decimal|Additional data with decimal type


## Add New Request

> POST /sdpapi/request/

```text
Request Example :
```
```json
{
    "operation": {
        "details": {
            "requester": "Shawn Adams",
            "subject": "Specify Subject",
            "description": "Specify Description",
            "requesttemplate": "Unable to browse",
            "priority": "High",
            "site": "New York",
            "group": "Network",
            "technician": "Howard Stern",
            "level": "Tier 3",
            "status": "open",
            "service": "Email"
        }
    }
}
```
```text
Response Example :
```
```json
{
    "operation": {
        "result": {
            "status": "Success",
            "message": "Request details added successfully."
        },
        "Details": {
            "WORKORDERID": "4",
            "REQUESTER": "Shawn Adams",
            "CREATEDBY": "administrator",
            "CREATEDTIME": "1429274762907",
            "DUEBYTIME": "1429504200907",
            "RESPONSEDUEBYTIME": "-1",
            "FR_DUETIME": "-1",
            "RESPONDEDTIME": "0",
            "RESOLVEDTIME": "0",
            "COMPLETEDTIME": "0",
            "SHORTDESCRIPTION": "Specify Description",
            "TIMESPENTONREQ": "0hrs 0min",
            "SUBJECT": "Specify Subject",
            "REQUESTTEMPLATE": "Unable to browse",
            "MODE": "E-Mail",
            "SLA": "High SLA",
            "ASSET": "",
            "DEPARTMENT": "",
            "SITE": "",
            "ISVIPUSER": "No",
            "SERVICE": "Email",
            "CATEGORY": "Internet",
            "SUBCATEGORY": "",
            "ITEM": "",
            "TECHNICIAN": "Howard Stern",
            "STATUS": "Open",
            "PRIORITY": "High",
            "LEVEL": "Tier 3",
            "IMPACT": "",
            "URGENCY": "",
            "IMPACTDETAILS": "",
            "REQUESTTYPE": "",
            "CLOSURECODE": "",
            "CLOSURECOMMENTS": "",
            "YETTOREPLYCOUNT": "",
            "GROUP": "Network"
        }
    }
}
```

Along with the input details, the operation name as given below should be passed as an input parameter

<aside class="notice">OPERATION_NAME=ADD_REQUEST</aside>

## View All Requests

> POST : /sdpapi/request/

```text
Request Example :
```
```json
{
    "operation": {
        "details": {
            "from": "0",
            "limit": "50",
            "filterby": "Open_System"
        }
    }
}
```
```text
Response Example :
```
```json
{
    "operation": {
        "name": "GET_REQUESTS",
        "module": "GET_REQUESTS",
        "result": {
            "status": "Success",
            "message": "WorkOrder Details Retrieved Successfully"
        },
        "details": [
            {
                "WORKORDERID": 4,
                "REQUESTER": "Shawn Adams",
                "CREATEDBY": "administrator",
                "CREATEDTIME": 1429274762907,
                "DUEBYTIME": 1429504200907,
                "SUBJECT": "Specify Subject",
                "TECHNICIAN": "Howard Stern",
                "PRIORITY": "High",
                "STATUS": "Open",
                "ISOVERDUE": "false"
            },
            {
                "WORKORDERID": 3,
                "REQUESTER": "Shawn Adams",
                "CREATEDBY": "administrator",
                "CREATEDTIME": 1429269284515,
                "DUEBYTIME": 1429272884515,
                "SUBJECT": "Specify Subject",
                "TECHNICIAN": "Howard Stern",
                "PRIORITY": "High",
                "STATUS": "Open",
                "ISOVERDUE": "true"
            }
        ],
        "resources": []
    }
}
```

This fetches the list of requests based on the filter passed through the filterby parameter.

The list of parameters that can be passed in the INPUT_DATA include,

Param | Value | Details
--------- | ----- | -------
from | [ 0 ] | **Numeric** <br>Indicates the row index from which the data needs to be fetched. If not specified, 0 will be used.
limit | [ 50 ] | **Numeric** <br>Indicates the number of requests that needs to be fetched starting from the record specified by the from parameter. If not specified, 50 records would be fetched. If the value specified exceeds 250, then 250 will be used as the limit.
filterby | [Open_System] | **String** <br>Indicates the view based on which the requests needs to be fetched. If not specified, Open Requests would be fetched. The filter's that are available for the requests view can be fetched through the API <a href="#get-requests-filters">Get Request Filters</a>. If no value is passed for the filterby parameter, then all the requests in the system would be fetched based on the range entered.


## Get Requests Filters

> POST /sdpapi/request/

```text
Response Example :
```
```json
{
    "operation": {
        "result": {
            "status": "Success",
            "message": "Request Filters retreived properly"
        },
        "Details": [
            {
                "VIEWID": "MyOpen_Or_Unassigned",
                "VIEWNAME": "My Open Or Unassigned"
            },
            {
                "VIEWID": "Unassigned_System",
                "VIEWNAME": "Unassigned Requests"
            },
            {
                "VIEWID": "Open_User",
                "VIEWNAME": "My Open Requests"
            },
            {
                "VIEWID": "Onhold_User",
                "VIEWNAME": "My Requests On Hold"
            },
            {
                "VIEWID": "Overdue_User",
                "VIEWNAME": "My Overdue Requests"
            },
            {
                "VIEWID": "All_Pending_User",
                "VIEWNAME": "My Pending Requests"
            },
            {
                "VIEWID": "All_Pending_Requests_Tasks_User",
                "VIEWNAME": "My Pending Requests or Tasks"
            },
            {
                "VIEWID": "Due_Today_User",
                "VIEWNAME": "My Requests Due Today"
            },
            {
                "VIEWID": "All_Completed_User",
                "VIEWNAME": "My Completed Requests"
            },
            {
                "VIEWID": "My_Pending_Approval",
                "VIEWNAME": "Requests Pending My Approval"
            },
            {
                "VIEWID": "All_User",
                "VIEWNAME": "All My Requests"
            },
            {
                "VIEWID": "Open_System",
                "VIEWNAME": "Open Requests"
            },
            {
                "VIEWID": "Onhold_System",
                "VIEWNAME": "Requests On Hold"
            },
            {
                "VIEWID": "Overdue_System",
                "VIEWNAME": "Overdue Requests"
            },
            {
                "VIEWID": "Overdue_System_Today",
                "VIEWNAME": "Requests Due Today"
            },
            {
                "VIEWID": "Pending_Approval",
                "VIEWNAME": "Requests Pending Approval"
            },
            {
                "VIEWID": "All_Pending",
                "VIEWNAME": "Pending Requests"
            },
            {
                "VIEWID": "All_Completed",
                "VIEWNAME": "Completed Requests"
            },
            {
                "VIEWID": "Waiting_Update",
                "VIEWNAME": "Waiting for my update"
            },
            {
                "VIEWID": "Updated_By_Me",
                "VIEWNAME": "Updated by me"
            },
            {
                "VIEWID": "All_Requests",
                "VIEWNAME": "All Requests"
            }
        ]
    }
}
```

This fetches the list of requests based on the filter passed through the filterby parameter.

Parameter | Mandatory | Value | Details
--------- | --------- | ----- | -------
OPERATION_NAME|true|GET_REQUEST_FILTERS
TECHNICIAN_KEY|true| < Unique Key > | The key of the technician who is going to perform the operation.
format | false | json | If not specified, xml format will be returned

