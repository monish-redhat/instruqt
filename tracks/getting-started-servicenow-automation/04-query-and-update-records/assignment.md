---
slug: query-and-update-records
id: mec4mlotoknj
type: challenge
title: Query and update records
teaser: Query and update multiple records of multiple types
notes:
- type: text
  contents: |-
    **Did you know?**
    Due to enhanced readability and the plain text nature of Ansible content, infrastructure as code is easily attainable using Ansible.
tabs:
- title: VS Code
  type: service
  hostname: controller
  path: /editor/?folder=vscode-remote%3A%2F%2F%2fhome%2Frhel%2Fservicenow_project
  port: 443
- title: Automation controller
  type: service
  hostname: controller
  port: 443
- title: ServiceNow
  type: website
  hostname: controller
  url: https://ansible.service-now.com
  new_window: true
difficulty: basic
timelimit: 400
---
Finally, lets assume that our fictional board meeting that was holding up the reboot of the webserver has now completed and we can safely perform our change request and update the status of the problem and incident to indicate that everything has been resolved.

To do this, inspect the playbook `close-records-by-user.yml` in VS Code. There are a few new modules here. These `*_info` modules are being used to query for different record types (incident, problem, and change_request) for active records created by your username. Ansible then transforms these returned records into simple lists of objects and passes the lists to their respective modules to update/close the records. For any fields not implemented by the module itself, there is a module parameter called `other` that can be used to specify any other field or custom fields for that particular table.

To perform this automation:
- Launch the job template `4 - Query and close records by user (close-records-by-user.yml` in automation controller
- Monitor the output of the job template and wait for the job to complete

Once the job completes, all records that you had created in previous challenges should be closed or removed! The job output should show all the relevant record numbers that were cleaned up. Refresh your views in ServiceNow to see the updates.

Now that everything has been cleaned up, move onto the next challenge!