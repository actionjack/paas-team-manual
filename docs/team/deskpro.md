[Deskpro](https://www.deskpro.com/) is the GaaP support tool. Each team customises it for its needs.

You need to be admin to change the settings.

*Basic manual setup should be documented here*

## Emergencies

## Email account

A `@gaap.deskpro.com` [email account](https://gaap.deskpro.com/admin/admin-interface#/tickets/ticket_accounts) is set up for emergencies. We don't currently use an `@digital.cabinet-office.gov.uk` address because we aren't confident that emails won't get caught by moderation and spam filters.

* The priority is set to `P1`.
* It has an action `Send email`:
  * Send to the emergency Pagerduty address
  * Based on template `gov-uk-paas-emergency.html`
* Set Email Account: normal support email address (otherwise the conversation continues on the emergency email address)

## Custom email template

The [custom email template](https://gaap.deskpro.com/admin/admin-interface#/tickets/email_templates/custom) is called `gov-uk-paas-emergency.html`.

The subject and body can be edited. See the [documentation](https://manuals.deskpro.com/html/admin/editing-templates/email-templates.html) for more information. In particular, [predefined](https://gaap.deskpro.com/admin/admin-interface#/setup/phrases-default) or [custom phrases](https://manuals.deskpro.com/html/admin/editing-templates/intro-templates.html#custom-phrases) can be inserted as well as [template variables](https://manuals.deskpro.com/html/admin/editing-templates/template-variables.html).

To make the Pagerduty alert meaningful, the content should show at least:

* Original email subject
* Original email body
* Link to the Deskpro ticket
* Ticket author
* Ticket creation date and time
