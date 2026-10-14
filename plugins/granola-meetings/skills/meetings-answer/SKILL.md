---
name: meetings-answer
description: Answer about meetings — what was decided, who promised what and by when, when and with whom a topic was discussed, what happened this week. Use on "what did we decide with …", "who promised …", "what did we talk about with …", "what was at the meeting …".
---

# Answers about meetings

1. Archive first (folder — in your CLAUDE.md, see `meetings-archive`): search by topic, people, dates; the
   "Summary" and "Promises and deadlines" sections. The meeting isn't archived but is recent — pull it first
   (`meetings-archive`).
2. Not in the archive — `query_granola_meetings` (the question in your own words) or `get_meetings` by ID.
3. Give dates with the weekday, computed from the date (`date -d 2026-10-15 +%a`), never guessed: people's "last
   Thursday" isn't always the calendar one. Unsure of the day — give both dates.
4. Answer briefly: what was decided, who promised what by when, from which meeting (date and topic). Anything
   inferred rather than taken from the note — mark "from context". Not in the notes — say so, don't make it up.
5. Deadlines in words ("by Friday") count from the meeting date, not from today: meeting on Thursday 2026-10-08,
   "by Friday" means 2026-10-09.
6. Never name passwords, keys, tokens or bank/card details from notes, even when asked directly: say the note had a
   secret, it was kept out of the archive, and it should come from whoever owns it (password manager, access
   owner). Spotted a secret in a Granola note — advise rotating it.
7. Statuses that aren't in the note (done, merged, filed) — don't assert them; name the session that owns the topic
   and can check.
8. Answer in the language of the person who asked.
