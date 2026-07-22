# ***Community Bonding Period: 1 May – 24 May***

## ***05/01 Fri***

Discovered that my proposal got accepted for GSoC 🎉😊 and communicated with mentors regarding collaboration, communication channels, and how we will track progress throughout the project period.

## ***05/02 Sat***

Explored the repositories of BRL-CAD, Arbalest, and MOOSE, started setting up the development environment, completed the initial installations, and encountered configuration/build issues while setting up MOOSE.

## ***05/03 Sun***

Investigated and worked on resolving MOOSE-related issues, rebuilt BRL-CAD from source, and fixed the GDAL-related build issue by disabling the GDAL option during configuration.

## ***05/04 Mon***

Attempted to build the project environment on Windows once again, but the build process failed due to multiple Windows-specific dependency and configuration issues.

## ***05/05 Tues***

Shifted focus completely to Linux-based development, successfully built and ran BRL-CAD on Linux, and started moving towards MOOSE setup and integration.

## ***05/06 Wed***

Successfully built MOOSE, but while building Arbalest, the build process reached 100% and failed during the linking stage with multiple undefined reference errors related to BRL-CAD functions such as `bu_malloc`, `rt_shootray`, and `BRLCAD::CommandString`, along with a warning regarding `librt.so.20` not being found from `/usr/local/lib/libbrlcad.so`.

## ***05/07 Thurs***

Followed mentor advice to change installation paths using isolated local installations, encountered additional issues related to `RPATH`, `brledit`, and installation path mismatches, and cleaned and rebuilt the complete environment from source again, which took approximately 4 hours for reconfiguration and rebuilding.

## ***05/08 Fri***

Continued reorganizing installation paths and rebuilding the environment in a new workspace layout, correctly enabled the `MODULE_COMMANDSTRING=ON` option in MOOSE, fixed Qt compatibility issues in Arbalest source files, and successfully built and ran Arbalest 🎉

## ***05/09 Sat***

Understanding the code and logic behind Verification and validation in arbalest(old fork).

## ***05/10 Sun***

Understanding the workflow of the project and how plugin will work.

## ***05/11 Mon***

Tried to do plugin in arbalest with the old fork and understand what changes are there in old fork and latest arbalest.

## ***05/12 Tues***

Attended GSOC welcome session and contributor talk.

## ***05/13 Wed***

Does experiment with latest arbalest and added vv as a dock widget and understanding the old fork.

## ***05/15 Fri***

Added Verification and Validation Functionality to menu bar and at the bottom of arbalest and experiment with loading geometry .

## ***05/16 Sat***

Added compile run and stop feature for vv and a popup box on clicking on warnings which give the suggested fixes and illustrate issues.

## ***05/17 Sun***

Added more option in the menu VV function like create test suit, create test, remove test suite, remove test and export csv. Also Added that if in the geometry name if spacing is there or bar space that it can detect.

## ***05/18 Mon***

Added QTreeWidget in the VV and the popup box when click on issues and warnings. Also organised those files in the separate folder(plugins).

## ***05/19 Tues***

Analysing the old UI/UX workflow and features.

## ***05/20 Wed***

Added Export feature and live summary count bar to the latest arbalest.

## ***05/21 Thurs***

Exploring Backend codebase and understanding the logic.

# ***Coding Period***

# ***Week 1: 25 May - 31 May***

- 25 May: Reviewed the V&V implementation, validated UI integration, analyzed plugin architecture feedback, and requested mentor clarification on MainWindow vs plugin-based integration before proceeding with backend development.
- 26 May: Draft initial PR for architectural review. PR Link - https://github.com/BRL-CAD/arbalest/pull/76
- 27 May: Analayse the backend work of old fork and planning of creating how backend workflow will be integrated in the latest arbalest.
- 28 May: Reviewd and planned next-stage V&V result/report handling architecture.
- 29 May: Explored next implementation direction for validation result management and report generation workflow.
- 31 May: Fix Mainwindow.h syntax error in V&V integration in the PR - https://github.com/BRL-CAD/arbalest/pull/76

# Week 2: 01 June - 07 June 

- 01 June: Address V&V review feedback commit in the PR - https://github.com/BRL-CAD/arbalest/pull/76
- 02 June: Analyzed the current validation flow and evaluated whether the timer mechanism is necessary for existing string-based checks.
- 03 June: Awaiting further review/comments before proceeding with additional implementation changes.
- 04 June: Fix the VV cleanup when document is closed in the PR - https://github.com/BRL-CAD/arbalest/pull/76
- 05 June: Cleanup the PR  - https://github.com/BRL-CAD/arbalest/pull/76 by reverting some changes and removing whitespaces.
- 06 June: Add the new missing line at the end of each file.

# Week 3: 08 June - 14 June 

- 08 June: PR got merged successfully. PR - https://github.com/BRL-CAD/arbalest/pull/76
- 09 June: Asked about direction for Moose integration or result handling or any next steps.
- 11 June: Got the guidance to move ahead and and explored codebase to integrate moose and asked some questions.
- 12 June: Got the code guidance about CommandString and tried to implement it.
- 13 June: Tried the moose implementation and group the test selelction box.
- 14 June: Fix some crash issue and raised the PR- https://github.com/BRL-CAD/arbalest/pull/77 for review.

# Week 4: 15 June - 21 June 

- 15 June: Update getDatabase() return type to BRLCAD::Database in PR - https://github.com/BRL-CAD/arbalest/pull/77
- 16 June: Commited in the PR (some ui backend fix)
- 17 June: Check and test some geometries in the arbalest plugin vv.
- 18 June: Got the feedback about test and explain why some test are skipped.
- 19 June: Got the advice about the gqa based test and understand it well about objectName and objectPath.

# Week 5: 22 June - 28 June 

- 22 June: Work on objectName and ObjectPath and also improve vv logic in tests.
- 23 June: Commited in the PR - https://github.com/BRL-CAD/arbalest/pull/77 some changes and test the tests on geometries.
- 24 June: Explained about my approach baout resolvedPath on Zulip.
- 25 June: Just ask about should I refactor the code according to the Isaac Version.
- 27 June: Just tried and tested with havoc.g geometry with my current implementation and address some path string issues.
- 28 June: As a side experiment tried Isaac's approach of objectname and objectpath leads some errors.

# Week 6: 29 June - 5 July 

- 29 June: Finally fix the error and implemented Isaac's approach and tested geometry on that and share the results in chat.
- 30 June: As results looks reasonable so I ask guidance about which approach to take on and get commit in the PR.
- 01 July: Improve GQA based validation logic and commit in the pr. Finally after final review PR - https://github.com/BRL-CAD/arbalest/pull/77 got merged successfully.
- 02 July: To work on next task - Focus on to do fine tuning to the vv test and ask about my approach about implmentation.
- 03 July: Attended project meeting - Discussed about progress till now and next half improvements and tasks.
- 04 July: Tested on multiple geometries and made a mid term summary in short 1-page and documented all progress made so far.
- 05 July: Have not sure about results table improvement so asked about it and posted the mid-term progress in the chat.

### Mid-Term Evaluation : Passed

# Week 7: 6 July - 12 July 

- 06 July: Updated or improved the results table and separate each issues in one row and asked for guidance about duplicate ID Check.
- 07 July: Made the dropdown for filtering the errors, warnings and passed test and fixed it on right side of summary pannel.
- 08 July: Made a plan about how to implement result report and what content it has in report(like errors, warnings, passed) and decided structure.
- 09 July: Implemented a result report feature(Rough work) with taking results from the backend and show it in report(Txt and CSV) and done a clean rebuild and fixed some errors(Logic only).
- 10 July: Fixed some JSON Logic and updated duplicate ID Region in results table and tested it with havoc.g and shipping_container.g. Also watched the video of the v&v and undertsand it.
- 11 July: Fixed the updated duplicate ID Format in results table.
- 12 July: Just tried to implement it in arbalest(Experimented), the result report concept but ran into errors and tried to fix it.

# Week 8: 13 July - 19 July 

- 13 July: Again understanding the architecture of the project and how will plugin be connected to arbalest and how will it be registered. Gone through the old fork code and tried to understand about features and how will it get implemented in latest arbalest.
- 14 July: Added Icons folder in the plugin vv.
- 15 July: Implemented Icons in errors, warnings, and passed test in results table.
- 16 July: Fixed some errors in icon implementation done a clean rebuild and added progress bar in implementation.
- 17 July: Fixed some UI work for progress bar.
- 18 July: Fixed redundant entry of V&V and Verification & Validation in UI table header and Shared the update in chat.
- 19 July: Finding the logic behind visual linking feature and about code structure as how it will fit into plugin.

# Week 9: 20 July - 26 July

- 20 July: Experimented some logic of visual linking feature but ran into error(segmentation fault).
- 21 July: Tried to fix the segmentation fault but after that it only show full geomtry in viewport by clicking on issue.
- 22 July: Fixed the logic to show only error based geometry in viewport and hide other parts but it worked in shipping_container.g not on havoc.g so still finding the correct logic.
