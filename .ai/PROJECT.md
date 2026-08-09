## Project Overview

This project is a React-based web application for managing and analyzing Clash of Clans Clan War League (CWL) player statistics.

The application maintains a persistent roster of up to 50 players for each CWL period and tracks their participation and performance across seven wars. Each CWL has a configurable war size of 5, 15, or 30 players, and the selected players can be rotated independently for each war.

The application provides a user-friendly interface for creating and managing CWL periods, maintaining the roster, selecting players for individual wars, recording war statistics including stars and destruction rate, and viewing calculated player performance metrics.

Google Sheets will be used as the persistent data store, with a single spreadsheet containing global player data and separate tabs for individual CWL periods.


## Goals

The primary goal of the application is to provide meaningful player performance statistics that can be used to support fair and informed CWL bonus-medal allocation decisions.

The application should:

* Track player participation and performance for each CWL war.
* Provide statistics such as wars selected, attacks used, total stars, and average stars in CWL.
* Make it easier to identify players who performed consistently across the CWL rather than relying only on total stars.
* Eliminate repetitive Excel manipulation and manual calculations through an easy-to-use interface.
* Provide a clear and visually useful presentation of CWL player statistics.
* Allow CWL statistics to be shared with clan members through a web link.
* The application should support bonus-medal decision making by identifying players who demonstrate strong performance relative to the number of wars in which they were selected, rather than ranking players solely by total stars.

## Non-Goals

The following are explicitly outside the scope of Version 1:

* Integration with the Clash of Clans API.
* Automatic retrieval of player, war, or CWL data from Clash of Clans.
* General clan management functionality.
* Clan member management outside the information required for CWL statistics.
* Attack reminders or notifications.
* Chat or communication features.
* Other Clash of Clans game statistics unrelated to CWL performance.

All CWL data in Version 1 will be entered and maintained manually through the application.

## Target Users

### CWL Administrator

The administrator manages the CWL statistics application. The administrator can create CWL periods, manage the player roster, add or deactivate players, enter war participation and performance data, and view the resulting statistics.

Only administrators can modify application data.

### Clan Members

Clan members are view-only users. They can access the application through a shared link, select a CWL period, search for players by name, and view the CWL summary and player performance statistics.

Clan members cannot modify player, roster, or war data.

## Core Capabilities

### CWL Period Management

* Create a new CWL period by specifying its month/name.
* Configure the war size when creating the CWL.
* Support war sizes of 5, 15, or 30 players.
* Automatically create all seven wars when a new CWL period is created.
* Select and view previously created CWL periods.
* Carry forward the previous CWL roster and player active/inactive status when creating a new CWL.
* Allow the administrator to add new players to the roster.
* Allow the administrator to update player active/inactive status for the new CWL.

### Player Management

* Maintain a global player list with a persistent player ID, player name, and Town Hall level.
* Add new players.
* Update player information such as name and Town Hall level.
* Preserve player identity across different CWL periods.
* Maintain a maximum CWL roster of 50 players.
* Mark players as active or inactive for an individual CWL period.
* Display active players before inactive players.
* Sort active players by Town Hall level.

### War Player Selection

For each of the seven wars:

* Allow the administrator to select players from the CWL roster.
* Display only active players in the war-selection interface.
* Allow players to be rotated between different wars.
* Enforce the configured war size for the CWL.
* Prevent selecting more players than the configured war size.
* Alert the administrator when attempting to select a player would exceed the configured war size.

For example, if the CWL war size is configured as 5, no war can contain more than five selected players.

### War Data Management

For every selected player in every CWL war, the administrator can manually record:

* Whether the player was added to the war.
* Whether the player used their attack.
* The number of stars scored.
* The destruction rate achieved in the war.

### Player Statistics

The application calculates and displays player performance statistics, including:

* Number of wars selected.
* Number of attacks used.
* Total stars scored.
* Average stars per selected war.

The destruction rate for each individual war is stored as manually entered war-level performance data.

Statistics are calculated from the underlying war-level data rather than being manually stored.

### Viewer Experience

Viewers have read-only access to CWL statistics.

They can:

* Select a CWL period.
* View the CWL player summary.
* Search/filter players by name.
* View each player's Town Hall level, wars selected, attacks used, total stars, and average stars.
* View the statistics without being able to modify any data.

### Data Persistence

* Use a single Google Spreadsheet as the application's data store.
* Maintain global player information in a dedicated player tab.
* Maintain separate tabs for individual CWL periods.
* Preserve historical CWL data when new CWL periods are created.

### Bonus Medal Evaluation

The application should provide statistics that help the administrator evaluate players for CWL bonus medals.

Bonus-medal evaluation must not be based solely on total stars.

Players who participate in fewer wars but demonstrate stronger average star performance should be considered alongside players who participate in more wars.

For example:

* A player selected for 7 wars and scoring 14 stars has an average of 2.00 stars per selected war.
* A player selected for 4 wars and scoring 11 stars has an average of 2.75 stars per selected war.
* The player with the 2.75 average should be considered a stronger performer despite having fewer total stars.

When players have comparable star performance, their destruction rates should be used as an additional comparison factor.

Destruction rate is recorded separately for each war. For bonus-medal evaluation, the destruction rates from the player's selected and played wars are summed to produce a cumulative destruction score.

When players have equivalent or comparable star performance, the player with the higher cumulative destruction score should rank higher for bonus-medal consideration.

The application should display the underlying statistics used for this evaluation so that the administrator can make the final bonus-medal decision.

## Constraints

The following business constraints apply to Version 1:

* A CWL period contains exactly seven wars.
* A CWL roster can contain a maximum of 50 players.
* Each CWL has a configured war size of 5, 15, or 30 players.
* The war size is selected when the CWL period is created.
* The configured war size applies to every war within that CWL period.
* Players can be rotated between wars.
* Only players marked as active for the CWL can be selected for a war.
* Inactive players must not be displayed in the war-selection interface.
* The number of selected players for a war cannot exceed the configured war size.
* The application must alert the administrator when a selection would exceed the configured war size.
* Player identity is persistent across CWL periods.
* Town Hall level is maintained as global player information.
* CWL active/inactive status is period-specific.
* War participation and performance are specific to each individual war.
* Statistics must be calculated from the underlying war data.
* Historical CWL data must remain available when new CWL periods are created.
