
# Code Review

## Benefits: 
* Share knowledge - helps developers share skills and ideas (communication)
* Discover bugs earlier - 2 or more reviewers
* Maintain compliance - Align in code style
* Enhance security - looks for vulnerabilities and alert developers of threat.
* Increase collaboration - Team work / Effective Solutions / Mindset (Read Article)

## Disadvantages: 
* Increase Time to ship
* Pull focus from other fellow developer
* large review is a pain (Large Changes / Could Skim quickly / Decrease Feedback )


## Good Insights:
* Show be small (˜250 lines) --> 60 to 90 min
* Feature Breaking --> Small PRs
* Single Responsability (PR about one thing)
* Title - Self-explanatory
* Description - What, Why, and How (Point to Issue Requirements)
* Screenshots (Optional)

## Best Practices (Comunication):
* Include everyone — including new and senior members of the team — in the process
* Distribute code review requests among the team members
* Ask questions and provide helpful context (best to help both of you learn during the process and save time)
* Find the defects and 'suggest' the fixes or investigations;
* Huge opportunity to correct bad habits, learn new tricks and expand knowledge.



## Drama Fee - Lol: (Leave ego at the door) 
0) Personal - Approach with a open mind  (Growth Mindset).
1) Read the description (What is going on, maybe questions are already answered there).
2) First Pass Through - Skim through the changes
   * Unit Test First - Small documentation (How works!)
   * Look if anything jumps/sticks out right away.
     - if yes, start there.
   - If theres anything that is clearly wrong - Give feedback in a form of Questions. 
   - Clearly wrong:
     * Not doing what that suppose to do:
       - Make a comment on the PR
       - Send a Direct Message (Slack) to Author to chat about it quickly
       - ** Note: Avoid Back and Forward comments, and open communication
3) Second Pass Through:
  3.1) Small Changes: pretty straightforward stuff go over the github/gitlab/bitbucket
    * Look for best practices
      - Do the names makes sense?
      - Are we using the language features properly (LifeCycles / Typescript (Not javascript way) / Custom Hooks)
    * Unit Tests:
      - Are doing what they say that are doing?
      - Mocks called as properly as a mock feature on Jest/... ?
  3.2) Complicated Changes:
    * Pull down the code, open on IDE.
    * Manually test the changes (Does what says that does?).
      * If not works - Add that to the code review.
    * Make sure that has a consistency path (DataFlows/Rendering Cycle)
    * If is confusing, ask questions (Why is this way, can you explain to me?)
4) Questions about the business requirement (If is confusing, just ask questions)
5) Just Suggestions if needed
     * *** If feel that a change are needed, It's my job convince the other about it.
6) Complement good code
7) What is the outcome of the review (writing)
8) PR Approved:
LGTM :shipit: ==> Looks good to me!


### References: 
Code Review - https://about.gitlab.com/topics/version-control/what-is-code-review/
Drama Free Code Review - https://www.youtube.com/watch?v=Y9sp8gONv9M&t=1s
Pair Programming: https://about.gitlab.com/blog/2019/08/20/agile-pairing-sessions/
Code Review Mindset - https://www.smashingmagazine.com/2019/06/bringing-healthy-code-review-mindset/
