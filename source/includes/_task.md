# Task

Task is a smaller piece of work can be done by a member of a team.

## Adding a Task

> POST <server-url>/sdpapiv2/tasks/


```text
Request Example :
```
```json
{
        "task":
        {
            "actual_starttime": "1428949800000",
            "scheduled_starttime": "1428949800000",
            "scheduled_endtime": "1429122540000",
            "actual_endtime": "1429036140000",
            "created_date": "1429087775290",
            "additional_cost": 67,
            "percentage_completion": 45,
            "estimated_effort_days": "1",
            "estimated_effort_hours": "2",
            "estimated_effort_minutes": "30",
            "task_type": {
                "name": "Implementation"
            },
            "associated_entity_id": 6,
            "entity": "request",
            "title": "Change the phone number mapping",
            "description": "To change the phone number mapping",
            "status": {
                "name": "Open"
            },
            "priority": {
                "name": "High"
            },
            "owner": {
                "name": "Heather Graham"
            },
            "group": {
                "name": "Hardware Problems"
            }
        }
}
```
```text
Response Example :
```
```json
{
    "task": [
        {
            "task_id": 2,
            "actual_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_endtime": {
                "value": 1429122540000,
                "display_value": "Apr 15, 2015 11:59 PM"
            },
            "actual_endtime": {
                "value": 1429036140000,
                "display_value": "Apr 14, 2015 11:59 PM"
            },
            "created_date": {
                "value": 1429087775290,
                "display_value": "Apr 15, 2015 02:19 PM"
            },
            "additional_cost": 67,
            "percentage_completion": 45,
            "created_by": {
                "id": 3,
                "name": "administrator"
            },
            "estimated_effort_days": "1 Days ",
            "estimated_effort_hours": "2 Hours",
            "estimated_effort_minutes": "30 Mins",
            "task_type": {
                "id": 2,
                "name": "Implementation"
            },
            "marked_owner": null,
            "marked_group": null,
            "associated_entity_id": 6,
            "projectid": null,
            "milestoneid": null,
            "entity": "request",
            "comment": null,
            "title": "Change the phone number mapping",
            "description": "To change the phone number mapping",
            "status": {
                "id": 1,
                "name": "Open"
            },
            "priority": {
                "id": 4,
                "name": "High"
            },
            "owner": {
                "id": 6,
                "name": "Heather Graham"
            },
            "group": {
                "id": 1,
                "name": "Hardware Problems"
            }
        }
    ],
    "response_status": {
        "id": "2",
        "status": "Success",
        "messages": [
            {
                "type": "Success",
                "message": "New Task added successfully.",
                "statuscode": "5002"
            }
        ]
    }  
}
```

Attribute | Details
--------- | -------
title |	**String**<br>Title of the task
status|	**Json object**<br>Status of the task. The JSON Object has "id" and/or "name" of the status.<br>E.g "status": {"name": "Open"}
group |	**String**<br>Group to which the task belongs
owner | **Json object**<br>Owner of the task. JSON Object has the "id" and "name" of the owner.<br>E.g. "owner":{"id":3}
associated_entity_id |	**Integer**<br>Id of the entity to which the task is associated
scheduled_starttime |	**Json object**<br>Scheduled Date and time to start task. JSON Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "scheduled_starttime":{"value":1428477462973}
scheduled_endtime |	**Json object**<br>Scheduled Date and time to end task.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "scheduled_endtime":{"value":1428477462973}
percentage_completion | **Integer**<br>% of completion
actual_starttime | **Json object**<br>Actual Date and time task started.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "actual_starttime":{"value":1428477462973}
actual_endtime	| **Json object**<br>Actual Date and time task ended.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "actual_endtime":{"value":1428477462973}
additional_cost	| **Integer**<br>Additional cost
priority | **Json object**<br>Priority of task. JSON Object has "id" and/or "name" of the priority.<br>E.g "priority":{"id":2}
task_type |	**Json object**<br>Task type. JSON Object has "id" and/or "name" of the task type.<br>E.g "task_type":{"id":2}
description | **String**<br>Description
estimated_effort_days |	**Integer**<br>Estimated number of days to finish task
estimated_effort_hours | **Integer**<br>Estimated number of hours to finish task
estimated_effort_minutes |	**Integer**<br>Estimated number of minutes to finish task
task_id	| **Integer**<br>Id of the task
created_date | **Json object**<br>Date and time on which the task is created. This object has the "value" in milliseconds and "display_value" in the standard date format.
created_by | **Json object**<br>Name and Id of the technician who created this task is present in the JSON format
marked_owner | **Json object**<br>Name of the technician to whom the task is marked. JSON Object has the "id" and "name" of the owner.<br>E.g. "marked_owner":{"id":3}
marked_group | **String**<br>Group to which the task is marked
projectid | **Integer**<br>Id of project which the task belongs to.
milestoneid | **Integer**<br>Id of the milestone which the task belongs to.
entity	| **String**<br>Name of the module(Entity) of parent of the task
comment	| **String**<br>Comment added for the task

## Fetching a Task

> GET <server-url>/sdpapiv2/tasks/2

```text
Response Example :
```
```json
{
    "task": [
        {
            "task_id": 2,
            "actual_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_endtime": {
                "value": 1429122540000,
                "display_value": "Apr 15, 2015 11:59 PM"
            },
            "actual_endtime": {
                "value": 1429036140000,
                "display_value": "Apr 14, 2015 11:59 PM"
            },
            "created_date": {
                "value": 1429087775290,
                "display_value": "Apr 15, 2015 02:19 PM"
            },
            "additional_cost": 67,
            "percentage_completion": 45,
            "created_by": {
                "id": 3,
                "name": "administrator"
            },
            "estimated_effort_days": "1 Days ",
            "estimated_effort_hours": "2 Hours",
            "estimated_effort_minutes": "30 Mins",
            "task_type": {
                "id": 2,
                "name": "Implementation"
            },
            "marked_owner": null,
            "marked_group": null,
            "associated_entity_id": 6,
            "projectid": null,
            "milestoneid": null,
            "entity": "request",
            "comment": null,
            "title": "Change the phone number mapping",
            "description": "To change the phone number mapping",
            "status": {
                "id": 1,
                "name": "Open"
            },
            "priority": {
                "id": 4,
                "name": "High"
            },
            "owner": {
                "id": 6,
                "name": "Heather Graham"
            },
            "group": {
                "id": 1,
                "name": "Hardware Problems"
            }
        }
    ],
    "response_status": {
        "id": "2",
        "status": "Success",
        "messages": [
            {
                "type": "Success",
                "message": "New Task added successfully.",
                "statuscode": "5002"
            }
        ]
    }  
}
```

Attribute | Details
--------- | -------
title |	**String**<br>Title of the task
status|	**Json object**<br>Status of the task. The JSON Object has "id" and/or "name" of the status.<br>E.g "status": {"name": "Open"}
group |	**String**<br>Group to which the task belongs
owner | **Json object**<br>Owner of the task. JSON Object has the "id" and "name" of the owner.<br>E.g. "owner":{"id":3}
associated_entity_id |	**Integer**<br>Id of the entity to which the task is associated
scheduled_starttime |	**Json object**<br>Scheduled Date and time to start task. JSON Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "scheduled_starttime":{"value":1428477462973}
scheduled_endtime |	**Json object**<br>Scheduled Date and time to end task.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "scheduled_endtime":{"value":1428477462973}
percentage_completion | **Integer**<br>% of completion
actual_starttime | **Json object**<br>Actual Date and time task started.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "actual_starttime":{"value":1428477462973}
actual_endtime	| **Json object**<br>Actual Date and time task ended.Object has the "value" in milliseconds and "display_value" in the standard date format.<br>E.g "actual_endtime":{"value":1428477462973}
additional_cost	| **Integer**<br>Additional cost
priority | **Json object**<br>Priority of task. JSON Object has "id" and/or "name" of the priority.<br>E.g "priority":{"id":2}
task_type |	**Json object**<br>Task type. JSON Object has "id" and/or "name" of the task type.<br>E.g "task_type":{"id":2}
description | **String**<br>Description
estimated_effort_days |	**Integer**<br>Estimated number of days to finish task
estimated_effort_hours | **Integer**<br>Estimated number of hours to finish task
estimated_effort_minutes |	**Integer**<br>Estimated number of minutes to finish task
task_id	| **Integer**<br>Id of the task
created_date | **Json object**<br>Date and time on which the task is created. This object has the "value" in milliseconds and "display_value" in the standard date format.
created_by | **Json object**<br>Name and Id of the technician who created this task is present in the JSON format
marked_owner | **Json object**<br>Name of the technician to whom the task is marked. JSON Object has the "id" and "name" of the owner.<br>E.g. "marked_owner":{"id":3}
marked_group | **String**<br>Group to which the task is marked
projectid | **Integer**<br>Id of project which the task belongs to.
milestoneid | **Integer**<br>Id of the milestone which the task belongs to.
entity	| **String**<br>Name of the module(Entity) of parent of the task
comment	| **String**<br>Comment added for the task

## Fetching Tasks

To get all the tasks based on filters.

> GET <server-url>/sdpapiv2/tasks/


```text
Request Example :
```
```json
{
    "list_info": {
        "row_count": "3",
        "start_index": "1",
        "end_index": "2",
        "fields_required": "[get_all]",
        "sort_column": "status",
        "sort_order": "A"
    },
    "tasks": {
        "entity": "request",
        "associated_entity_id": "6",
        "filter": "PENDING"
    }
}
```
```text
Response Example :
```
```json
{
    "tasks": [
        {
            "title": "Change the phone number mapping",
            "status": {
                "id": "1",
                "name": "Open"
            },
            "priority": {
                "id": "4",
                "name": "High"
            },
            "owner": {
                "id": "6",
                "name": "Heather Graham"
            },
            "scheduled_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_endtime": {
                "value": 1429122540000,
                "display_value": "Apr 15, 2015 11:59 PM"
            },
            "percentage_completion": "45",
            "actual_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "actual_endtime": {
                "value": 1429036140000,
                "display_value": "Apr 14, 2015 11:59 PM"
            },
            "entity": "Request",
            "group": {
                "id": "1",
                "name": "Hardware Problems"
            },
            "created_by": {
                "id": "3",
                "name": "administrator"
            },
            "estimated_effort": "1 Days ",
            "task_type": {
                "id": "2",
                "name": "Implementation"
            },
            "additional_cost": "67.0",
            "description": "To change the phone number mapping",
            "task_id": "2"
        },
        {
		...
        }
    ],
    "list_info": {
        "row_count": "3",
        "total_count": "2",
        "start_index": "1",
        "end_index": "2",
        "page_number": "1",
        "fields_required": [
            "get_all"
        ],
        "sort_field": "-",
        "search_fields": {}
    },
    "response_status": {
        "status": "Success",
        "messages": [
            {
                "type": "Success",
                "message": "List view fetched successfully",
                "statuscode": "200"
            }
        ]
    }
}
```

Attribute | Details
--------- | -------
row_count |	numeric values
entity |	request, problem, change, project, milestone, general
associated_entity_id |	numeric values
filter |	MYOPEN, MYOVERDUE, MYDUETODAY, MYALLTASKS, OPEN, OVERDUE, PENDING, DUETODAY, GROUPTASKS, UNASSIGNEDTASKS, ALLTASKS
search_columns |	searchable columns in task list
sort_column |	any sortable column in task list
sort_order |	A, D
fields_required |	list of task columns or "[task_id,title,status]" (for specific requirement alone)
start_index |	numeric value
end_index |	numeric value

## Updating a Task

> PUT <server-url>/sdpapiv2/tasks/5


```text
Request Example :
```
```json
{
    "task": {
        "title": "Title Modified",
        "status": {
            "name": "On Hold"
        }
    }
}
```
```text
Response Example :
```
```json
{
    "task": [
        {
            "task_id": 2,
            "actual_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_endtime": {
                "value": 1429122540000,
                "display_value": "Apr 15, 2015 11:59 PM"
            },
            "actual_endtime": {
                "value": 1429036140000,
                "display_value": "Apr 14, 2015 11:59 PM"
            },
            "created_date": {
                "value": 1429087775290,
                "display_value": "Apr 15, 2015 02:19 PM"
            },
            "additional_cost": 67,
            "percentage_completion": 45,
            "created_by": {
                "id": 3,
                "name": "administrator"
            },
            "estimated_effort_days": "1 Days ",
            "estimated_effort_hours": null,
            "estimated_effort_minutes": null,
            "task_type": {
                "id": 2,
                "name": "Implementation"
            },
            "marked_owner": null,
            "marked_group": null,
            "associated_entity_id": 6,
            "projectid": null,
            "milestoneid": null,
            "entity": "request",
            "comment": null,
            "title": "Title Modified",
            "description": "To change the phone number mapping",
            "status": {
                "id": 2,
                "name": "Onhold"
            },
            "priority": {
                "id": 4,
                "name": "High"
            },
            "owner": {
                "id": 6,
                "name": "Heather Graham"
            },
            "group": {
                "id": 1,
                "name": "Hardware Problems"
            }
        }
    ],
    "response_status": {
        "id": "2",
        "status": "Success",
        "messages": [
            {
                "type": "Success",
                "message": "Task details updated successfully.",
                "statuscode": "5003"
            }
        ]
    }
}
```

## Deleting a Task

> DELETE <server-url>/sdpapiv2/tasks/1


```text
Response Example :
```
```json
{
    "task": [
        {
            "task_id": 1,
            "actual_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_starttime": {
                "value": 1428949800000,
                "display_value": "Apr 14, 2015 12:00 AM"
            },
            "scheduled_endtime": {
                "value": 1429101000000,
                "display_value": "Apr 15, 2015 06:00 PM"
            },
            "actual_endtime": {
                "value": 1429122540000,
                "display_value": "Apr 15, 2015 11:59 PM"
            },
            "created_date": {
                "value": 1429087504214,
                "display_value": "Apr 15, 2015 02:15 PM"
            },
            "additional_cost": 34,
            "percentage_completion": 45,
            "created_by": {
                "id": 3,
                "name": "administrator"
            },
            "estimated_effort_days": "2 Days ",
            "estimated_effort_hours": null,
            "estimated_effort_minutes": null,
            "task_type": {
                "id": 2,
                "name": "Implementation"
            },
            "marked_owner": null,
            "marked_group": null,
            "associated_entity_id": null,
            "projectid": null,
            "milestoneid": null,
            "entity": "general",
            "comment": null,
            "title": "sample",
            "description": null,
            "status": {
                "id": 1,
                "name": "Open"
            },
            "priority": {
                "id": 4,
                "name": "High"
            },
            "owner": {
                "id": 6,
                "name": "Heather Graham"
            },
            "group": null
        }
    ],
    "response_status": {
        "id": "1",
        "status": "Success",
        "messages": [
            {
                "type": "Success",
                "message": "Task deleted successfully",
                "statuscode": "5004"
            }
        ]
    }
}
```

