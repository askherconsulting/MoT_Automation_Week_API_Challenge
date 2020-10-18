API Automation Challenge

## Observations
The following things we might want to just write about in the write up and mention the things we observe as some of it theres little value in automating?
- Some endpoints do not require auth where as some do? (e.g. GET /booking doesn't but GET /booking/id does
- The creation endpoint allows you to inject XSS, I didn't think we should automate checks for these but should def mention it?

## Features of our testing approach
- Worth talking about contract testing in write up as this is valuable and I'm glad I learnt about it
- Also love the insertion of random (dynamic) variables in our test bodies - esp. randomBSBuzz and randomCatPic
- Used lodash module to set min and max random number generated variable for use in POST room request
- I'd never used the pre-request strip to actually do a post request for example to setup a room, this was really cool
- Negative testing for the deletion is cool and might be good to talk about also?
- Beth learnt that regular small merges with master in Github is a much cleaner and easier way of pairing with someone than just getting carried away and dumping a whole load of changes at once!
- Biggest and best part of the approach was pair programming - each committing code to master github repo with comments then having a zoom call to go through sticky points - really helped to know when to stop as we both have a tendancy to over-engineer!

## Improvements - how would we develop the framework if time were no object
- More tests including checking SWAGGER docs to find non-happy path status codes and creating tests for these
- performance testing
- Data visualisation perhaps of the Report results?

## Suggestion for Report for MoT
Question: Can you share a bit more about your experience report with us?Tools? Programming Language? What insights you might share?
We chose to automate the AIT API's using Postman (Javascript).  The biggest insights we can share is the advantages of pair programming and collaboration - Beth and Viv did not know each other but were able to help drive the solution forward - 2 heads are better than one!
Other key features of the framework include contract tests (a first for us both), random dynamic variables (including $randomCatPic, yay!), and extensive use of pre-request scripts/environment variables to ensure each request executes both independently and as part of a collection.