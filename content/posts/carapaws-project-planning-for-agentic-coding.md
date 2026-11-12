+++
date = '2026-10-30T12:00:00+00:00'
draft = false
title = 'CaraPaws: a project plan your coding agent can read'
tags = ['IT']
image = 'https://assets.galfajon.dev/pictures/carapaws/carapaws-header.png'
description = "Using AI to flesh out our CaraPaws plan from a document into a GitHub Project, and why it made working with coding agents much simpler."
+++

After [finishing the UI prototype]({{< relref "/posts/carapaws-ui-prototype.md" >}}) for CaraPaws, my teammate and I started building the real application: an Express API with a PostgreSQL database, private photo storage, and a new React and Capacitor frontend, based on our initial prototype. Our plan lived in a Markdown file in the repository, and we wanted to expand that application spec into a project plan that coding agents could work with.

We decided to turn the plan into a GitHub Project, with every task written as a proper technical specification. Most of the work was done with Claude Code driving the GitHub CLI, which made it much faster than clicking through the web interface. Here is the process, step by step, for anyone who wants to turn a Markdown spec into a project timeline their agents can work from.

## 1. Set up the GitHub CLI

The [GitHub CLI](https://cli.github.com/) is what makes the rest of this convenient, because both you and your agent can script the tracker from the terminal. On Windows:

```bash
winget install --id GitHub.cli -e
gh auth login --scopes project
```

## 2. Create the skeleton: labels and milestones

Before creating any tasks, decide how you will group and sort them. We used:

- **Area labels:** `api`, `ui`, `testing`, `infra` and `user-testing`
- **Priority labels:** `priority: critical`, `priority: high` and `priority: low`
- **Milestones:** one per week, each with a due date and an exit criterion

Labels come from `gh label create`. Milestones have no dedicated command, but `gh api` covers them:

```bash
gh api repos/OWNER/REPO/milestones -f title="Week 2 — First end-to-end demo" \
  -f due_on="2026-11-08T23:59:59Z" -f description="Exit criterion: ..."
```

## 3. Turn every feature or goal into an issue

We converted each goal in the plan into its own issue, with a title, area and priority labels, and a milestone. The agent created these in bulk with `gh issue create` and closed any work that was already finished with `gh issue close`, so the milestones showed the current state of the project from the start.

## 4. Expand each vague task into a technical specification

An issue should be a specification. Our original plan had lines like "Add routes that allow owners to enter dog information". As an issue, it became:

- **Endpoints:** `GET` and `POST /api/dogs` for an owner's own dogs, and `GET`, `PUT` and `DELETE /api/dogs/:id` for a single dog. Each one lists who may call it (the owner, or a sitter currently caring for the dog), its response and every error status.
- **Input rules:** `name` and `gender` are required, text fields have length limits, and the "loves" and "dislikes" lists are capped at 20 short labels.
- **Implementation notes:** the dog, its emergency contact and its preferences are written in one database transaction, an attached photo must belong to the owner, and access goes through the shared "owner or assigned sitter" helper.
- **Client functions:** the exact signatures this adds to the frontend's API client, such as `getDog(dogId: string): Promise<Dog>`.
- **Acceptance criteria:** owners can manage their dogs, sitters can only read a dog while caring for it, saves are atomic, and the integration tests cover the owner, the assigned sitter and an outsider.

We did the same for every task. The agent drafted each specification from the existing code, the database schema and the requirements, and I reviewed and corrected them.

## 5. Build the project and the timeline

With the issues in place, the project itself is a few more commands:

```bash
gh project create --owner OWNER --title "CaraPaws"
gh project link 1 --owner OWNER --repo OWNER/REPO
gh project field-create 1 --owner OWNER --name "Start date" --data-type DATE
gh project field-create 1 --owner OWNER --name "Target date" --data-type DATE
```

Each issue is added with `gh project item-add`, and its status and dates are set with `gh project item-edit`. Views can't be created through the API, so the board and roadmap views take a minute in the web interface. Point the roadmap at the two date fields, and the timeline appears.

## 6. Point your agents at the tracker

Finally, tell your agents about the tracker. Our `AGENTS.md` says where the tasks live and how to work with them:

- find the issue (`gh issue list --assignee @me`)
- check that its dependencies are closed
- stay within its scope, and raise anything new as a separate issue
- put `Closes #N` in the commit that finishes it

Starting a task becomes "work on #22" instead of a long prompt re-explaining the context, and the acceptance criteria tell the agent when it's done.

## Keeping it useful

The tracker only helps if it stays accurate, so when a decision changes, the issues change with it. That's easy when the agent that wrote them can also edit them. None of this is specific to GitHub either: Jira or any tracker with an API works the same way, as long as your agent can read it. I've come to see the tracker as part of the context you give a coding agent, alongside the code and `AGENTS.md`, and it's worth writing with the same care as the code itself.
