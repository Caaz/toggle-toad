# Toggle Toad

A settings/feature flag/whatever tool for managing deployments externally, without needing to fiddle with redeploying.

## Development

I'm still figuring this out, but here's what I'm doing!

### Prerequisites
In theory, you'll need docker compose set up. I imagine Podman would work as well.

### Running a local development server
- `docker compose run backend bash`
    - Gets you into the shell for running the following commands:
    - `python manage.py reset_db`
        - Initializes the DB, great for when things break.
    - `python manage.py migrate`
        - Runs the migrations necessary for the project.
    - `exit`
        - Gets you out of this shell, you should be good.
- `docker compose up` 
    - This'll start all the services, and assuming I did things right, changes locally will update the container.

### Running in production

Buddy I'm not even there yet