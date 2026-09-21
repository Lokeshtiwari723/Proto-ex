# FL-07 — Agent Build Log

## Agent
Source-Grounded Research Notes Agent

## Platform
Claude Project — My AI Workflow

## Core Job
Turn a real research source into clear, structured research notes while keeping the source visible and requiring human verification.

## Initial Build
The agent was built from the FL-06 Personal Agent Design Spec.

The workflow is:

1. Gather the source
2. Synthesize important information
3. Draft structured research notes
4. Review the notes against the source

## Live Tool Connection
Google Drive connector.

I verified that the connected Google Drive tool can retrieve live files from my Drive. I then used a Google Drive document as the source for the agent's research-notes workflow.

## What I Tested
The agent was tested on a real document from Google Drive.

It was instructed to:
- use the connected Drive document as the only source,
- extract key findings and evidence,
- preserve limitations and uncertainty,
- use "Unknown" when information is missing,
- separate source-supported facts from interpretation,
- and produce a human verification checklist.

## What Broke / Earlier Iteration
Earlier tests used files uploaded directly into the Claude chat. Those tests produced useful source-grounded notes, but they did not satisfy the live-tool requirement because Google Drive was not the source.

I therefore changed the workflow to use the Google Drive connector explicitly.

## What Changed
The final workflow uses:
- Google Drive as the live source,
- explicit source-provenance instructions,
- source-grounded extraction,
- uncertainty handling,
- and human verification.

## What Was Cut
The first version allowed multiple possible source types.

For the MVP, I narrowed the live workflow to a connected Google Drive document so the core job could be tested end to end with a real tool connection.

## Guardrails
The agent must not:
- invent facts or statistics,
- invent missing information,
- claim access it did not have,
- turn association into causation,
- publish, delete, modify, or send external content automatically,
- or replace human verification.

## Current Status
The MVP completes the core research-notes workflow using a real Google Drive connection.

Human verification remains part of the workflow.
