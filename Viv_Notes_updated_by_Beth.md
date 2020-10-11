API Automation Challenge

## Things to discuss
- Currently we have checks for fields not being null and being an integer or string etc - we might want to consider contract testing for this? Agreed, lets do this!
- For now I've fixed failing tests which check for null and their type just to get some green tests :) - roger that
- I've changed for the create booking requests values to be dynamic for creating a booking, did we want to do this everywhere where possible? - Makes a lot of sense
- Some of the API's feel like they need to follow on from each other in a flow e.g. POST booking / get bookings (verify posted booking visible) / PUT booking (same booking) / delete booking - is a pre-request script the best way forward for this? if so, where?
- I updated the auth -> create token post request because /auth was giving me a 400.  I added /login to the end and updated the password and this worked fine
- I could be wrong about this, but I tried adding a patch request for the automationintestingonline site (as opposed to restfulbooker.herokuapp) and I get a 405 method not allowed - is it poss that this endpoint hasn't been added here?
- Create booking test was not adding the booking ID to the environment variable - I updated the response reference so that it now does
- Create booking endpoint didn't look correct - it was returning a 200 but it wasn't actually generating a new booking.  I've updated the URL from {{aitbaseURL}}/booking to {{aitbaseURL}}/booking/ to fix this
- To re-run create booking and for it to work every time, there needs to be a unique start/end date OR room availability - to do this I tried a pre-request script for POST booking/ but cant get it to pass the parameter bk, please can you take a look at my notes and see where I'm going wrong?
- updated PUT booking body fields to match those of POST booking - also think a pre-request script to generate a booking that we can update would be worthwhile
- DEL room/booking - after viewing a postman advanced testing tutorial I added in a negative test to check for an empty response body/not an error, see what you think.
- Get Branding - updated response values test to match the updated values as per PUT request and changed order of tests so that this runs after PUT in a collection 

## Observations
The following things we might want to just write about in the write up and mention the things we observe as some of it theres little value in automating?
- Some endpoints do not require auth where as some do?
- The creation endpoint returns the wrong status codes? I've added a test which currently fails as the API is wrong - it returns a 200 not a 201 on creation.
- The creation endpoint allows you to inject XSS, I didn't think we should automate checks for these but should def mention it?

## Features of our testing approach
- Worth talking about contract testing in write up as this is valuable and I'm glad I learnt about it
- Also love the insertion of random (dynamic) variables in our test bodies
- Used lodash module to set min and max random number generated variable for use in POST room request

