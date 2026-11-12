# PUBLIC_M5_team3_tembusu_fm

# TembusuFM — AI Engineering Capstone (team3_tembusu_fm)

Your team is the forward-deployed engineering unit for **TembusuFM**. Your job: build the
maintenance copilot described in [CLIENT_BRIEF.md](CLIENT_BRIEF.md) and survive a live demo with the
customer on **Fri 27 Nov 2026**.

## Quick start

```bash
git clone <this repo>
cd team3_tembusu_fm
Mac: python3 -m venv .venv && source .venv/bin/activate
Windows: python3 -m venv .venv && .venv\Scripts\Activate.ps1

cp .env.example .env          # paste in your team API key (handed out at the briefing)
# download your team zip from NTULearn and unzip into data/  (see data/README.md)
docker compose up -d          # local MySQL — or use MySQL Workbench directly
docker compose exec -T mysql mysql -uroot -pcapstone < data/sql/<dump>.sql
```

## Rules of engagement

1. **No client data in git.** `data/` is git-ignored; keep it that way. Same for `.env` and your API key.
2. **Every member contributes.** Team-process marks are graded per person from commit history — every member commits real work under their own GitHub account (set `git config user.email` to the e-mail on your GitHub profile, or your commits are credited to nobody). Pair-programming is fine; say so in commit messages (`Co-authored-by:`).
3. **Budget.** Your API key has a hard budget. Watch your spend; a burned key is not replaced.
4. **Cite everything.** Answers your app gives must say where the fact came from. See [HARNESS_CHECKLIST.md](HARNESS_CHECKLIST.md) — it is the grading rubric in checklist form.
5. **Ask the client, by email.** The client is reachable only by email to the course director (subject `Client question — Team N`), replies within two working days and does not take calls. If the brief mentions something that is not in the package, ask — do not guess and do not quietly work around it. Keep every answer in `docs/client_qa.md`.

## Deliverables

- Working application (live demo; a judging panel plays your customer and asks unscripted questions)
- Architecture documentation with **at least two Mermaid diagrams** (in `docs/`)
- Data quality report: every trap you found and how you handled it
- 5-minute pitch
- Honest post-mortem (what you'd do differently)

## Timeline

Briefing Mon 16 Nov (Zoom) · Checkpoint 1 Thu 19 Nov · Checkpoint 2 Mon 23 Nov · Consults Thu 19, Fri 20, Mon 23, Tue 24 Nov (Zoom) · Final sprint Thu 26 Nov · **Demo Fri 27 Nov 09:00–13:00, SR902** (slot order announced Tue 24 Nov). Details: [CHECKPOINTS.md](CHECKPOINTS.md).
