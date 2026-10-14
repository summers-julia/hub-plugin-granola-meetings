# granola-meetings — Granola meetings for Agents Hub

A meetings agent: once a week it pulls notes from Granola into an archive on your disk, answers what was decided and
who promised what, preps you for calls and hands agreements over to the hub sessions that own the topic.

Why: free Granola keeps notes for 30 days only, and promises made in meetings get lost. The archive stays with you —
plain markdown files, one per meeting.

## Install

1. Tell the hub: "install plugin summers-julia/hub-plugin-granola-meetings" (or Settings → Plugins).
2. Agent: "create agent meetings — Granola meetings, plugin granola-meetings", or yourself:
   `hub session new meetings --agent --about "Granola meetings: archive, who promised what, call prep"`.
3. Granola login: the agent asks for the `granola` tool; sign in to your own account via the link (`hub mcp login`).
   The plugin holds no keys — everyone signs in with their own account.
4. The agent proposes a pull schedule itself (you pick the day and hour) and sets it after your "yes".

Without the hub, in Claude Code:

```
claude plugin marketplace add summers-julia/hub-plugin-granola-meetings
claude plugin install granola-meetings@granola-meetings
```

Then run `/mcp` in Claude Code and sign in to `granola`.

## Skills

| Skill | What it does |
|---|---|
| `meetings-archive` | new meetings into the archive: summary, decisions, who promised what by when, the note text; masks secrets |
| `meetings-answer` | "what did we decide with …", "who promised …", "what happened this week" — from the archive, then Granola |
| `meeting-prep` | a one-screen brief for a call: past meetings, open promises, what to ask |
| `meetings-handoff` | agreements to the session that owns the topic, tasks as drafts to the tasks agent; never writes to people |

## Where the archive lives

`GRANOLA_ARCHIVE`, otherwise `<hub folder>/owner/calls` (`~/.hub-core/owner/calls`). The folder is yours only (700).

## Risk

`owner-data`: the agent reads your meetings. It sends nothing outside and never writes to people; Granola is
read-only (except `sign_out`).
