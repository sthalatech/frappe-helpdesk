# frappe-helpdesk

Custom Frappe app for internal departmental helpdesk with team-based permissions: agents get full access to their team's tickets, other teams get read-only visibility into tickets they raised.

## Install

```bash
bench get-app https://github.com/sthalatech/helpdesk_internal_custom.git
bench --site <site-name> install-app helpdesk_internal_custom
bench --site <site-name> migrate
```

Requires Frappe Framework v15+ and the Frappe Helpdesk app installed. After installing, create teams under Helpdesk > HD Team, assign each user's `Assigned Team` field, and grant one of the custom roles (`Helpdesk User Internal`, `Helpdesk Manager Internal`, `Helpdesk Admin Internal`).

## Usage

```bash
bench --site <site> execute helpdesk_internal_custom.test_setup.test_ticket_access
```

Tickets automatically track `originating_team` (the creator's team, immutable) and can be assigned to any team via `agent_group`. Users with `Helpdesk Admin Internal` see all tickets regardless of team.

## Contributing

Issues and PRs are welcome. For significant changes, please open an issue first to discuss what you'd like to change.

## Reporting Issues

Found a bug or have a feature request? [Open an issue](../../issues/new) with steps to reproduce (or the use case, for feature requests).

## License

MIT © Sthala
