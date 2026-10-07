# n8n Personal Job Scout

A simple personal automation built with n8n to automatically search for relevant job opportunities from multiple job APIs and send a daily email digest.

## Problem

Manually checking job boards every day is repetitive and time-consuming.

The goal of this project was to create a lightweight automation that searches for recent job opportunities, combines results from multiple sources, filters out irrelevant roles and sends only new relevant jobs by email.

## Workflow

The automation runs daily and follows this process:

1. A Schedule Trigger starts the workflow.
2. Adzuna and Jooble APIs retrieve recent job listings.
3. Split Out converts API results into individual job items.
4. Jooble data is normalized to match the Adzuna structure.
5. Merge combines both job sources into one stream.
6. Target Roles keeps jobs matching selected career areas.
7. Exclude Unwanted Roles removes irrelevant logistics/import-export positions.
8. Remove Duplicates prevents previously processed jobs from being sent again.
9. A Code node combines the remaining jobs into a single report.
10. Gmail sends the report by email.

## Workflow

![n8n Job Scout Workflow](workflow/screen%20jobscout%20n8n.PNG)

## Tech Stack

- n8n
- Adzuna Jobs API
- Jooble API
- Gmail

## Key Concepts Practiced

- Scheduled workflows
- REST API requests
- Working with multiple APIs
- JSON data normalization
- Merging multiple data sources
- Positive and negative filtering
- Deduplication between workflow executions
- Data aggregation
- Automated email notifications

## Security

API credentials are not included in this repository.

To use the workflow, replace:

- `YOUR_ADZUNA_APP_ID`
- `YOUR_ADZUNA_APP_KEY`
- `YOUR_JOOBLE_API_KEY`

with your own API credentials inside n8n.

## Result

The workflow automatically searches Adzuna and Jooble, combines and filters the results, removes previously processed listings, and sends a concise email containing only new relevant jobs.
