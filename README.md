# CTRI Website

The official website for [CTRI](https://ctri.ng) — the Curriculum and Textbook Resource Initiative, an initiative of [Care for Knowledge](https://careforknowledge.org).

Built with Jekyll, hosted on GitHub Pages.

---

## Pages

| Page | URL | Purpose |
|---|---|---|
| Homepage | `/` | Overview of CTRI, the three barriers, subjects, how it works |
| Textbooks | `/subjects/` | Grid of all five subjects |
| Subject page | `/subjects/[subject]/` | Leads, description, full chapter roadmap |
| About | `/about/` | Theory of change in accessible language |
| Team | `/team/` | Programme team and all subject leads |
| Volunteer | `/volunteer/` | Open roles, how to get involved |

---

## Everything you need to update lives in `_data/`

```
_data/
├── team.yml                    ← Programme Coordinator and Volunteer Manager
├── volunteer_roles.yml         ← Open volunteer roles (add/remove by changing status)
└── subjects/
    ├── mathematics.yml
    ├── physics.yml
    ├── chemistry.yml
    ├── biology.yml
    └── agricultural-science.yml
```

---

## Common tasks

### Update a chapter status
Open `_data/subjects/[subject].yml`, find the chapter, change `status:` to one of:
- `Not Started`
- `Started`
- `In Progress`
- `Under Review`
- `Published`

When `Published`, also set `version:` (e.g. `1.0`) and `url:` (the download link).

### Add a volunteer role
Add a block to `_data/volunteer_roles.yml`:
```yaml
- title: "Role Title"
  subject: "Mathematics"
  status: "open"
  commitment: "X hours per week"
  description: "..."
  what_you_will_do:
    - "Task one"
    - "Task two"
  apply_url: "https://..."
```

### Remove/fill a volunteer role
Change `status: "open"` to `status: "filled"` or `status: "paused"`. The role disappears from the volunteer page automatically.

### Update subject leads
Edit the `writing_lead:` or `creative_steward:` block in the relevant `_data/subjects/[subject].yml`. The `fellow_slug` field links to their CFK Fellowship profile and loads their photo automatically.

### Add a team member
Add a block to `_data/team.yml`:
```yaml
- name: "Full Name"
  role: "Their Role"
  linkedin: "https://linkedin.com/in/..."
  fellow_slug: "their-slug"   # leave blank if not a CFK Fellow
  photo_override: ""           # leave blank to use Fellowship photo
```

---

## Running locally

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`.

## Deployment

Push to `main`. GitHub Pages builds and deploys automatically.

---

## Colour system

| Token | Value | Use |
|---|---|---|
| `--red` | `#F60700` | Primary CTA, borders, badges |
| `--orange` | `#FF7803` | Accent, creative steward label |
| `--yellow` | `#F7D100` | Accent, highlights |
| `--black` | `#171717` | Hero, nav, dark sections |
| `--white` | `#FEFEFE` | Light backgrounds |
