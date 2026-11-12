# Client Brief — TembusuFM Pte Ltd

*From: Alan Chew, Operations Director (your client contact)*

We maintain 9 commercial buildings. MD wants a board-level view of maintenance cost and energy
usage per building; my techs want a copilot that actually knows our equipment. Our CMMS export is
in `sql/`, but half the story lives in scans: contractor quotations, preventive-maintenance
checklists, and meter photos the techs WhatsApp me monthly (our auto-meter feed for two buildings
died in January — the photos are the only record since).

**What we want:** one assistant that answers both tech questions ("when was AHU-02 at Tembusu
Tower last serviced and what was found?") and management questions ("total maintenance spend per
building this year, including contractor quotes we accepted"; "monthly kWh trend for ALL 9
buildings including the two on photos"). It must also produce a defensible P1-ticket SLA report —
a tenant is threatening penalties (see emails).

**Known landmines:**
- Equipment tags: half old convention, half new, same equipment. Counting breakdowns naively will double-count.
- Ticket priority is free text. "P1", "urgent", "URGENT (MD office!)" — you decide the mapping and defend it.
- Contractor quotes: some ex-GST, some inclusive, one contractor isn't GST-registered.

**Data manifest:** `sql/tembusufm_cmms.sql`, `tabular/` (equipment register xlsx, monthly kWh CSV),
`images/` (12 meter photos, 48 quotes, 30 checklists), `docs/emails/`.

---

## Engagement rules (same for all teams)

You are a squad of **forward deployed engineers**. The client is non-technical.
A panel of judges will role-play your client contact at the demo.

**You must deliver, on presentation day (Fri 27 Nov 2026, 09:00–13:00, NTU@one-north SR902; per team: 5-minute pitch, 5-minute live demo, then Q&A from the panel; slot order announced at the Tue 24 Nov consult):**

1. A working AI application using the LLM API endpoint provided in class (open API, key issued per team). No other paid AI services.
2. Ingestion of ALL data source types in this package (SQL, tabular, images, documents). The app must answer from *this* data, not model memory.
3. An architecture diagram and at least two Mermaid diagrams (e.g. data flow, sequence diagram of one query, ER diagram of your cleaned schema).
4. A one-page data quality report: what was wrong with the client's data and what you did about it.
5. A live demo in which the client (the judging panel) will ask unscripted questions.

**Constraints:**
- The raw data is too large to paste into a prompt. You are expected to build retrieval / pipelines, not a mega-prompt.
- Answers must cite their source (table, file, or image) so the client can verify.
- If the data cannot answer a question, the app must say so instead of guessing.
- Handle the data-protection issues you find. You may be asked about PDPA on demo day.

**Talking to the client:** the client is reachable by email only. Send questions to the course director with the
subject `Client question — Team N`; the client replies within two working days, answers only what is asked, and does
not take calls. Real clients forget things: if something this brief mentions is not in the package, do not guess and
do not work around it in silence — ask. Record every client answer in `docs/client_qa.md` in your repo.

**Marking signal (what the client cares about):** correct answers on messy cross-source questions,
graceful handling of contradictions and missing data (including noticing what is missing and asking),
clear architecture, and a demo that survives questions you did not rehearse.
