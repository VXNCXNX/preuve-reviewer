# Preuve Reviewer

Preuve Reviewer is a GitHub App that reviews pull requests. Install it on a repository, and it reads the first pull request of each month and posts a review on it. The review is free.

## What a review contains

A review has two parts:

- A summary comment on the pull request. Its first line is the verdict, for example `Verdict: COMMENTS, risk: medium`. The verdict is `APPROVE`, `COMMENTS` or `BLOCK`, and the risk is `low`, `medium` or `high`. Below the verdict, each finding names a file and a line and says what to change.
- Inline comments on the diff, on the lines the findings refer to. Reply to them or resolve them like any other review comment.

The summary comment ends with a footer that shows the date of the review, for example `Preuve Reviewer · 2026-10-19`.

## Which pull request gets reviewed

Each installation gets one review per calendar month. The app reviews the first pull request that meets one of these conditions during the month:

- Someone opens it, and it is not a draft.
- Someone marks a draft pull request as ready for review.

The app skips a draft pull request until someone marks it ready for review. Commits pushed after the review do not start a new review. If a review fails for a technical reason, the next push to that pull request retries it, up to three attempts in total, and the failed attempt does not count against the month.

One installation can cover one repository or many, depending on the repositories you select. All repositories under one installation share the same monthly review.

Review capacity is also limited across all installations each month. When it runs out, a pull request can get the "already used" comment below, even on an installation that has not had its review yet.

## The "already used" comment

When the month's review is used, the next pull request gets one short comment instead of a review. In October 2026 the comment reads:

```text
Preuve Reviewer already used this installation's free review for October 2026 (one per month). Reviews resume on 1 November 2026.

Validating the idea behind this repo? https://preuve.ai
```

That pull request gets no review. On the first day of the next month, the next pull request that meets the conditions above gets a review.

## What the app reads, and what it never does

Preuve Reviewer reads the pull request and the code in the repository.

It never does these things:

- It does not run, build or test your code.
- It does not push commits, open branches or change files.
- It does not merge pull requests.
- It does not keep a copy of your code after the review.

These are the permissions it asks for, and why:

| Permission | Access | Why |
| --- | --- | --- |
| Pull requests | Read and write | Read the diff and post inline review comments. |
| Issues | Read and write | GitHub stores pull request conversation comments as issue comments, so the summary comment needs this. |
| Contents | Read | Read the code that the pull request changes. |
| Metadata | Read | GitHub requires it for every app. |

It listens to three events: pull request, installation, and Marketplace purchase.

## Install the app

1. Open [Preuve Reviewer on GitHub](https://github.com/apps/preuve-reviewer) and click **Install**.
2. Select the account or organization to install it on.
3. Select **All repositories**, or select **Only select repositories** and pick the repositories to review.
4. Click **Install**.

The next pull request that you open, or mark as ready for review, gets the month's review.

To add or remove repositories later, open the app's installation settings, described in the next section, and change the repository list.

## Uninstall the app

For a personal account:

1. On GitHub, open **Settings**, then **Applications**, then **Installed GitHub Apps**.
2. Next to **Preuve Reviewer**, click **Configure**.
3. At the bottom of the page, click **Uninstall**, then confirm.

For an organization:

1. Open the organization's **Settings**, then **GitHub Apps** under **Third-party Access**.
2. Next to **Preuve Reviewer**, click **Configure**.
3. At the bottom of the page, click **Uninstall**, then confirm.

Comments that the app already posted stay on your pull requests. Delete them by hand if you do not want them.

## Support and policies

- Support: [preuve.ai/support](https://preuve.ai/support)
- Privacy policy: [preuve.ai/privacy](https://preuve.ai/privacy)
- Terms of service: [preuve.ai/terms](https://preuve.ai/terms)

## Who makes it

[Preuve AI](https://preuve.ai) makes Preuve Reviewer. Preuve AI checks the business idea behind the code. You describe the idea, and it returns a report on the market and the competitors, with a verdict on whether the idea is viable.
