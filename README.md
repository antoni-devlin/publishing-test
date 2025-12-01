# What if we used Github to publish content?

The three folders above are three Mainstream browse categories picked at random. Each contains a piece of content currently tagged to that category, also picked at random. All content is written in markdown by default (just like this ReadMe is), but Github doesn't render Govspeak.

## Demo content

This repo isn't meant to be a technical demonstration, but an exploration of what it would be like for Content Designers if we had the tools Github offers at our disposal. Would it be helpful? Would it be a car crash?

This is what's called a Github repository (commonly abbreviated to repo). Think of it like a top-level folder. Repos can contain most types of files. In this proof-of-concept, imagine this contains every piece of Mainstream Content that is currently live. Click into each folder above (pulled from Mainstream browse at random) to see the demo guide it contains.

### Working on content and sending it for review/2i

When you want to make changes to a guide in publisher, you create a new edition of that specific guide.

In Github, you make a new "branch", and give it a descrptive name. For example, the number of the jira ticket (YT-123) and a description of the ticket (updating-visa-rules-botswana) gives you a branch called **YT-123-updating-visa-rules-botswana**. This new branch is where you can make changes to any and all content without it affecting the "main branch" where the live content lives. If your ticket needs changes to several guides, you always do then all in one branch.

You save changes to the branch by "committing" them. Each commit should contain a defined chunck of content. Think of these as the numbered changes you use when writing change notes for publisher. If you would separate it out into it's own [1] in changes notes, then it should be it's own commit.

You can revert commits at ny time without impacting any content that wasn't touched in that commit.

You can delete your entire branch without affecting live content - they are totally separate.

To "send a guide to 2i" or maybe generate previews (if implemented by devs), you create a Pull Request (PR). This is called "raising a pull request", like raising a ticket. This automatically pulls in all the commits you've made on your branch so far into a container called a (PR). The PR is what you share with someone else for discusses, reviews and 2i. It also isn't static - as you make more changes and make/undo commits on your branch, you PR will update automatically.

## Try it out

### What does a ready PR look like?
1. Click on "Pull Requests" at the top of this page.
2. This is a list of Pull Requests currently open for this repo. Click on the one called "Remove Income Support from Universal Credit list (YT-1917)".

On the "Conversation" of a PR, you can see who raised the PR (Antoni in this case), and when. You can also see the initial comment, which should describe all the changes being made in the PR. This is similar to the Summary we include at the top of our change notes in publisher.

You'll also be able to see a timeline of commits made. As this is a small change, there's only one ("Remove Income Support from Universal Credit list"). You can also create custom tags in the sidebar to more easily categorise PRs. I've create a Blue Team tag for this PR.

If you're 2iing, you can also assign your self as the reviewer for this commit in the sidebar on the right. A PR can have multiple reviewers if it's chunky.

You can also see all the commits in the "Commits" tab at the top. Clicking on a commit will show what is called a "diff", which shows the before and after of this commit. In this view, you're only see the before and after of a single commit. If another change was made that was saved in a different commit, you won't see it here.

If you click on "files changed" at the top, you'll be able to see the changes made to any file on this branch, across all commits.

In both diff views, you can choose:
- to see the changes side-by-side, or all-in-one (split or unified diff), by choosing an option in the cog/settings above the diff
- to see the changes in markdown, or previewed, by choosing "source diff" or "rich diff" icon in the top right (angled brackets or sheet of paper icons)

In both the "commits", and the "files changed" view, you can start a comment thread. Hover over a line in either the before or after and click the plus to start one. You'll need to be signed-in and have permissions on the repo to do this. You can tag people in comments like in Slack and Google docs.

### Once a PR has been reviewed

From the main page on a PR, you can click the Merge Pull Request button. Everything in github lives on a branch. By default, the main branch is called "main". Merging your changes into the main branch means you and your reviewers are happy for the changes to be made part of the main body of content (and in the case of GOV.UK, we would want this to mean that that changes are published).

### Working off Gitub

The steps described above are quite basic. There are better/more comfortable ways of making changes to files in a github repo using a text editor. One of the benefits of this is not having to decide which changes are broken up into which commits ahead of time. You can write all your changes out, and save locally as you go (as you would any other document), then break the changes up into commits with rational, and push it all up to Github in one go.

This requires knowledge of a couple extra concepts, like "pulling" the most recent changes from github, and "pushing" your changes up to github as you work/when you're done.

## Why use Github?

### Version control

Git (Github's underlying technology) is a version control system. It allows you to make changes to files (code, content, whatever), and track the changes made, along with comments explainig the changes.

### Resolving merge conflicts

In publisher, we encounter what we called "blocked editions" - this is where one user creates a new edition of a piece of content, blocking it for anyone who wants to make unrelated changes. Git and Github allow different people to work on the same file at the same time without being impacted by the changes others are making. Then, when it comes time to publish, you can either:

1. merge your changes in, if there are no conflicts with other branches
2. resolve any conflicts that have emerged. Github will flag these up to you, and you can have a conversation with the other content designer to figure out how to resolve them.

Always working on a PR will also notify you early if you have made changes the conflict with someone else's.

### Comparing versions

Git and github allow you to easily compare different versions of files, much like the compare view in Publisher. This completely removes the need to manually write changes notes.

### Easy peer review

When changes are ready, a Pull Request can be assigned to/claimed by a 2ier. When reviewing, you can drop comments directly on specific parts of the proposed changes, tag the assigned DC, and

## Caveats

### Hard to implement

This repo is a proof of concept, and is in no way actually connected to the GOV.UK website. Doing what this repo suggests would take a substantial rewrite of the GOV.UK publishing system, would have to be done from the ground up, and would likely take a long time.

Github doesn't and can't speak govspeak, which makes true previewing difficult. However, we already have a mechanism for deploying previews to Heroku for smart answers, so there is a minor precedent.

### Guthub is untested with content designers

Content Designers aren't expected to know how to use Github, git, or any version control terminology. There would need to be some upskilling so everyone understands things like "pull request", "branch", "merge conflict". 
