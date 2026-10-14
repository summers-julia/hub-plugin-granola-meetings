---
name: meetings-handoff
description: Hand agreements and tasks from a meeting to whoever owns the topic — a hub direction or the tasks agent, as a draft. Use after pulling new meetings when they contain decisions or promises on someone's topic.
---

# Handing off agreements

You are the meetings specialist: decisions and tasks of a topic are owned by someone else. Your job is to get them
to the owner.

1. To whom: the hub direction for the topic (`hub status`, role "direction", its description says what it covers).
   No direction for the topic — one line to the owner in the pull summary, not into your own to-do list.
2. What: per agreement — `hub send <direction> "<meeting: date, topic> — decided: …; promised: who, what, deadline"`.
   One message per direction per pull, not one per item.
3. Tracker tasks — drafts only: to the hub's tasks agent if there is one (`hub status`, its description), otherwise
   to the direction. Never file them in the tracker yourself.
4. Write and send nothing to people: hub sessions only.
5. Once handed off, mark the meeting file with a line `- Handed off: <to whom>, <date>`; a repeated pull doesn't
   hand it off twice.
6. Write messages in the hub owner's language.
