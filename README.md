# [Sentry](https://getsentry.com/welcome/) vagrant box

### Test the playbook in vagrant

- Run `vagrant up`
- Add `192.168.33.90 sentry.server` to `/etc/hosts`
- Run `vagrant ssh`
- Run `/www/sentry/bin/sentry --config=/etc/sentry.conf.py changepassword admin@sentry.local` and set a password
- Go to `http://sentry.local`
- Log in with `admin@sentry.local

### Variables

```yml

sentry:
    user: sentry
    home: /www/sentry
    virtualenv: /www/sentry/
    template: sentry.conf.py
    admin_username: admin
    admin_email: admin@sentry.local
    admin_password: admin
    hostname: sentry.local
    server_email: sentry@sentry.local
    secret: VDpBG3DQOapXLkDqQDt8ToJd4ty6/1GOvpTHUO4o0sHtDIMAIKzxZQ==
    port: 9000
    mailgun_key: ''
    extensions: [ "sentry-jira", "sentry-slack" ]
    twitter_consumer_key: ''
    twitter_consumer_secret: ''
    facebook_app_id: ''
    facebook_api_secret: ''
    google_oauth2_client_id: ''
    google_oauth2_client_secret: ''
    github_app_id: ''
    github_api_secret: ''
    trello_api_key: ''
    trello_api_secret: ''
    bitbucket_consumer_key: ''
    bitbucket_consumer_secret: ''

pgsql:
    user: sentry
	  password: sentry
	  database: sentry
	  auth_template: pg_hba.conf.j2

supervisor:
    port: 9001
    username: supervisor
    password: supervisor

```
