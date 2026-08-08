## Project Overview

This project is a React-based web application for managing and analyzing Clash of Clans Clan War League (CWL) player statistics.

The application allows players to be maintained as a persistent roster while tracking their participation and performance separately for each CWL period. Each CWL period consists of seven wars, with player participation, attack usage, and stars recorded independently for every war.

The application provides a user-friendly interface for creating and managing CWL periods, maintaining the roster, recording war statistics, and viewing calculated player performance metrics.

Google Sheets will be used as the persistent data store, with a single spreadsheet containing a global player data tab and separate tabs for individual CWL periods.

## Goals

The primary goal of the application is to provide meaningful player performance statistics that can be used to support fair and informed CWL bonus-medal allocation decisions.

The application should:

* Track player participation and performance for each CWL war.
* Provide statistics such as wars selected, attacks used, total stars, and average stars in CWL.
* Make it easier to identify players who performed consistently across the CWL rather than relying only on total stars.
* Eliminate repetitive Excel manipulation and manual calculations through an easy-to-use interface.
* Provide a clear and visually useful presentation of CWL player statistics.
* Allow CWL statistics to be shared with clan members through a web link.

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
