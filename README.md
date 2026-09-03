# Detection Engineering Lab

A hands-on detection engineering project built with Elastic, Sysmon, KQL, Sigma, Python, and controlled adversary simulations. The goal is to develop detections as testable engineering artifacts: define the threat behavior, verify the telemetry, trigger the rule, investigate the alert, and measure tuning decisions.

##  Architecture

- Elastic Stack 9.5.2 on Ubuntu 24.04 in AWS EC2
- Elasticsearch, Kibana, and Fleet Server on one lab node
- Windows 11 VM monitored with Elastic Agent and Sysmon
- TLS between components; restricted AWS security-group access
- Seven-day telemetry retention for cost and storage control
