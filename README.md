<div align="center">

# From Models to Marketplace

**A Django service marketplace, built to understand what `startapp` actually hides from you.**

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-Backend-092E20?style=flat&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Live Demo](https://img.shields.io/badge/demo-live-success?style=flat)](https://ahmadhussain.pythonanywhere.com)

[**Live Demo**](https://ahmadhussain.pythonanywhere.com) · [Features](#what-it-does) · [Architecture](#how-its-put-together) · [Getting Started](#getting-started) · [What I'd Change](#what-id-do-differently)

</div>

---

## Why this exists

Most Django tutorials stop the moment `runserver` prints a green URL. They never make you answer the harder questions: What happens when three models need to reference each other cleanly? What does an admin panel look like when it's built for someone who isn't you? What breaks the first time you deploy to a host that isn't your laptop?

This project is where I went looking for those answers. It's a small service marketplace — services tied to store locations, reviews attached to services, certificates attached to services — deployed and actually reachable, not just running locally and screenshotted for a portfolio.

It's not trying to be a real business. It's trying to be an honest exercise in the full lifecycle: **model it, build it, style it, ship it.**

---

## What it does

| | |
|---|---|
| 🗂️ **Browse services** | A catalog of services, each with its own detail page |
| 📍 **Filter by store** | Narrow the catalog down to a specific store location |
| ⭐ **Reviews** | Users can read and leave feedback on individual services |
| 📜 **Certificates** | Services can carry certificates — a credibility layer, not just a listing |
| 🛠️ **A real admin panel** | Customized Django admin, built so a non-developer could manage the catalog without touching code |

---

## How it's put together

```
my_project/
├── services/          → the actual product: models, views, forms, admin
├── theme/              → django-tailwind build pipeline, isolated from logic
├── templates/           → shared layout + page templates
├── static/ & media/      → styling and uploaded assets
└── my_project/            → settings, routing, WSGI entrypoint
```

A few decisions were deliberate, not defaults:

- **`services/` and `theme/` are separate apps.** Styling churns constantly during development; business logic shouldn't be caught in that blast radius. If I rip out Tailwind tomorrow, `services/` doesn't notice.
- **The admin panel is customized, not scaffolded.** Django gives you a working admin for free, but "working" and "usable by someone who isn't me" are different bars. Getting the second one right was most of the actual learning here.
- **SQLite, on purpose, for now.** This is a single-node, low-traffic deployment on PythonAnywhere. Reaching for Postgres before there's a reason to would be solving a problem I don't have yet — but it's the first thing that changes if this ever needs to hold real traffic.

---

## Tech Stack

- **Backend:** Django
- **Frontend:** HTML + Tailwind CSS (via `django-tailwind`)
- **Database:** SQLite (dev), portable to Postgres for production-scale traffic
- **Hosting:** [PythonAnywhere](https://www.pythonanywhere.com)

---

## Getting Started

**Prerequisites:** Python 3.8+, Git, and Node.js if you want to rebuild Tailwind's static assets.

```bash
# Clone and enter the project
git clone git@github.com:AhmadHussainRandhawa/servicebay.git
cd servicebay/my_project

# Isolate your environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# Install, migrate, and (optionally) get an admin login
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser

# Run it
python manage.py runserver
```

The app lives at `http://127.0.0.1:8000/`, the admin panel at `/admin`.

---

## Deploying your own copy

1. Push to GitHub, then open a Bash console on PythonAnywhere and clone it.
2. Build the virtual environment and install dependencies as above.
3. In the **Web** tab, point the working directory and WSGI file at `my_project/wsgi.py`.
4. Run migrations on the remote console, then reload the web app.

---

## What I'd do differently

The most useful part of a portfolio README isn't the list of what works — it's the list of what I now know I'd build differently, because that's the actual evidence of learning:

- **Ship with tests, not add them later.** `tests.py` exists and is mostly empty. In hindsight, writing even three or four tests alongside each model would have caught migration mistakes I only found by clicking around manually.
- **Star ratings, not free-text reviews.** Free text is easy to build and hard to aggregate. A 1–5 scale with optional text is a small change that would make reviews actually useful for browsing decisions, not just decorative.
- **Auth from day one.** Retrofitting user accounts onto a project that didn't plan for them is more painful than starting with `django.contrib.auth` wired in from the first commit.
- **A CI workflow.** Right now "does it still work" is answered by running it locally. A GitHub Actions job running migrations and tests on every PR is the obvious next commit.

---

## Roadmap

- [ ] Move from illustrative listings to real, transactable services
- [ ] User authentication and accounts
- [ ] Star ratings on reviews
- [ ] Advanced search and filtering
- [ ] Test coverage for `services/`
- [ ] CI pipeline

---

## Contributing

```bash
git checkout -b feature/your-feature-name
git commit -m "feat: describe what changed, following Conventional Commits"
git push origin feature/your-feature-name
```

Then open a PR against `master`.

---

## License

Licensed under the [MIT License](./LICENSE).

---

## Contact

**Ahmad Hussain Randhawa**
📧 official.ahmadrandhawa@gmail.com · 🐙 [GitHub](https://github.com/AhmadHussainRandhawa) · 💼 [LinkedIn](https://www.linkedin.com/in/ahmad-hussain-randhawa/)
