# Pega Developer Productivity Booster: Feature outline

- Top toolbar
    - Icon to open into the application definition
    - Icon to open the search menu
    - Right-click on the branch icon to open your active branch
- Right-click profile icon to open operator profile
- Bottom toolbar
    - Current branch name added
    - Added Logs button
        - Cleaned up the log files UI: important works are prominent and linked
        - Log viewer
            - Always jumps to the latest log: last page
            - Higher default lines per page
            - Bottom toolbar always stays visible
            - No more pages input
            - No more defaulted requestor filter
            - Button to set requestor
            - Clear filter button
            - Search, can click repeatedly to use like a refresh button and it always scrolls to the bottom/latest
    - Clipboard
        - Specific pages can now be sorted to the top
          - It is configurable so you can add your own page names to get this treatment
    - Tracer
        - You can set a countdown to start the tracer after X secons
        - Header is in green when it's tracing
        - You can press the space bar to play/pause
        - When the tracer is running, it shows the state in dev studio on the bottom toolbar
            - This is also synced to portals you have open
- App explorer
    - Refresh button added
    - Added ‘eye’ icon next to classes
        - Left-click to open class record
        - Right-click to open data designer
- Data transform
    - Moved the ‘call superclass’ up to the top
    - A step that calls another DT with ‘pass param page’ enabled now shows a solid cog icon - no more Schrödinger's config
    - Comments steps have a grey background and with fake comment line marker
- Rule headers
    - Left side
        - Last editor summary, and when: useful at a glance to know if a rule’s been modified by someone else, particularly for a branch with multiple authors, or for a lead that’s reviewing code
        - info icon toggles the side bar
        - History icon opens up history popup - no more needing to go to another tab and scroll down
        - The class is now text selectable instead of opening the menu, so you can copy it and paste it somewhere, a chat or a rule etc
        - New icon next to the ruleset if the rule is in a branch: it opens the branch for that rule
        - When a rule is checked out, you can change the ruleset of that rule, instead of needing to save as, delete
        - Rule sharing
            - You can right-click on the rule label and get options to share the rule
              - Why? When you tell someone to look at a rule, they have to search for it, and find the right one. Maybe it’s ‘pyDefault’ and search is useless
            - The text is copied to your clipboard
            - To use it, just paste it into the search box
    - Right side
        - Quick action buttons (contextual, uses the same visibility logic and rule specialisation as the menu actions)
            - Run
            - Trace current rule
            - Siblings
                - Right-clicking opens the version list
            - Open References
            - Refresh
                - Right-click to pop rule into a new window
        - Actions
            - Delete button is now just an icon button
    - Rule status
        - If you delete a rule, the header background changes to a grey-ish colour
        - If you change the availability of the rule to Blocked, Not available, Withdrawn, you get a red background
- The sidebar
    - Every rule now has a 'sidebar' which can be configured to open by default per operator
    - It currently shows 'Description', 'Usage', and your guardrails
- History tab
    - Added a relative date to the history details page
- Class rule form
    - Rearranged the layout to be less tall (less scrolling)
    - DB details are now embedded here - no more clicking on test connection to see the table details
        - And you can go straight to the class table mapping rule
- Activity rule
    - Call activity step shows you if pass param is set
    - Same with Apply DT, we show you the name and pass param setting)
        - You can click on the name of the DT to copy it to your clipboard
- Branch landing page
    - The layout of the right column sections have been cleaned up
    - Current reviewers are shown as well, no more opening the review and action menu just to see the reviewers
    - Table changes
        - Whole table has been rethought/rebuilt
        - Added availability
            - Ever looked at a rule and wondered what it was doing there only to realise it was being withdrawn?
        - Updated by is a user's name and not the ID
        - Update time is relative
        - Columns are appropriate widths so you can see what's in the cells
        - Name is bolded
        - The default sorting is by ‘rule type label’ instead of ‘rule type class’ so the sorting makes sense
        - Added rule review status, combined with checkout status
          - If the rule has been modified since setting the status, it's shown just as it is in the Peer Review component
        - Right-click on a rule to
          - Open the rule in a new window
          - And if there's an active review, you can make it as 'Done' or remove that status without going into the rule
    - Refresh button next to the actions menu
      - And Merge button
- Peer review changes for rules
    - The review toolbar is now a cluster of buttons: Done, Fix, Ask, instead of a menu of status
      - One click to set the status
      - Click again to unset that status
    - Review sidebar
      - The Change log opens expanded
        - If change log is too long, it now has a scrollbar so Pulse isn't pushed off screen
        - UI compacted a bit and the timestamp on the logs is relative
- Default project passwords feature
  - Most projects need only lock a branch or ruleset to prevent accidental edit, but that means SAs need to type 'rule'
    or 'install' 500 times a day. Well no more
  - When you are locking or unlocking a branch or ruleset version, or merging, a button is available to enter the 'standard project 
    password'
    - The default password set in config
  - Can disable this feature entirely in config
    - Can also disable this per-user
- Ruleset view
    - Most recent version is at the top, now descending
    - The detail section is simplified
    - The lock/unlock button also uses the standard password option
    - Lock and unlock a branch by clicking on the lock
- Creating a new rule
    - New feature to correctly capitalise the 'ID' to 'Id'
      - E.g. if you enter 'Entity ID' into the label, the auto-generated name is 'EntityId'
      - Can be disabled in config
    - Exposed a checkbox in the new rule naming screen, so you can see when Pega is going to auto-update your rule name
      - Also so you can disable/enable it if you want more control
- Test cases
    - Run test case button has been added to the UI
    - The results of a test run can be viewed in a popup instead of a new tab
    - Test cases have a new auto-naming pattern
      - E.g. you are authoring a test for the Data transform 'SetSomeData'
        - If you name your test 'Happy path', then the new naming scheme generates it as 'TC_SetSomeData_DT_HappyPath'
      - This is configurable, too
- Application definition
    - Branches
        - More info: branch creator, and optionally, rule count via the checkbox (it’s slow)
        - Delete button removed to prevent a team from overwriting changes to the app definition when adding branches
            - Use the app explorer tab instead
        - Can restore the old table via configuration
        - If you use Jira or Agile studio, if a branch name matches the pattern of a ticket, you'll get a deep link to your
          configured issue tracker
- Data pages
    - A ‘Flush all’ button, so you don’t need to click into a popup
- Admin studio
    - Requestors
        - Sorts Browser to the top
        - Added relative time column
        - Refresh button added to the toolbar
- Grab bag
    - Option to have the toolbar in portals to auto-open (option is in Operator record)
    - Recents: right-click to open a rule by name. Useful if a rule doesn’t exist anymore (merged, deleted) but you still
      want to see the most relevant rule without searching
    - Report viewer
        - Refresh button
        - Header doesn’t go off the edge of the window when there are lots of columns
    - Pressing the space bar activates controls that have 'click' or 'enter' configured actions
      - Fixes the issue where a link button has 'focus' (dashed outline) but you can't activate it with space bar
    - The Work- pyInstance list report now has ‘pyWorkStatus’ as a column
    - If you open a rule that Pega can't find, the pzInsKey is shown on the error screen so you know what rule you tried
      to open
- Configurability
  - Configurations are use Configuration Sets in App Studio
  - The component ships with defaults (everything on)
  - Some options are also in the Operator record