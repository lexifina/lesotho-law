# How this repository was made (Lesotho)

This file is written by the build on 2026-10-28, the day the source data was retrieved. Everything below is enough to rebuild this repository hash for hash.

## Sources

| Source | Address | Retrieved | Requests | Licence |
| --- | --- | --- | ---: | --- |
| LesLII, the Lesotho Legal Information Institute (supported by the Judiciary of Lesotho, the Law Office and the Law Society; on the Laws.Africa Peachjam platform) | <https://lesotholii.org> | 2026-10-28 | 52 | CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy) |
| Internet Archive Wayback Machine | <https://web.archive.org> | 2026-10-28 | None | Archived copies of LesLII pages; the content licence is LesLII's |
| LesLII, earlier website (lesotholii.org/ls/..., until 2023), through the Internet Archive | <https://lesotholii.org/ls/legislation/num-act/1993/1> | 2026-10-28 | 1 | LesLII content, CC BY-NC 4.0 crediting LesLII as the source (https://lesotholii.org/terms-of-use/) |

Every response is cached by the sha256 of its URL, and the table above lists every source with its retrieval date. Lexifina keeps its fetch scripts privately; `tools/parse.py` reads only the cache and writes `corpus.json`, so the same cache always gives the same corpus.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `money-laundering` | Money Laundering and Proceeds of Crime Act, 2008 | 5 | 2009-04-01 to 2015-09-25 |
| `anti-trafficking` | Anti-Trafficking in Persons Act, 2011 | 2 | 2011-01-11 to 2021-01-14 |
| `constitution` | Constitution of Lesotho | 1 | 1993-04-02 to 1993-04-02 |

The build made 8 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 5 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-28.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 8 laws in the record.
- 16 tags.

## Dates

Each commit is dated at noon (Africa/Maseru) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: every version is dated by LesLII's own expression date, or by the commencement date LesLII states for the act as published. No date is computed from a default rule. https://lesotholii.org/legislation/

## Commands, in order

```sh
# fill the cache from the sources listed above (network; Lexifina's fetch scripts are kept privately)
python -X utf8 tools/parse.py                  # cache -> corpus.json (no network)
python -X utf8 tools/build.py <folder> --repo <empty folder> --docs-date 2026-10-28
python -X utf8 tools/check_repo.py <repo> --corpus <folder>/corpus.json --write
python -X utf8 tools/build.py <folder> --repo <another empty folder> --docs-date 2026-10-28 --compare <repo>
```

In the main Lexifina repository these files live as follows:
- `fetch.py`, `parse.py` and `repo/`: in `scripts/lesotho-law/`.
- `build.py`, `check_repo.py` (`check.py` there) and `on.py`: in `scripts/gitlaw_common/`, with the corpus format in `SCHEMA.md`.

## Exact inputs

- `corpus.json` sha256 `534e2fc19bd101211a4e090ac7a498bfce863e66639cd1a71d1116b0c85785a5` (499356 bytes)
- Script blob hashes (`git hash-object`):

| Script | Blob |
| --- | --- |
| build.py | `2bfc4ac9df193a7be844556d7f69cdb9d93ec3f2` |
| check.py | `cd346c7ff9996d450240e3bab52bcae03b2bc865` |
| on.py | `644a6c0857fbcc72562032b58d57aa113fee0641` |
| fetch.py | `504e11c9cbe811780167a75549859e3290d429ac` |
| parse.py | `14d09fc3621c162f127be576ed4dc2ae7a5ae8f3` |

- Tools:
  - Python 3.14.0
  - git version 2.52.0.windows.1
  - curl 8.21.0 (Windows) libcurl/8.21.0 Schannel zlib/1.3.2 WinIDN WinLDAP

## Checks

7 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 8 history commits and 16 tags (history tip `eb6e5985483be1b50316c01290252445fb2eb94a`).

These results are from the check run on the build before this one, from the same corpus.

## Decisions made by hand

- Acts were chosen by what the archives hold. Of the 142 LesLII act works with an archived expression page, only two have more than one archived expression: the Money Laundering and Proceeds of Crime Act 2008 (3 expressions: 2008-04-10, 2013-03-28, 2015-09-25) and the Anti-Trafficking in Persons Act 2011 (2 expressions: 2011-01-11, 2021-01-14). Each of their versions is read from its own dated expression.
- The Constitution of Lesotho 1993 has no archived LesLII (Peachjam) expression page: the Internet Archive holds no /akn/ls/act/1993/... page for it. Its 1993 text as made is read from the archived page of LesLII's earlier website (lesotholii.org/ls/legislation/num-act/1993/1), in corpus.d/10-constitution.json; see that part's own decisions.
- Licence and terms: LesLII licenses primary and secondary law content CC BY-NC 4.0, crediting LesLII as the source; its terms (section 4) prohibit scraping and bulk downloading from its website, and its robots.txt sends Content-Signal ai-train=no, ai-input=no and Crawl-delay 5. No LesLII page was fetched from lesotholii.org: every page, including the terms and robots.txt, is read from an archived copy (Internet Archive, or Common Crawl), for the configured acts only. The user decided on 2026-10-28 that reading these archived copies is acceptable (relayed by the coordinator: "scraping wayback is fair game, dont overdo it"). The repository stays private; CC BY-NC allows only non-commercial use. No legal text was given to a model.
- Version dates are LesLII's expression dates. Laws.Africa's terminology guide (https://docs.laws.africa/getting-started/terminology-guide) says "Amendments to Principal works come into force on the Commencement date of the Amending work" and that the first point in time is "the work as originally published"; so an amendment's expression is dated by its commencement (in force), and an act's original expression by its publication, which is replaced by the commencement date the page states.
- Credits: a version whose History names exactly one amending law (and no consolidation) between it and the previous version is credited to that law for every provision that changed. Otherwise a provision is credited only to laws that LesLII's editorial note inside that provision links to; the rest are unexplained (publisher).
- Editorial notes (akn-remark) are left out of the text and used only as credit evidence, except where a provision has no other text (repealed or spent), where the note is the provision's whole printed content.
- Part, Chapter and Division headings are left out; each provision file starts with its own number and heading. Every other text of each version is in a provision file: parse.py checks this per version (verification.json, fidelity).
- MLPCA 2008: the LII's page says: This is the latest available version of this Act. There are outstanding amendments that have not yet been applied. See the History tab for more information.
- MLPCA 2008: LesLII's page says "There are multiple commencements" and prints a commencements table; the act's start is built from it (lii.py): Part I (section 1–10); Part II, section 11–13; Part III, section 16–17, section 19–36; Part IV (section 37–86); Part V (section 87–110); Part VI (section 111–113) from 2009-04-01 (Legal Notice 51 of 2009); Part II, section 14–15 from 2011-06-10 (Legal Notice 68 of 2011); Part III, section 18 from 2012-07-01 (Legal Notice 82 of 2012). The long title, the preamble and the schedules whose headings tie them to a section are dated with that section; the text of every provision is the 2008-04-10 expression's, the Act as published.
- MLPCA 2008: not applied, because no archived copy gives the consolidated text after them: Amended by Money Laundering and Proceeds of Crime (Amendment) Act, 2016 (dated 2017-02-06 by LesLII); Amended by Money Laundering and Proceeds of Crime Act 2008 (Amendment of Schedule) Notice, 2017 (dated 2017-06-30 by LesLII). LesLII's own latest version (2015-09-25) does not apply them either; so from the earliest of those dates the text here is not the law in force.
- Constitution: LesLII's current site has no archived expression page of the Constitution, so its text is read from the archived page of LesLII's earlier website (https://lesotholii.org/ls/legislation/num-act/1993/1, Internet Archive capture 20230326214103). That page's editorial note reads: "Ed Note: This is the official text. The Revised Draft of a Constitution for Lesotho was published as Government Notice No. 12 of 1993 on 5 February 1993. That revised draft was then amended by Government Notice No. 211 of 1993, published on 27 March 1993. By virtue of section 5 of the Lesotho Constitution (Commencement) Order, 1993 (Order No. 5 of 1993) as amended by the Lesotho Constitution (Commencement) (Amendment) Order, 1993 (Order No. 16 of 1993), the draft constitution came into operation as the Constitution of Lesotho on 2 April 1993, following the appointment on 1 April 1993 of a Prime Minister Designate."
- Constitution: the version is dated 2 April 1993, the day that editorial note gives for the Constitution coming into operation; the same page's "Date of commencement" field says 01 April 1993, the day the note gives for the appointment of the Prime Minister Designate that triggered commencement. The law's Published date is 5 February 1993, when the Revised Draft was published as Government Notice No. 12 of 1993 (it was amended by Government Notice No. 211 of 1993 on 27 March 1993).
- Constitution: the page prints the Constitution as it came into operation, with no amendment applied (section 56 reads "The National Assembly shall consist of eighty members"). The amending Acts are not applied, because no archived copy gives a dated consolidated text after them and no text is reconstructed: Second Amendment of the Constitution Act, 1997; Fourth Amendment to the Constitution Act, 2001; Fifth Amendment to the Constitution Act, 2004; Sixth Amendment to the Constitution Act, 2011; Seventh Amendment of the Constitution Act, 2011 (the five the page lists), and the others the page does not list. The repository's history of the Constitution therefore stops at 2 April 1993, and this part (corpus.d/10-constitution.json) is not marked verified, so it builds only to the preview branch.
- Constitution: Chapter and Part headings are left out; 24 were dropped. All 1157 paragraphs of the page are in the 166 section files and 3 schedule files (checked by constitution.py). The source's own typing errors are kept as printed.

## What AI did and did not do

The fetch, parse and check scripts were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above, through code that anyone can rerun.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (Claude Opus 5.5, claude-opus-5-5) wrote the configuration and the Constitution parser and chose the acts. No model wrote, summarised or transformed legal text: parse.py is deterministic code.
