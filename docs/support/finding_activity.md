# Finding the activity for a given user

In case of suspicion of compromised CF details, we can use Kibana to
obtain some information about the API use.

## Finding user GUID

You may need to obtain this, to move the investigation forward. It's
usually useful, to have a starting point in the form of organisation.
Possessing that name, use this command, to obtain users from the
organisation:

```
$ cf curl "/v2/users?q=organization_GUID:$(cf org ORG_NAME --guid)"
```

**Note:** It may be a big chunk of JSON, which you may want to export
into a file.

Each user as an entity, will have metadata enclosed. This metadata will
have users GUID.

### Finding deleted user GUID

There may be a need to find a GUID for already deleted user. There is a
way to do that, but it's a little inconvenient...

If you go to Kibana, you can use the `"DELETE \"/v2/users"` phrase in
your search. This will print out the logs that were taken on user
removal. This does not however, give you an indication of who the user
was.

## Kibana: Finding API usage

We can make the investigation easier for ourselves by considering the
following criteria:

- Filter by user: `"for user: {GUID}"`
- *Optionally:* Scope to job: `api`
- `@message` should consist of:
	- Detailed endpoint
	- The response code, time
	- IP address
	- vcap_request_id

It probably won't end here, but it should provide a start for an
individual to go further.

