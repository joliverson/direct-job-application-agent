<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/1b07f018-821d-4c8c-b505-4350cb4d0f92" />

# Direct Job Application Agent

A Codex skill that screens job leads against documented experience, prepares accurate applications, routes submissions through employer careers sites, and records verified results in an optional tracker.

The repository is a **sanitized template**. It contains no applicant resume, contact details, account credentials, salary or location preferences, application history, or tracker URL. Personal configuration belongs in the ignored `private/` directory and should stay on the user's machine.

## Set up

1. Place this repository in your Codex skills directory as `direct-job-application`.
2. Create `private/`, then copy `references/profile.template.md` to `private/profile.md` and `references/preferences.template.md` to `private/preferences.md`. If you use a tracker, copy `references/tracker.template.md` to `private/tracker.md`. Fill in only verified facts and your own preferences. The `private/` directory is ignored by Git.
3. Invoke `$direct-job-application` with an employer listing, a company and requisition, pasted job description, screenshot, or a job-board lead. The skill uses a job board only to find the matching employer listing.
4. Review the fit assessment and prepared application. Submission follows the review rule in your private preferences and the active computer-use requirements.

## How this was built in ChatGPT

1. Multiple resume versions and a professional profile were reviewed to extract supported career facts, project evidence, and limits on claims.
2. An employer-site input path was defined. A third-party job link is resolved to the employer's own listing and checked for current availability.
3. A 100-point rubric was added for duties, qualifications, domain knowledge, seniority, and practical fit, with separate checks for hard requirements.
4. The workflow was tested with a real job-board lead. The selected title differed from the search phrase; the agent traced the exact employer requisition, found the published deadline, and skipped an under-threshold application. No application was submitted during that test.
5. A tracker map and candidate preference card were added locally, then the skill was validated and installed for reuse.
6. For this public version, the personalized facts, values, links, and credentials were replaced with empty templates. A privacy scan is run against the files intended for publication before pushing.

## Privacy boundary

Do not commit the `private/` directory or source resumes. The Git ignore rules are a backup, not a substitute for reviewing staged files before publication. Store passwords in an approved credential manager, never in this repository or an application tracker.
