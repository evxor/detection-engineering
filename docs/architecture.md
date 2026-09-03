# Lab Architecture

## Purpose

This environment supports repeatable Windows detection development without exposing sensitive infrastructure details in the repository. It is a personal lab, not a production design.

## Components

| Component | Location | Responsibility |
|---|---|---|
| Elasticsearch 9.5.2 | AWS EC2, Ubuntu 24.04 | Stores telemetry and detection alerts |
| Kibana 9.5.2 | Same EC2 instance | Rule development, investigation, and Fleet management |
| Fleet Server 9.5.2 | Same EC2 instance | Manages enrolled Elastic Agents |
| Elastic Agent 9.5.2 | Windows 11 VM | Collects and forwards endpoint telemetry |
| Sysmon | Windows 11 VM | Produces detailed Windows process and system events |
