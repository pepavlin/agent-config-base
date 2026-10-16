---
name: user-facing-copy
description: How to write text that end users see in a frontend - labels, buttons, hints, descriptions, empty states, errors, toasts, confirmations, onboarding. Use whenever you build or change UI, write or review UI copy, or the user says the interface is too technical, too wordy or confusing.
---

# User-facing copy

The person using the app wants to get something done. They don't care how the app does it. Every word on screen costs their attention, so each one has to earn its place.

## The test

For every piece of text, ask: **does the user need this to decide or act right now?**

- Yes → keep it, in the fewest words that work.
- No → delete it. Don't move it to a tooltip or a "learn more" by default either; hidden noise is still noise.

## Rules

1. **Outcome, not mechanism.** Describe what the user gets, not what the system does.
2. **No implementation vocabulary.** API, endpoint, database, record, sync, cache, queue, job, webhook, token, payload, ID, status codes, stack traces, internal names of services or fields. Use the words the user would use for the thing.
3. **Don't narrate clicks.** A button labelled "Save" doesn't need a line explaining that clicking it saves. The label is the explanation.
4. **Shortest form that's still clear.** One sentence over two, one word over a phrase. Headings and buttons are verbs or nouns, not sentences.
5. **Don't explain what the UI already shows.** If a spinner, a checkmark or the updated list makes the result obvious, no text is needed.
6. **One message at a time.** Don't stack a heading, a subheading, a description and a hint on the same element.
7. **Same thing, same word.** Pick one term per concept and use it everywhere.
8. **Write in the app's language and the user's register,** not a literal translation of developer English.

## Exceptions: where more text is right

These are not excuses to add mechanism back. They add only what the user needs.

- **Destructive or irreversible actions.** Say what will be lost and that it can't be undone. "Delete project? All its files will be gone for good." Not how the deletion is executed.
- **Errors.** Say what went wrong in the user's terms and what they can do next. "Couldn't save. Check your connection and try again." Never the raw error, never the code, unless there's a support flow that needs it (then put it in small, copyable form, not in the message).
- **Money, privacy, sharing.** If an action charges the user, shares their data or makes something public, say so plainly.
- **Waiting longer than a few seconds.** Tell the user it's working and roughly how long, not which step is running.
- **Tools for technical users.** In admin panels, developer tools and dashboards whose users are developers, technical terms *are* the user's language. Apply the same test; the vocabulary just changes. If you're not sure who the user is, ask.

## Examples

| Too technical / too much | Better |
| --- | --- |
| "Clicking Save will send your changes to the server and update the database." | Button: "Save". Afterwards: "Saved". |
| "Syncing with backend… (job #4821 queued)" | "Saving…" |
| "Error 500: Internal Server Error at /api/v1/projects" | "Something went wrong. Try again in a moment." |
| "No records found in the collection." | "No projects yet." + button "New project" |
| "This toggle sets `notifications_enabled` to true in your user profile, which our worker reads every 5 minutes to send emails." | "Email me about new comments" |
| "Your session token has expired. Please re-authenticate." | "You've been signed out. Sign in again to continue." |
| "Upload a file. The file will be stored in S3 and processed asynchronously. When processing completes, you'll see it in the list." | "Upload file". Show it in the list with a "Processing…" state. |

## Reviewing existing UI

When asked to clean up copy, go screen by screen, apply the test to every string, and list what you removed, not just what you changed. Removing text is the main deliverable; don't replace one long sentence with a different long sentence.
