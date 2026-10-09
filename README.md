# Campus 360 enhanced Flask app

## Features
- Student registration/login and complaint tracking
- Admin complaint queue, worker assignment and student management
- Worker sign-in at `/worker/login`, assigned-task dashboard at `/worker`, and status updates restricted to assigned complaints
- Enhanced rule-based assistant, emergency contacts UI, and help center
- Vercel entrypoint and configuration

## Vercel deployment
Set Root Directory to the folder containing `app.py`. Add environment variables `SECRET_KEY`, `ADMIN_EMAIL`, and `ADMIN_PASSWORD`. Deploy from GitHub.

Important: SQLite and uploads are stored under `/tmp` when VERCEL is set, so they are temporary and not suitable for production student data. Connect a managed persistent PostgreSQL database and object storage before real use. The assistant is rule-based, not a generative AI service. Demo campus contact numbers must be replaced with verified numbers.

## Local run
`python -m pip install -r requirements.txt`
`python app.py`

## Worker accounts
An admin creates worker accounts from Admin → Workers, entering a unique email and a password of at least 8 characters. Workers sign in from the main login page's Worker sign in link at `/worker/login`.
