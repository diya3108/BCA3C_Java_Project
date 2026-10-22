# UPI Pay Desktop

A Java Swing desktop demonstration of local, simulated UPI-style payments. It is for academic demonstration only: there is no real UPI, bank, or payment network connection.

## Features

- Account registration and login using a salted, iterated PIN hash.
- Simulated accounts with persistent balances and local SQLite storage.
- Explicit Add Demo Money operation.
- Atomic transfers between registered users, with balance validation and transaction receipts/history.
- Receive screen with the user's UPI ID; an incoming payment must originate from another registered user.
- Transaction history, dashboard totals, basic reports, profile view, and PIN management.
- Forest-green Swing interface with navigation, a dashboard balance card, four metrics, recent transactions, quick actions, account details, and a security card.

## Seven modules

1. Registration, login, and sessions.
2. Simulated accounts and balances.
3. Send Money.
4. Receive Money.
5. Transaction History.
6. Security and PIN management.
7. Dashboard, reports, and analytics.

## Technology and prerequisites

- Java 17 or newer (built with Java 26 in the supplied environment).
- Maven 3.9+ for a network-enabled Maven build.
- Java Swing, SQLite JDBC, SQLite, and BigDecimal/integer paise for money calculations.

## Run

Double-click `outputs/UPI-Pay-Desktop.jar` or run `java -jar outputs/UPI-Pay-Desktop.jar`. Create a user in the login screen. Register a second user to test transfers. Add demo money explicitly, then send money to the second user's UPI ID. Recipient and sender balances update together. Transaction records persist across restarts.

Database location is `upipay-data/upipay.db`, relative to the working directory used to launch the application. Back up that folder to preserve demo records.

## Build and tests

With Maven Central access, run `mvn package` to build the shaded executable JAR. Maven dependencies could not be downloaded in the build environment used for this artifact; the supplied JAR was compiled with `javac` and packaged with the cached SQLite JDBC dependency instead. No automated tests are included in this delivered build, and no test suite was run.

## Limitations

- Payments are simulations and never move real money.
- This is a university demo, not a production banking application.
- Local SQLite data is not encrypted at rest; do not use real credentials or personal financial information.
- The dashboard follows the supplied layout reference, adapted to a forest-green theme. Some decorative illustrations and icon details are simplified for the Swing implementation.
- Email is collected but not verified; profile editing, advanced search, filters, monthly reports, and failed-attempt auditing are not implemented in this initial build.

