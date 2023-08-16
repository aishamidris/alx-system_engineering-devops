POSTMORTEM REPORT ON AN OUTAGE THAT OCCURRED ON THE 10TH OF AUGUST, 2023



Issue Summary:

Duration: August 10, 2023, 14:45 GMT - August 11, 2023, 03:30 GMT Impact: Service degradation affecting our online marketplace platform. User Experience: Users experienced slow page loading, delayed transactions, and intermittent errors. Approximately 20% of users were affected.

Root Cause:
The root cause of the outage was identified as a database deadlock situation triggered by a code update. This led to excessive resource contention and slowed down critical database queries.

Timeline:
August 10, 2023, 14:45 GMT: Issue detected via monitoring alert showing increased response times.
August 10, 2023, 14:50 GMT: Engineering team engaged to investigate the performance degradation, suspecting database issues.
August 10, 2023, 15:15 GMT: Initial investigation focused on database performance optimizations.
August 10, 2023, 17:30 GMT: Misleading assumption made about increased network latency, leading to unnecessary network diagnostics.
August 10, 2023, 20:00 GMT: Issue escalated to senior database administrators as slow performance persisted.
August 10, 2023, 22:30 GMT: Database administrators identified a deadlock situation and started resolving it.
August 11, 2023, 03:30 GMT: The deadlock was resolved, and service performance gradually returned to normal.

Root Cause and Resolution:
The root cause was an unintended code change that introduced a transactional deadlock in the database. This occurred due to an application code update that altered the order of operations in a critical transaction. As a result, two concurrent transactions were locking each other's resources, leading to a deadlock scenario.
To resolve the issue, the engineering team rolled back the problematic code change and applied a hotfix to prevent similar situations in the future. Additionally, database query. 
optimizations were implemented to reduce the chances of resource contention and deadlocks.
Corrective and Preventative Measures:
Improve code review and testing processes to catch unintended consequences of code changes.
Implement stricter database transaction management guidelines to avoid deadlocks.
Enhance monitoring and alerting mechanisms to quickly identify and respond to similar performance degradation issues.
Conduct thorough post-incident reviews to identify areas for improvement and knowledge sharing among teams.

Tasks to Address the Issue:
Conduct a comprehensive code review of recent changes to identify potential unintended consequences.
Review and enhance database transaction handling to prevent deadlock scenarios.
Implement additional automated tests to catch performance regressions during the development phase.
Enhance monitoring by adding specific alerts for critical database performance metrics.
Establish a clear communication protocol for escalating incidents to senior specialists.


In conclusion, the recent service degradation on our online marketplace platform was caused by a database deadlock triggered by an unintended code change. The issue was promptly identified, resolved, and measures are being taken to prevent similar incidents in the future through enhanced testing, monitoring, and communication procedures.

