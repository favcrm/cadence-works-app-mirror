---
app: works
title: Works
version: '0.2.0'
summary: 'Docs, decks and sheets with review and export gates. Create, edit and review on the host; export receipts only for approved revisions.'
needs:
  connections: []
  capabilities: {}
  views:
    contract: app-views/v1
  requires:
    contracts:
      app-screens: [1]
      screen-records: [1]
      app-views: [1]
listing:
  tagline: Docs, decks and sheets with review and export gates
  icon: assets/works.svg
  category: operations
  tags:
    - documents
    - review
  publisher:
    name: Cadence
  about: Works keeps docs, decks and sheets as revisioned host content. An author edits and requests review; an independent reviewer approves or requests changes; an export receipt is recorded only for the approved current revision. The screen reads and writes Works through the host. The app does not approve its own content.
  can:
    - Create, read, edit and trash docs, decks and sheets
    - Request review of a revision and record the reviewer's decision
    - Record an export receipt for an approved current revision
  screenshots: []
  setup: []
  data:
    stores:
      - Works docs, decks and sheets owned by the host, scoped to the installation's context.
    personal: true
---
# Works

Works is the host-owned content store for docs, decks and sheets. The screen
at `screens/works/` reads and edits Works through the `screen-records.v1` host
operations only. Review and export are host-confirmed decisions: the reviewer
picks approve or changes in a host-drawn confirmation, and an export receipt is
recorded by the host for the approved current revision.

The app does not approve its own content, choose a reviewer, or mark anything
exported. A workflow `document-draft` produces a local text draft; it does not
mutate Works and makes no content-approval claim.
