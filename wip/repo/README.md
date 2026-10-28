# Lesotho: law history in git

The law of Lesotho as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change to a provision; `tools/on.py` gives the text in force on any day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ls/`. Every version is a dated point-in-time version published by [LesLII](https://lesotholii.org) on the Laws.Africa Peachjam platform.

**What is in it now**

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `money-laundering/` | [Money Laundering and Proceeds of Crime Act, 2008](https://lesotholii.org/akn/ls/act/2008/4) | 5 | 2009-04-01 to 2015-09-25 |
| `anti-trafficking/` | [Anti-Trafficking in Persons Act, 2011](https://lesotholii.org/akn/ls/act/2011/1) | 2 | 2011-01-11 to 2021-01-14 |

**Money Laundering and Proceeds of Crime Act, 2008**

| In force | Author |
| --- | --- |
| 2009-04-01 | Act 4 of 2008 (as enacted) |
| 2011-06-10 | Act 4 of 2008, Legal Notice 68 of 2011 |
| 2012-07-01 | Act 4 of 2008, Legal Notice 82 of 2012 |
| 2013-03-28 | Legal Notice 30 of 2013 |
| 2015-09-25 | Legal Notice 112 of 2015 |

**Anti-Trafficking in Persons Act, 2011**

| In force | Author |
| --- | --- |
| 2011-01-11 | Act 1 of 2011 (as enacted) |
| 2021-01-14 | Act 1 of 2021 |

Each folder's `README.md` lists every provision, how often it changed and when.

## A lawyer's questions as git commands

| Question | Command |
| --- | --- |
| What did sec-014 say on 2009-04-01? | `python tools/on.py 2009-04-01 money-laundering sec-014` |
| The same, with raw git (bash) | `git show $(git rev-list -1 --before="2009-04-01T23:59:59Z" main -- money-laundering/sec-014.md):money-laundering/sec-014.md` |
| The same, in PowerShell | `$r = git rev-list -1 --before="2009-04-01T23:59:59Z" main -- money-laundering/sec-014.md; git show "$($r):money-laundering/sec-014.md"` |
| Which law wrote each line? | `git blame money-laundering/sec-014.md` |
| Every change, word by word | `git log -p --word-diff money-laundering/sec-014.md` |
| Every law in the record, in order | `git log --reverse --format="%ad %an" --date=short main` |
| Everything one law changed | `git show law/<key>` (tags `law/<key>` mark each law's commit) |
| The whole act on a date | `python tools/on.py 2009-04-01 money-laundering` |
| Which law gave a provision its wording on a date | `python tools/on.py --law 2009-04-01 money-laundering sec-014` |

After a rebuild, refresh tags with `git fetch --force --tags`: a plain fetch keeps stale tags.

## Dates

- Each commit is dated at **noon, Africa/Maseru, on the day the change took effect**. The day is also in the `In-force:` trailer, which the tools read; enactment (assent) and Gazette publication dates are trailers too, where LesLII states them.
- **The day is LesLII's.** Each version is a Laws.Africa expression, and its date is the day the amendment it takes in came into force, as the amendment list says ("[Amended by <Act> on <date>]"). For a consolidation (a revised edition) it is the date the edition is as at. An act's original expression is dated by its Gazette publication; where LesLII gives a later commencement date ("Commenced on ..."), the first version is dated by that instead (see REPRODUCE.md, decisions).
- `--before="YYYY-MM-DD"` alone uses your clock's time of day, so a law that took effect that day may be missed before noon. Use `T23:59:59Z` as above, or the tool.

## How it is checked

- Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`. Results are in `REPRODUCE.md`.
- **Against LesLII today:** the last version of each act is LesLII's current expression, as named by its own legislation listing on the retrieval day, and is the text of that expression page.
- **Every version is its own dated expression**: each was parsed from an archived copy of exactly that expression's page, whose sha256 is recorded with the version.
- The repository is rebuilt from the same data a second time and must give identical hashes.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist, so `git blame` and `git log --author` name laws. The committer is always Lexifina.

- **Credits come only from LesLII's own notes.** A version whose History entry names one amending Act is credited to it. Where one version takes in several Acts, or a revised edition, a provision is credited to an Act only if LesLII's editorial note in that provision names it ("[section 5 amended by section 2 of Act 3 of 2020]"); the rest are committed by the publisher and labelled "unexplained", and the commit message names the Acts the version takes in.
- **The first commit** is the act as enacted where that is the oldest version; otherwise it is the oldest version available (a consolidation), credited to the publisher.
- Blame credits whole lines (one paragraph per line). Use `git log -p --word-diff` to see exactly which words each change made.

## What it does not show

- **Only the versions LesLII publishes.** Changes before its oldest version are not separate commits.
- **Editorial notes.** LesLII's bracketed notes ("[Act No. 18 of 1996]", "[section 5 amended by ...]") are left out of the text and used only for credits, except where a provision has no other text (repealed or spent), where the note is what LesLII prints and is kept.
- **Headings above the provision** (Part, Chapter, Division) are left out; each file starts with its own number and heading. Footnotes are kept at the end of the file.
- **Amendments not yet applied.** Where the LII lists an amendment as not yet applied to its consolidated text, it is not in this history; REPRODUCE.md lists each one.
- **No OCR.** Acts the LII shows only as scanned PDFs are not included.

## How it is built


## Sources

| Source | What it gives | Used for |
| --- | --- | --- |
| [LesLII](https://lesotholii.org) | Dated point-in-time versions (expressions) of each act, its History and amendment list, and per-provision editorial notes; its listing page names the current version | The text and dates of every version |
| [Internet Archive](https://web.archive.org/) | Archived copies of those expression pages | Reading them |

## Licence

See [LICENSE](LICENSE). Source: LesLII (https://lesotholii.org), licensed under the Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0).

LesLII's terms: CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy). Lexifina's arrangement, messages, tables and tools are CC0.

This repository is not legal advice. Lesotho's laws are published in English, so there is no separate summary in another language.
