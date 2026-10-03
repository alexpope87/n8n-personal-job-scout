# n8n Personal Job Scout

A simple personal automation built with n8n to automatically search for relevant job opportunities and send a daily email digest.

## Problem

Manually checking job boards every day is repetitive and time-consuming.

The goal of this project was to create a lightweight automation that searches for recent job opportunities, filters out irrelevant roles and sends only relevant results by email.

## Workflow

The automation runs daily and follows this process:

1. A Schedule Trigger starts the workflow.
2. An HTTP Request retrieves recent job listings from the Adzuna API.
3. Split Out converts the API results into individual job items.
4. Target Roles keeps jobs matching selected career areas.
5. Exclude Unwanted Roles removes irrelevant logistics/import-export positions.
6. Remove Duplicates prevents previously processed jobs from being sent again.
7. A Code node combines the remaining jobs into a single report.
8. Gmail sends the report by email.

## Workflow

![n8n Job Scout Workflow](workflow/screen%20jobscout%20n8n.PNG)

## Tech Stack

- n8n
- Adzuna Jobs API
- Gmail

## Key Concepts Practiced

- Scheduled workflows
- REST API requests
- JSON data handling
- Positive and negative filtering
- Deduplication between workflow executions
- Data aggregation
- Automated email notifications

## Security

API credentials are not included in this repository.

To use the workflow, replace:

- `YOUR_ADZUNA_APP_ID`
- `YOUR_ADZUNA_APP_KEY`

with your own Adzuna API credentials inside n8n.

## Result

The workflow automatically searches for recent job opportunities, removes irrelevant and previously processed listings, and sends a concise email containing only new relevant jobs.
