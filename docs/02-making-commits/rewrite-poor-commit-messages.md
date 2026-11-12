# Rewriting commit messages 

## Goal
Five rewritten messages with different subject lines, bodies explaining why they were needed, the overloaded message split into three commits and a sentence per message on what was missing. 

## Steps taken
1. Rewrite each of these five commit messages as a subject line and, where useful, a body: 'fix', 'wip', 'changes from review', 'updated stuff in the user service and also fixed the date bug and some tests', 'Bug fix for ticket'.
2. For each, invent a plausible change and explain what information the original message was missing.

## Commands
N/A

## Results

1. Fix 
Plausible Change: a process button could create duplicate analyses if someone clicked submit more than once
Subject: Prevent duplicate analyses on submitted text during processing
Body: Disable the submit button after the first click so a slow response cannot create a second analysis.
Missing: fix didn't say what was fixed or why. anyone reviewing would have difficulty working out what change was done.

2. Wip
Plausible change: user profile updates now validate email addresses for admins
Subject: validate email addresses on profiles - update
Body: Reject malformed addresses before saving so invalid data isn't stored in db
Missing: doesn't state the change/work being done along with if it is completed or not

3. Changes from review
Plausible change: analysis results now highlight the specific text associated with mental health concerns
Subject: Display evidence alongside flagged mental health warnings
Body: Show the relevant text alongside each warning category, so that reviewers can understand which parts of a submission triggered the model's attention
Missing: it doesn’t say which review feedback was addressed or what changed

4. updated stuff in the user service and also fixed the date bug and some tests
Plausible change: the work done covered user-profile handling, submission validation and tests
Subject: validate text and URL submissions before saving
Body: ensure submissions contain the correct information for their input type before being stored in the database
Subject: normalize profile data before saving users
Body: keep user records consistent when profile details are updated
Subject: add tests for submission and analysis handling
Body: verify that invalid submissions are rejected and analysis status changes correctly throughout processing
Missing: the original combines three separate areas, making the changes harder to review and test

5. bug fix for ticket
Plausible change: expired invitation links for new admin account creation were still accepted
Subject: reject expired invitations during acceptance
Body: expired links should not grant access for practitioners to create accounts on system
Missing: it doesn’t identify the bug or explain what behaviour changed


## Observations

