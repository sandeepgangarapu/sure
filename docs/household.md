# Household setup

This fork starts with the name **Household Finance** and owner **Our Household**.
Sure's existing household accounts, invitations, sharing permissions, budgets and
goals provide the foundation for our version.

## Customize the name

Set these values in `.env.local` for development or `.env` for Docker Compose:

```dotenv
PRODUCT_NAME="Household Finance"
BRAND_NAME="Our Household"
```

`PRODUCT_NAME` appears in the browser title, installable web app, signup screen
and invitation emails. `BRAND_NAME` identifies the owner in the footer.
The example environment files and Docker Compose configuration include both.

The existing logo and app icons are still Sure's. Replacing those assets is a
separate branding step once we choose our household's final name and look.

## Run the app

For a self-hosted instance, follow the [Docker hosting guide](hosting/docker.md).
The example Compose file runs Sure's published image with our branding settings.
Changes to application code in this fork require building our own image from the
repository's `Dockerfile`.

For development, follow the [local setup instructions](../README.md#local-development-setup).
The repository requires Ruby 3.4.9, PostgreSQL and Redis. Use
`.env.local.example` as the starting configuration.

## Add household members

1. Create the first account and finish onboarding.
2. Open **Settings → Profile Info** and use **Add member** to invite each person
   into the same household. Separate signups normally create separate households.
3. On a self-hosted instance, copy and share the invitation link directly; the
   invitation controller does not send invitation emails in self-hosted mode.
4. Choose the member's role and review which accounts are shared with them.
5. After the initial setup, use **Settings → Self-Hosting** to switch onboarding
   to invite-only and manage signup codes.

## Keep the fork up to date

The local checkout keeps the original project as `upstream` and our GitHub fork
as `origin`. To bring upstream changes into a working branch:

```sh
git fetch upstream
git merge upstream/main
```

Review and test updates before deploying them to the household instance.
