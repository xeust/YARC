## yarc


### General Info

*yarc* gives you a "box" of notes. It is a minimal micro-homage to the bi-directional linking in tools like [Roam Research](https://roamresearch.com/).

#### Notes

Every note has a url at: `:base_url/notes/:note_name`

The notes are also accessible via API:

`GET :base_url/notes/:note_name?json=true`

You can edit notes using the **edit** button, writing regular markdown. **save** will save your changes and switch to a notes view.

You can link to any note in your box using the convention **[[note_name]]**.
- This creates bi-directional links. 

A list of all notes that link to the present note are under a header **Backlinks**.

#### Home

The home page lets one search for or go directly to notes.

- **search**: brings up all notes that contain a given query.
- **go**: brings you directly to a (potentially new) note.


### Deploying

My instance of yarc is running on [Deta](https://www.deta.sh/).

It could, with little modification, be configured to run elsewhere (it's a FastAPI app), but a database is needed.

#### On Deta

1. Clone the GitHub repo.

2. Login to the [Deta](https://web.deta.sh/) web app, and a 'default project' will be created (if you have a project, you can skip this step).

3. Install the [Deta CLI](https://docs.deta.sh/docs/cli/install) and use 2 commands from within the yarc directory:

```
deta login
```

```
deta new
```


Your copy of *yarc* should be live for personal use (you can get the url from a `deta details` cli command or from the Micros dashboard within Deta).

The endpoint and "box" are protected by default, but is accessible if one is logged in to Deta, with api keys, or by making it public.

### Libraries Used

- [FastAPI](https://fastapi.tiangolo.com/)
- [Jinja2](https://jinja.palletsprojects.com/en/2.11.x/)
- [Bleach](https://bleach.readthedocs.io/en/latest/clean.html)
- [Deta](https://www.deta.sh/)
- [hyperapp](https://github.com/jorgebucaran/hyperapp)
- [Showdown](http://showdownjs.com/)
- [CodeJar](https://github.com/antonmedv/codejar)
- [highlightjs](https://highlightjs.org/usage/)
