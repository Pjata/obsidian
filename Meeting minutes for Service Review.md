## Attendees

- David Judik
- Tamas Laszlo
- Bence Pjatacsuk

## Agenda

Commons: 
- Checking incident reports, no new incidents since last service review
- Checking triggered alerts, found one monitor that was outdated and had to be deleted
- Checking Sentry for new errros, found 2 with 1-1 occurance. Checking it indicates it needs no deeper investigation as it is a one-off error
- Checked for any new incoming bugs, found no new
- Checking Datadog dashboards for trends. Found an increase of reads on the users table, this is due to the new HEAP features
- Checking Snyk for vulnerabilities, found 1 critical/high vulns with mature state, put the ticket to fix on the kanban board

Catalog

- Checking incident reports, no new incidents since last service review
- Checking triggered alerts, found one monitor that was outdated and had to be deleted
- Checking Sentry for new errros, found an error that was due to one schools vuln testing, passing invalid queries and resultin in500s
- Checked for any new / old bugs that are duplicates or already solved. new ones are picked up weekly
- Checking Datadog dashboards for trends. Found some live events in the deatletter queue. Also need to update payment redirector counters, to show the ELB response counts in number format too
- Checking Snyk for vulnerabilities, found one vuln regarding pdf kit that needs action. However we have plans to remove pdfkit altogether in the upcoming quarter.


## Action Items

- https://app.datadoghq.com/monitors/triggered?q=tag%3A%22phoenix%22 Check pensieve alerts if can be deleted, these are created by hand and now we have ones created by roboops
- Pick up the Commons vuln ticket in the upcoming weeks
- Check live events in the dead letter queue
- Update payment redirector dashboard to fix 200s/400s/500s counts
