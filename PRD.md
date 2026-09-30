# Product Requirements Document: CBE Event Program Records

## Problem Statement

CBE runs executive education for the energy sector through three programs: the **Energy Executive Course (EEC)**, the **Energy Executive Summit**, and the **Legislative Energy Horizon Institute**. Each program produces event schedules and agendas. These list sessions, speakers, speaker titles and organizations, times, venues, tours, and meals.

The records from 2016 through 2026 exist only as individual documents, mostly Word files. Different people made them by hand, and the format has drifted over time. For example:

- The **2018 Richland agenda** is a day-by-day list. Each session gives the time, title, speaker, the speaker's job title, and their organization.
- The **2021 Austin EEC/Summit schedule** is a grid of days by time slots. It gives speaker names and times only, with no titles or organizations. Some sessions are marked as shared with Summit participants.
- Both documents mix classroom sessions with logistics such as buses, meals, hospitality suites, and tours.

Because of this, the program staff cannot easily answer basic questions. Examples: "Who has spoken on natural gas in the past?", "When did we last use this speaker?", "Which organizations have we drawn from?" They also have no reliable starting point for building the next event's schedule. Every lookup means opening old files one by one and reading them by hand.

**For whom:** the CBE program staff who plan, run, and report on these events.

## Goals

Success means the program staff can:

1. **Find things fast.** Answer a question like "Has this person spoken for us before, and on what?" in under a minute, without opening the original documents.
2. **Trust the data.** Every event from 2016 through 2026 is in one place, in one consistent format, and each record can be traced back to its source document.
3. **Keep it current.** Staff can add, edit, and delete records themselves, with no technical help needed.
4. **Learn from history.** Staff can see patterns across years, such as topic coverage, repeat speakers, and organizations represented.
5. **Plan the next event faster.** Staff can build a new event schedule starting from past sessions and speakers instead of a blank page.
6. **Not lose anything.** Staff can back up the data and restore it.

## Constraints

- **Source data is inconsistent.** Formats, detail level, and layout vary by year, program, and author. Some fields, such as speaker title or organization, will be missing for some events.
- **The data is public.** Nothing in the source files is confidential, but the team should still handle it discreetly and respectfully.
- **Non-technical users.** The people maintaining the data are program staff, not developers.
- **Handoff at semester end.** The product must be usable and maintainable by the client after the class ends, without the student team.
- **Class timeline and team.** Four students are building it within one semester, using AI-assisted development. All changes go through GitHub pull requests that teammates approve.
- **Time zones and locations vary.** Events happen in different cities, such as Richland, WA and Austin, TX. The source schedules state their local time zone, and that time zone must be kept.

## Target Users / Personas

**1. Program Manager / Event Planner (primary)**
Builds each year's agenda, invites speakers, and books venues and tours. Needs to look up past speakers and sessions quickly, and wants to reuse what worked before. Comfortable with Word and email, not with databases.

**2. Program Coordinator / Admin (primary)**
Enters and maintains records after each event. Fixes mistakes, such as a misspelled name or a speaker who cancelled. Needs simple add, edit, and delete, plus a clear way to back up the data.

**3. Program Director / Leadership (secondary)**
Asks bigger-picture questions for reporting and strategy. Examples: "How much of our content has been on renewables vs. natural gas?" and "Which companies have sent speakers?" Needs summary views, not raw records.

## User Stories

- As an **event planner**, I want to search past sessions by speaker name, organization, topic, year, or program, so that I can quickly find who has presented before and on what.
- As an **event planner**, I want to see every appearance by a single speaker across all years, so that I know their history with us before I invite them again.
- As an **event planner**, I want to build a new event schedule by picking from past sessions and speakers, so that I don't start from a blank page.
- As a **coordinator**, I want to add a new event and its sessions after it is finalized, so that the records stay current.
- As a **coordinator**, I want to edit or delete a record, for example to fix a typo or mark a speaker as cancelled, so that the data stays accurate.
- As a **coordinator**, I want to back up all records and restore them from a backup, so that a mistake or a lost computer doesn't wipe out years of history.
- As a **director**, I want to see summaries such as sessions by topic, speakers by organization, and repeat speakers over time, so that I can report on program content and spot gaps.
- As **any user**, I want each record to show which source document it came from, so that I can check the original if something looks wrong.

## Functional Requirements

Each requirement is written so it can be tested.

### FR1 - Organized, standard data
- FR1.1 The system stores each **event** with at least: program, year, start and end dates, location or venue, and time zone.
- FR1.2 The system stores each **session** with at least: event, date, start and end time, title, and session type (e.g., lecture, panel, tour, meal, logistics).
- FR1.3 The system stores each **speaker** as a separate record with name, and optionally title and organization, and links speakers to sessions with a role (e.g., presenter, panelist, moderator).
- FR1.4 A speaker who appears in more than one event exists as **one** speaker record linked to multiple sessions. The title and organization shown are the ones from that specific appearance.
- FR1.5 Every event records the source file it was taken from.
- FR1.6 All schedules from 2016 through 2026 provided by the client are loaded into the standard format.

### FR2 - Add, edit, delete
- FR2.1 A user can create, edit, and delete events, sessions, and speakers through a user interface, without editing files or code.
- FR2.2 The system asks the user to confirm before deleting.
- FR2.3 Deleting an event does not silently delete speakers who also appear in other events.

### FR3 - Search
- FR3.1 A user can search by speaker name, organization, session title keyword, program, year, and location.
- FR3.2 Search is not case-sensitive and matches partial words (e.g., "gas" finds "Natural Gas 101").
- FR3.3 Search results show the event, date, session title, and speaker(s), and link to the full record.

### FR4 - Analysis
- FR4.1 The system shows counts of sessions and speakers by program and by year.
- FR4.2 The system lists repeat speakers with the number of appearances and the years they spoke.
- FR4.3 The system shows the organizations represented, with the number of speakers from each.
- FR4.4 Classroom sessions can be analyzed separately from logistics items such as meals and buses.

### FR5 - Backup and restore
- FR5.1 A user can export all data to a single backup file with one action.
- FR5.2 A user can restore from a backup file, and the restored data matches the data at the time of backup.
- FR5.3 The backup file is in an open, human-readable format (e.g., CSV or JSON).

### FR6 - Build a new event schedule
- FR6.1 A user can create a new event and add sessions to it, either new or copied from past sessions.
- FR6.2 A user can view the new schedule day by day in time order.
- FR6.3 A user can export the new schedule to a document for sharing, such as Word or PDF.

## Out of Scope

These are deferred to a later release or not planned:

- Speaker contact management, outreach, or emailing speakers
- Participant or attendee registration, rosters, and badging
- Travel, hotel, bus, and catering booking (logistics are *recorded* as schedule items, not *managed*)
- Budgets, speaker fees, and sponsorship tracking
- Automatic import of future Word agendas (new events are entered through the app for v1)
- Public-facing website or participant-facing mobile app
- Multi-user permissions and roles beyond a single staff login
- Storing presentation slides, recordings, or other session materials