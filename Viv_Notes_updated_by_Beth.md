API Automation Challenge

## Things to discuss
- Currently we have checks for fields not being null and being an integer or string etc - we might want to consider contract testing for this? Agreed, lets do this!
- For now I've fixed failing tests which check for null and their type just to get some green tests :) - roger that
- I've changed for the create booking requests values to be dynamic for creating a booking, did we want to do this everywhere where possible? - Makes a lot of sense
- Some of the API's feel like they need to follow on from each other in a flow e.g. POST booking / get bookings (verify posted booking visible) / PUT booking (same booking) / delete booking - is a pre-request script the best way forward for this? if so, where?


## Observations
The following things we might want to just write about in the write up and mention the things we observe as some of it theres little value in automating?
- Some endpoints do not require auth where as some do?
- The creation endpoint returns the wrong status codes? I've added a test which currently fails as the API is wrong - it returns a 200 not a 201 on creation.
- The creation endpoint allows you to inject XSS, I didn't think we should automate checks for these but should def mention it?
- Worth talking about contract testing in write up as this is valuable and I'm glad I learnt about it
