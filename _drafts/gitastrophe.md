---
layout: post
title:  "How  to Avoid a Gitastrophe"
date:   2015-02-06 21:23:19
categories: git
---
Week 9 of General Assembly's Web Development Immersive was project week. Our team had to build a Ruby on Rails app that used <a href="http://everytrail.com/" title="everytrail">
Everytrail </a> and <a href="http://leafletjs.com/examples/quick-start.html" title="leaflet">leaflet APIs</a> for the users to favorite, rate and share. We used Git to manage version control, with a fork and pull model. The project got off to a goood start, but ran into a bit roadblock on day 2. The system we put in place was too complicated, and when each step of the process was not followed, it inevitably broke down. By understanding what went wrong, I hope to enlighten anyone who wants to know how Git can help manage your project smoothly, and how to fix it when something goes awry.

What we were trying to do 
-
On our team, we had a Github project lead  and 4 developers that were given different features to build. Each of the developers had a branch of the master in the main GitHub repository. The developers forked this branch into their own GitHub repositories.  They then cloned this fork locally.  When a developer made a change, they would push it to their fork on GitHub, and then make a pull request from their fork to their branch in the main GitHub repo. 

The project lead would then evaluate their pull requests by checking out the developer's branch locally. If everything looked kosher, she could then push the changes to the master branch. This multi-step process was intended to keep the master branch free of bugs.

What we actually did
-
Instead of following process where each developer would make pull requests to their branch of the main GitHub repository, some pull requests were made to the master branch of the main repo. These pull requests were then accepted into master, before they were evaluated.  When these pull requests contained errors, they broke the master branch. Any developer that tried to pull from the upstream master then received the broken master branch, breaking their local environment. 

What we should have done
-
Everyone should have pushed from their fork to their branch on the main repo, never to the master. The master repo manager should have rejected outright the pull requests coming in straight to the master. The pull request should have been resubmitted to the developer's branch, at which point the lead would have checked out and merged with the latest master locally, only after testing to see if everything still worked before pushing it into the master on github.

The Takeway
-

The master branch should never be corrupted with bad code.
if there is a merge conflict between 2 developers, the project lead can either try and fix it himself, or just accept one person's pull request, and tell the other developer to pull in the latest master and add his changes into a new pull request that won't cause a merge conflict.

















