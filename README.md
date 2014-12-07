Khan Academy "Infection" Model
============

## Run me

## Summary

I've described my approach to the infection problem below. During the process of writing my code and thinking through possible strategies, I compiled a "data wishlist" - salient user information for the problem at hand. My solutions are predicated on the existence and availability of this data!

## Part I: Infect

Users are represented by the User class in user.py. Users are the nodes / vertices of coaching graphs (Graph class in user.py). The graph can be constructed from an edge list (list of coach-student liaisons)

## Part II: Limited Infection

The first way to limit spread is simply to choose not to infect users with many coaches, students or both, containing the spread by infecting relatively isolated nodes.

A slightly more nuanced approach with tradeoffs:

If we were testing a new feature through A-B testing we would want equal proportions of users to see site A and site B. Ways to limit spread of new site infection: stop at "dead nodes"

Given that the objective in the limited infection scheme is to minimize the risk of a coach-student pair seeing different sites, I implemented "infection containment" using edge weighting. 

## Extras

Data wishlist:
1. Total number of minutes spent on KA within the last X days/weeks/months for any given student-coach pair (to gauge whether the pair is active - targeting inactive users as stopping points for the infection minimizes the risk of a site version mismatch). This activity window could be determined by the average length of an AB test.

2. Aggregate number of logins for a coach-student pair.

Logins * minutes spent on KA

2. Interactions: weight nodes by total hours spent together (affinity)

3. Length of playlist - a longer playlist translates to more chances for the 
