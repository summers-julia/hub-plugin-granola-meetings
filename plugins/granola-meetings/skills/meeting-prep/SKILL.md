---
name: meeting-prep
description: Prepare for a call — past meetings with these people or on this topic, open promises on both sides, what to ask and what to bring. Use on "prep me for the call/meeting with …", "what to discuss with …", "for the daily".
---

# Call prep

1. Who and what: people and topic from the request; if it's unclear who — check the calendar or the last meeting
   of this series in Granola; don't ask if you can find out.
2. Archive: the last 3–5 meetings with these people or on this topic (pull fresh ones first — `meetings-archive`).
3. A one-screen brief, written entirely in the asker's language — section labels translated too:
   - **Before:** a line per past meeting — date, what was decided.
   - **Open promises:** whose, what, deadline; overdue ones first.
   - **Ask:** what is still unresolved, where the other side owes an answer.
   - **Bring:** what the owner promised for this meeting.
4. Weekdays — computed from the date (`date -d <date> +%a`), never guessed. Deadlines in words count from the date of
   the meeting where they were said, not from today ("by Friday" said at a meeting on Thu 2026-10-08 means Fri
   2026-10-09). A note can't tell whether a promise was kept: write "deadline passed, done or not — unknown", not "you
   didn't send it".
5. Task statuses you did not check yourself — mark "per meeting note <date>"; don't present them as current.
6. Give the brief to whoever asked; as a file only if asked (next to the archive, named `prep_<date>_<topic>.md`).
7. Write in the language of the person who asked.
