---
name: meetings-archive
description: Pull new meetings from Granola into an archive on disk — one file per meeting with a summary, decisions and who promised what. Use on the pull schedule, on "pull the meetings", "what's new from meetings", and before answering about a meeting that isn't in the archive.
---

# Pulling Granola meetings into the archive

**Archive** — the folder from `GRANOLA_ARCHIVE` (environment variable) or from your CLAUDE.md; neither set —
`<hub folder>/owner/calls` (`$HUB_STATE_DIR/owner/calls`, usually `~/.hub-core/owner/calls`). Write the chosen path
into your CLAUDE.md so you don't have to look next time. The folder is for the owner only: create it with mode 700,
files 600.

**Already pulled** — `.granola-ids.txt` in the archive, one meeting ID per line. New means an ID not listed there.

## Steps

1. `list_meetings` for `last_30_days`; look for a fresh meeting (today, yesterday) in `this_week` as well — it may
   be missing from the first list. Free Granola returns only the last 30 days: anything older can't be pulled, so
   pull regularly (once a week leaves a margin).
2. New IDs — `get_meetings` in batches of at most 10.
3. One file per meeting, `YYYY-MM-DD_<topic>.md`, topic in Latin letters with hyphens (non-Latin file names break
   links). Headings and labels in the owner's language; the note text verbatim:

   ```markdown
   # <meeting title>
   - Date: <YYYY-MM-DD HH:MM (time zone)> · Granola id <id>
   - Attendees: <who was there; if not visible — "from context: …" or "no names in the note">
   - Summary: <2–3 lines: what was decided>

   ## Promises and deadlines
   - <who> — <what> — <by when; no deadline — "no deadline given">

   ## Full note text
   <Granola note verbatim>
   ```

   Count deadlines in words ("by Friday", "on Thursday") from the meeting date, not from today, and write them as a
   date with the weekday: "by Fri 2026-10-09". Unclear which week — "by Friday (per note; date unclear)".
4. No secrets in the archive: password, key, token, card or account details → a placeholder in the owner's
   language, e.g. `[secret — not archived]`. After
   writing, search the file for secret words in the note's language (password, token, key, api and their
   translations) and mask anything you missed.
5. Add the ID to `.granola-ids.txt` only after the file is written: a failure midway must not lose a meeting.
6. Summary to whoever asked: how many new, a line per meeting (date, topic, main promise). Nothing new — stay
   silent on a scheduled run, say "no new meetings" on request.

## Don't

- Don't invent names: Granola usually knows only the note owner. The other side comes from the text; unclear —
  "from context".
- Don't paraphrase the note in "Full note text" — verbatim only.
- Don't send anything to people or file tracker tasks — that's `meetings-handoff`, and drafts only.

## Schedule

No pull job of your own (`hub schedule list`) — propose a day and hour to the owner and set it after their "yes":
`hub schedule add --id <you>-granola-weekly --cron "<min> <hour> * * <day>" --prompt "Pull new meetings from Granola
(skill meetings-archive)"`. A session job lives at most 30 days — renew it when the hub reminds you.
