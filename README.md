# What if we used Github to publish contnet?

The three folders above are three Mainstream browse categories picked at random. Each contains a piece of content currently tagged to that category, also picked at random. All content is written in markdown by default (just like this ReadMe is), but Github doesn't render Govspeak.

## Demo content

This is what's called a Github repository (commonly abbreviated to repo). Think of it like a top-level folder. Repos can contain most types of files. In this proof-of-concept, imagine this contains every piece of Mainstream Content that is currently live. Click into each folder above (pulled from Mainstream browse at random) to see the demo guide it contains.

### Working on content and sending it for review/2i

When you want to make changes to a guide in publisher, you create a new edition of that specific guide.

In Github, you make a new "branch", and give it a descrptive name. For example, the number of the jira ticket (YT-123) and a description of the ticket (updating-visa-rules-botswana) gives you a branch called **YT-123-updating-visa-rules-botswana**. This new branch is where you can make changes to any and all content without it affecting the "main branch" where the live content lives. If your ticket needs changes to several guides, you always do then all in one branch.

You save changes to the branch by "committing" them. Each commit should contain a defined chunck of content. Think of these as the numbered changes you use when writing change notes for publisher. If you would separate it out into it's own [1] in changes notes, then it should be it's own commit.

You can revert commits at ny time without impacting any content that wasn't touched in that commit.

You can delete your entire branch without affecting live content - they are totally separate.

To "send a guide to 2i" or maybe generate previews (if implemented by devs), you create a Pull Request (PR). This automatically pulls in all the commits you've made on your branch so far into a container called a (PR). The PR is what you share with someone else for discusses, reviews and 2i. It also isn't static - as you make more changes and make/undo commits on your branch, you PR will update automatically.

## Why use Github?

### Version control

Git (Github's underlying technology) is a version control system. It allows you to make changes to files (code, content, whatever), and track the changes made, along with comments explainig the changes.

### Resolving merge conflicts

In publisher, we encounter what we called "blocked editions" - this is where one user creates a new edition of a piece of content, blocking it for anyone who wants to make unrelated changes. Git and Github allow you to

### Comparing versions

Git and github allow you to easily compare different versions of files, much like the compare view in Publisher. This completely removes the need to manually write changes notes.

### Easy peer review

When changes are ready, a Pull Request can be assigned to/claimed by a 2ier. When reviewing, you can drop comments directly on specific parts of the proposed changes, tag the assigned DC, and

## Caveats

### Hard to implement

This repo is a proof of concept, and is in no way actually connected to the GOV.UK website. Doing what this repo suggests would take a substantial rewrite, would have to be done from the ground up, and would likely take a long time.

Github doesn't and can't speak govspeak, which makes true previewing difficult. However, we already have a mechanism for deploying previews to Heroku for smart answers, so there is a minor precedent.

### Guthub is untested with content designers

Content Designers aren't expected to know how to use Github, git, or any version control terminology. There would need to be some upskilling so everyone understands things like "pull request", "branch", "merge conflict". 
