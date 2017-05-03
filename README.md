# StellaDMS

[![Greenkeeper badge](https://badges.greenkeeper.io/bdfoster/stella-dms.svg)](https://greenkeeper.io/)

StellaDMS is an open source 
[document management system (DMS)](https://en.wikipedia.org/wiki/Document_management_system)
built with Node.js. Specifically, it allows users to track, manage, and store digital
documents.

**PLEASE NOTE: This project is nowhere near ready for production use.** Active development is
taking place, and we expect to have the first production-ready release by October, 2017.
Contributions in the form of code, ideas, or bug reports are always welcome.

## Summary
* **API First**: All functions of StellaDMS are available via a JSON-based RESTful API. Other interfaces
  (such as the web client) are built on top of the API.
* **Accounts**: Access to documents are controlled by two account types: `user` accounts and `client`
  accounts. `user` accounts are mappable to a human, `client` accounts are mappable to an application.
* **Granular Access**: A `scope`-based authorization system allows administrators to govern access
  to documents.
* **Documents**: Documents can be in the form of files, such as PDFs, or in the form of data, such as JSON
  or XML. Revision tracking can be enabled to allow each `document` to be updated, which allows users
  to see the history of each version of the `document`.
* **Groups**: A `group` is essentially a set of `account`s that inherit specific `scope`s. By default, three
  `group`s exist:
  * `authenticated`: All `account` types have this by default. It is implicit, in a sense, because no `account`
    will show this as a one of their `group`s.
  * `public`: This `group` is also implicit, and is used for un-authenticated users.
  * `admin`: Administrators of the system are given this `group`. Only `user` accounts can be assigned this
    group. Users of this group can create, manipulate, or destroy any `resource` type by default.

## Documentation
[Scopes](docs/scopes): An explaination of how scopes work in StellaDMS.
