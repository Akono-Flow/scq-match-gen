# SCQ Match Generator & Projector System Manual

## Overview

The SCQ Match Generator is the central application for importing a
master Excel question bank, generating quiz matches, reviewing/editing
questions, exporting reusable match packages, and presenting media
through the Projector View.

## Typical Workflow

1.  Import the master Excel workbook.
2.  Select worksheet and map columns.
3.  Import questions into the question bank.
4.  Generate a match or selected sections.
5.  Review the generated match.
6.  Edit questions if necessary.
7.  Review pending corrections.
8.  Export an `.scq` match package.
9.  Open Projector View or distribute the `.scq` file.
10. Print the HTML report to PDF if printed copies are required.

------------------------------------------------------------------------

# Importing Questions

-   Import Excel (.xlsx/.xls)
-   Choose worksheet.
-   Map columns.
-   Preview imported questions.
-   Finalize import.

Each imported question stores source metadata (worksheet, row, source
file) so later corrections can be traced back.

------------------------------------------------------------------------

# Generating Matches

Supported sections:

-   Alternate
-   Minute
-   Buzzer

You may: - choose subjects - choose categories - use templates - define
subject order - avoid previously used questions - export HTML and JSON

------------------------------------------------------------------------

# Reviewing and Editing

Generated questions are editable.

Editable fields include: - Question - Answer - Information - Media
metadata (where applicable)

Edits do NOT modify the original question bank.

Instead, pending correction records are created.

------------------------------------------------------------------------

# Corrections System

Every edit records: - Question ID - Source worksheet - Source row -
Original value - New value - Pending status - Optional notes

The application provides: - Corrections review panel - Export
Corrections JSON - Automatic inclusion of `corrections.json` inside
`.scq`

------------------------------------------------------------------------

# SCQ Package

The `.scq` package is the portable match format.

Typical contents:

-   match.json
-   projector_manifest.json
-   report.html
-   print_report.html
-   corrections.json
-   metadata.json (future expansion)

Importing an `.scq` restores: - generated match - projector data -
pending corrections

------------------------------------------------------------------------

# Projector View

Purpose: Present media without revealing answers prematurely.

Supported media: - Images - Audio - Video - PDF

Features: - White or black cover - Manual reveal - Automatic re-cover on
Next/Previous - Hidden answer reveal - Hidden info reveal - Hidden
quizmaster details - Subject list navigation

------------------------------------------------------------------------

# Reports

Export HTML creates the printable report.

Use the browser Print dialog to create a PDF.

The HTML report is also suitable for presentation.

------------------------------------------------------------------------

# Future Architecture

The application is designed to work with companion applications: - Excel
Correction Manager - Media Manager - Quiz Presentation System -
LearnWithMe ecosystem

Corrections remain non-destructive until applied by the dedicated
correction application.

------------------------------------------------------------------------

# Best Practices

-   Keep the master Excel workbook as the source of truth.
-   Treat `.scq` as the portable project file.
-   Export corrections after every editing session.
-   Archive generated `.scq` packages.
-   Apply corrections to the master workbook using the future correction
    manager rather than editing the workbook manually.
