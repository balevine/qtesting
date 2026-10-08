# QVAL RULES — Q-DO Support Conversations

## RULES

### Your task

You are triaging customer support conversations for **Q-DO**.

Base every decision only on the text of the conversation (subject and messages). Do not invent facts.

### The product

Q-DO is a collaborative to-do list app. People use it through a **web app**, **desktop apps** (Windows, macOS, Linux), and **mobile apps** (iOS, Android, plus Apple Watch). Users can:

- create to-do lists and add task items (with notes, subtasks, priorities, due dates, recurring tasks and reminders)
- check off items as complete
- share lists with other people, who can then edit and check off items on the shared list (with roles/permissions)
- archive completed lists, and search, export or print lists
- sync lists across all their devices, including changes made offline

Customers are end users, mostly productivity-minded people, who are tech savvy but not developers. They write from laptops, phones and tablets. Their tone ranges from crisp and professional to frustrated when something blocks their work.

### Reading a conversation

- A conversation (thread) is a subject plus one or more messages in time order.
- Messages where `isStaff` is `true` (sender email at `company.biz`) are from the Q-DO support team. All other messages are from the customer.
- Every conversation starts with a customer message. The first customer message defines what the conversation is about.

### What customers ask about

Based on an audit of 100 Q-DO conversations, customers write in about these kinds of things:

- **Feature requests** — ways to organize lists (folders, tags, templates, kanban, auto-archive, bulk import), more task fields (attachments, dependencies, quantities, Markdown), finer sharing controls, new ways to capture or see tasks (voice assistants, widgets, location reminders), desktop-only features, and more themes.
- **Task and list bugs** — edits that don't stick or come out garbled, tasks deleted or added by accident, wrong due/repeat/completion dates, wrong list order or progress, and wrong reminders or notifications.
- **Help center and how-to** — features, limits or sharing behavior that the help center doesn't explain, outdated or mistranslated help articles, and requests for advice on how to use Q-DO well.
- **Install, launch and crashes** — unsupported devices/OS/browsers, installs that fail, apps that won't start, and crashes or freezes.
- **Sync across devices** — checkmarks not syncing, lists that differ between devices, offline changes that never upload, and repeated sync conflict prompts.
- **Sharing and collaboration** — other members' changes not appearing, edits that collide, failed invites, and roles or "leave list" not working.
- **Signup and sign-in** — missing or expired verification emails, signup forms blocking a valid user, and wrong or duplicate accounts.
- **Archive, search and export** — the archive showing or taking the wrong lists, archived content that can't be reached or gets reset, and incomplete exports or printouts.

A conversation may also be something other than a support request (spam, sales pitch, job application, a thank-you with no ask), or too vague to classify. Categories exist for those cases.

---

### Labels

Labels are grouped into a number of areas, each with a set number of options.

Areas (with options):

- Platform (WEB, ANDROID, IOS, DESKTOP-MACOS, DESKTOP-WINDOWS, DESKTOP-LINUX)
- Issue (HOW_TO/DOCS, BUG, FEATURE_REQUEST, NOT_SUPPORT, SPAM, NO_ISSUE, UNCLEAR)
- Product-Area (TASKS_LISTS, SHARING, ARCHIVE_SEARCH_EXPORT, SYNC, INTEGRATIONS, ACCOUNT)

**ISSUE** is a mandatory field.
**PLATFORM** and **PRODUCT-AREA** are optional.

Notes on applying labels:

- Each ticket should have no more than one of each selected. If more than one may apply, choose the strongest match. For example, if a customer has a problem sharing their task lists, then it's product area is `SHARING`.
- Do not label things mentioned only in passing (e.g., "I love the dark mode, but…"), or things raised only by support.
- If later messages show that the real problem is different from how it was first described, label the real problem and not the mistaken one.
- **One problem gets one label.** Apply more than one label only for **separate** problems or requests, not to hedge between two possible labels for the same problem.
- Two separate problems that fall under the same label (e.g., two different sync bugs) still mean that one label applies.
- Every conversation gets at least one label.
- The standalone labels `NOT_SUPPORT`, `NO_ISSUE` and `UNCLEAR` are used **alone**. If one of them applies, no other label applies.

Label definitions:

#### Product areas

| Area | Definition and examples |
|---|---|
| `TASKS_LISTS` | Creating and editing tasks and lists on the customer's own account: task titles, notes, subtasks, priorities, due dates, recurring tasks, completion, reminders and notifications, list order, sorting, progress, pinning, organizing lists (folders, tags, templates, views). |
| `SYNC` | Keeping **one person's own devices** in step: changes, checkmarks or lists that differ between devices, offline changes that don't upload, sync-conflict prompts. |
| `SHARING` | Lists shared **between different people**: invites, members, roles and permissions, leaving a list, assigning tasks, seeing other members' changes, collisions between members' edits. |
| `ARCHIVE_SEARCH_EXPORT` | Archiving and unarchiving lists, the archive view, search, import, export (CSV etc.) and printing. |
| `ACCOUNT` | Creating an account, verification emails, signing in, wrong or duplicate accounts, merging accounts, account settings and limits, plans and billing. |
| `INTEGRATIONS` | Using Q-DO from outside the app: home- or lock-screen widgets, voice assistants, calendars, location-based triggers, other apps and services. |

Choosing the area:

- **Sync vs. sharing:** If the problem is between **one person's own devices**, use `SYNC`. If it is between **different people** on a shared list, use `SHARING`.


#### Issue types

| Type | Definition |
|---|---|
| `BUG` | Something that exists in Q-DO doesn't work as it should: data not saved, garbled or lost; wrong behavior; sync failures; crashes; installs or sign-ins that fail; a device that should be supported being refused. |
| `FEATURE_REQUEST` | The customer asks for something Q-DO doesn't do, even if they phrase it as a complaint ("why can't I…"). Includes asking for support for a device, OS or browser Q-DO doesn't support. |
| `HOW_TO/DOCS` | The customer looked for help and the help center, FAQ or in-app guidance is missing, unclear, wrong, outdated or mistranslated. Or the customer asks how to do something or for advice on using Q-DO, without pointing to a documentation problem and with nothing broken. |
| `NOT_SUPPORT` | Not a Q-DO support request: job applications, press or partnership requests, sales pitches, messages meant for a different company. |
| `SPAM` | Not for this company, or clearly trying to sell a product or service that we don't need. |
| `NO_ISSUE` | Thank-you notes or comments that ask for nothing. |
| `UNCLEAR` | The message is too vague, empty or garbled to tell what the problem is, even if the customer names an area (e.g., "something's wrong with sharing"). Use only as a last resort. |

Choosing the type:

- **Bug vs. feature request:** If the customer describes something that exists in Q-DO but behaves incorrectly, it is a `BUG`. If they ask for something Q-DO doesn't do, it is a `FEATURE_REQUEST`.
- **Bug vs. documentation:** If the product works but the help is missing or wrong, use `HOW_TO/DOCS`. If the product itself misbehaves, use `BUG`, even if the customer also mentions a help article. If the help says one thing and the product does another and it isn't clear which is wrong, use `BUG`.
- **Unsupported devices:** If the customer asks whether a device is supported, use `HOW_TO/DOCS`. If they ask Q-DO to support a device it doesn't, use `FEATURE_REQUEST`. If a device that should work is refused, use `BUG`.

---

### Urgency

Pick exactly one of the three urgency values `HIGH`, `MEDIUM` or `LOW`, choosing the one that reflects **how much the customer's problem hurts them and how soon support must act**. Judge the impact of the problem as the customer reports it. Do not lower the urgency because support later answered, worked around or fixed it in the same conversation.

| Urgency | Definition and examples |
|---|---|
| `HIGH` | **Must be addressed immediately.** The customer cannot use Q-DO at all, or faces loss, exposure or lockout. Examples: can't sign in or reach their account; can't create an account at all; sees another person's account or data; the app won't install, start or stay open on any device they use; a service outage or servers unreachable; tasks or lists permanently lost and not recoverable. |
| `MEDIUM` | **Should be addressed soon.** Something is broken and gets in the way, but Q-DO is still usable. Examples: a bug that blocks a non-critical feature (export, print, reminders, archive view); intermittent or partial sync problems; shared-list changes slow to appear; edits that sometimes don't save; crashes limited to one device or one large list; a failing invite; a bug with a known workaround. |
| `LOW` | **Can be addressed later.** Nothing important is broken. Examples: cosmetic bugs (wrong progress bar, sort display, layout glitches); feature requests; general feedback; documentation gaps or outdated help articles; how-to and advice questions; `NOT_SUPPORT` and `NO_ISSUE` messages. |

Tie-breakers:

- If the conversation has several labels, grade the urgency of the **most urgent** problem.
- A feature request is `LOW` even if the customer says it is important to them, unless it describes something actually broken.
- If the customer says a problem is blocking a deadline or their whole team, move up one level, but never to `HIGH` unless it fits the `HIGH` definition.
- If you can't tell how badly the customer is affected, choose `MEDIUM` for bugs and `LOW` for everything else.

---

### Sentiment

Grade the **customer's** sentiment only; ignore the tone of support messages. Consider all customer messages, but weight the **most recent customer message** most heavily, since it shows how the customer feels now. Judge the emotion expressed, not the severity of the problem: a calm report of a serious bug is `NEUTRAL`.

| Sentiment | Definition and cues |
|---|---|
| `UNHAPPY` | Clear frustration or disappointment. Words like "frustrating," "annoying," "disappointed," "this is the third time"; says the problem is blocking their work or productivity; impatient follow-ups ("any update?"). |
| `NEUTRAL` | Matter-of-fact. Reports a problem, asks a question or makes a request with polite but unemotional language. Routine courtesies ("Hi," "Thanks," "Cheers") alone do not make a message positive. Most first messages fall here. |
| `HAPPY` | Positive. Expresses appreciation, satisfaction with the answer or fix, or affection for the product ("I love Q-DO, but…", "That worked, thanks!"), with little or no frustration. |

Tie-breakers:

- If the customer started frustrated but their latest message says the problem is fixed and thanks support, grade the latest mood (usually `HAPPY`).
- If the customer started polite but their latest message reports the problem still isn't fixed and expresses frustration, grade `UNHAPPY`.
- If there is no clear emotional signal, choose `NEUTRAL`.
