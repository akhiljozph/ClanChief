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
