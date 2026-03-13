# Voice Guide: <project-name>
**Layer 3 — Project Reference**

This file defines the tone and style for all text produced in the context of this project: commit messages, PR descriptions, code comments, README content, and inline documentation.

## Tone

```
overall-tone:       # e.g. concise and technical, friendly and clear, formal
```

## Commit messages

```
style:              # e.g. imperative ("add", not "added"), short subject line
max-subject-length: 72
body:               # when to include a body: always / on non-trivial changes / rarely
emoji:              # yes / no
```

**Examples of good commit messages for this project:**
```
# Example 1:
feat(auth): add JWT refresh token rotation

# Example 2:
fix(api): return 404 instead of 500 for missing resources
```

## PR descriptions

```
template:           # link to .github/pull_request_template.md if exists
focus:              # what the PR description should emphasise: why / what / both
```

## Code comments

```
when-to-comment:    # intent only / complex logic / public API
style:              # sentence case, no period / full sentences
jsdoc-or-docstrings: yes/no
```

**Example of a good code comment for this project:**
```
# Write an example here that reflects the project's actual style
```

## README and documentation

```
audience:           # internal developers / external API consumers / end users
format:             # headers then prose / bullet lists / code-heavy
```

## What to avoid

- _List tones or styles that don't fit this project (e.g. no marketing language, no passive voice, no emoji in comments)_
