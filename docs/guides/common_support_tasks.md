This guide contains instructions for common support tasks.

The [PaaS Support Manual](https://docs.google.com/document/d/1Ui0MQtZbZnRCIj4RUdqCPU6PdWvfqY9FNf7Ou3OE99w) lives elsewehere, but should be moved into the team manual sometime soon.

## Changing a user's password

1. Set your AWS environment variables to the production environment (assuming this is a production user)
2. Set your `DEPLOY_ENV` environment variable to `prod`
3. Ensure you have the [uaac client](https://github.com/cloudfoundry/cf-uaac) installed
4. Run `./paas-cf/scripts/rotate-user-password.sh -e prod -u user@example.com`

The script will generate a new password for the user, change it, and then email them the password.

## Subscribe and check the AWS notifications

AWS [sends notifications to our maillists](../team/responding_to_aws_alert/). You should subscribe to these groups to get any notification.

## Resetting the user testing organisation

After a user testing lab session, we rotate test user passwords and delete and recreate the `paas_user_testing` org in prod.

We use the same test users each time. They are of the form `holly.challenger+N@digital.cabinet-office.gov.uk` for N 1-6.

If Holly needs anything extra (for example, a Jenkins box provisioned) she will ask on a case-by-case basis.

You need admin access to `cf` in prod to do the reset.

The script lives in `paas-cf`.

## Notifying all users

Occasionally you may need to notify all users of an event on the platform, perhaps during an incident in progress or to send an incident report.

To do this, follow the instructions on [notifying tenants](../team/notifying_tenants/).

## Uncontactable Org Managers

If none of the org managers for a specific org are contactable (for example if they've all left) then the following people within the team are permitted to approve the nomination of another person to be org manager:

- Product Manager
- Delivery Manager
- Technical Architect

Factors in their decision:

- if the org is used for trial/prototyping or live use
- if they are able to make contact with other senior members of the team to whom the org belongs
- if the email account belonging to the absent org manager can be made active again to send an email authorising the change.

We will also email every user currently in the organisation to explain what has been done.
