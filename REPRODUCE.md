# How this repository was made (Lesotho)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| LesLII, the Lesotho Legal Information Institute (supported by the Judiciary of Lesotho, the Law Office and the Law Society; on the Laws.Africa Peachjam platform) | <https://lesotholii.org> | 2026-10-28 | CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy) |
| Internet Archive Wayback Machine | <https://web.archive.org> | 2026-10-28 | Archived copies of LesLII pages; the content licence is LesLII's |
| LesLII, the Lesotho Legal Information Institute (supported by the Judiciary of Lesotho, the Law Office and the Law Society; on the Laws.Africa Peachjam platform) (Penal Code) | <https://lesotholii.org> | 2026-10-30 | CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy) |
| Internet Archive Wayback Machine (Penal Code) | <https://web.archive.org> | 2026-10-30 | Archived copies of LesLII pages; the content licence is LesLII's |
|  | <https://commoncrawl.org> | 2026-10-30 | the content's licence is LesLII's |
| LesLII, the Lesotho Legal Information Institute (supported by the Judiciary of Lesotho, the Law Office and the Law Society; on the Laws.Africa Peachjam platform) (Children's Protection and Welfare Act) | <https://lesotholii.org> | 2026-10-30 | CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy) |
| Internet Archive Wayback Machine (Children's Protection and Welfare Act) | <https://web.archive.org> | 2026-10-30 | Archived copies of LesLII pages; the content licence is LesLII's |
|  | <https://commoncrawl.org> | 2026-10-30 | the content's licence is LesLII's |
| LesLII, the Lesotho Legal Information Institute (supported by the Judiciary of Lesotho, the Law Office and the Law Society; on the Laws.Africa Peachjam platform) (Arbitration Act) | <https://lesotholii.org> | 2026-10-30 | CC BY-NC 4.0, crediting LesLII as the source (https://lesotholii.org/terms-of-use/, read from the Internet Archive's copy) |
| Internet Archive Wayback Machine (Arbitration Act) | <https://web.archive.org> | 2026-10-30 | Archived copies of LesLII pages; the content licence is LesLII's |
|  | <https://commoncrawl.org> | 2026-10-30 | the content's licence is LesLII's |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `money-laundering` | Money Laundering and Proceeds of Crime Act, 2008 | 5 | 2009-04-01 to 2015-09-25 |
| `anti-trafficking` | Anti-Trafficking in Persons Act, 2011 | 2 | 2011-01-11 to 2021-01-14 |
| `penal-code` | Penal Code Act, 2012 | 1 | 2012-03-09 to 2012-03-09 |
| `childrens-protection-and-welfare` | Children's Protection and Welfare Act, 2011 | 1 | 2011-03-31 to 2011-03-31 |
| `arbitration-act` | Arbitration Act, 1980 | 1 | 1981-10-01 to 1981-10-01 |

The build made 10 commits:

| Commits | Kind |
| ---: | --- |
| 5 | first version of an act |
| 5 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 10 laws in the record.
- 20 tags.

## Dates

Each commit is dated at noon (Africa/Maseru) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: every version is dated by LesLII's own expression date, or by the commencement date LesLII states for the act as published. No date is computed from a default rule. https://lesotholii.org/legislation/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `89f66a3d49927fe513ceee5c0a5777a4e388234cb18b990a1f79adc7721e5033` (696058 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

10 versions of 5 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Acts were chosen by what the archives hold. Of the 142 LesLII act works with an archived expression page, only two have more than one archived expression: the Money Laundering and Proceeds of Crime Act 2008 (3 expressions: 2008-04-10, 2013-03-28, 2015-09-25) and the Anti-Trafficking in Persons Act 2011 (2 expressions: 2011-01-11, 2021-01-14). Each of their versions is read from its own dated expression.
- The Constitution of Lesotho 1993 has no archived LesLII (Peachjam) expression page: the Internet Archive holds no /akn/ls/act/1993/... page for it. Its 1993 text as made is read from the archived page of LesLII's earlier website (lesotholii.org/ls/legislation/num-act/1993/1), in a separate part of the corpus; see that part's own decisions.
- Licence: LesLII licenses primary and secondary law content CC BY-NC 4.0, crediting LesLII as the source; CC BY-NC allows only non-commercial use. Every LesLII page is read from an archived copy, for the configured acts only. No legal text was given to a model.
- Version dates are LesLII's expression dates. Laws.Africa's terminology guide (https://docs.laws.africa/getting-started/terminology-guide) says "Amendments to Principal works come into force on the Commencement date of the Amending work" and that the first point in time is "the work as originally published"; so an amendment's expression is dated by its commencement (in force), and an act's original expression by its publication, which is replaced by the commencement date the page states.
- Credits: a version whose History names exactly one amending law (and no consolidation) between it and the previous version is credited to that law for every provision that changed. Otherwise a provision is credited only to laws that LesLII's editorial note inside that provision links to; the rest are unexplained (publisher).
- Editorial notes (akn-remark) are left out of the text and used only as credit evidence, except where a provision has no other text (repealed or spent), where the note is the provision's whole printed content.
- Part, Chapter and Division headings are left out; each provision file starts with its own number and heading. Every other text of each version is in a provision file: this is checked per version (verification.json, fidelity).
- MLPCA 2008: the LII's page says: This is the latest available version of this Act. There are outstanding amendments that have not yet been applied. See the History tab for more information.
- MLPCA 2008: LesLII's page says "There are multiple commencements" and prints a commencements table; the act's start is built from it: Part I (section 1–10); Part II, section 11–13; Part III, section 16–17, section 19–36; Part IV (section 37–86); Part V (section 87–110); Part VI (section 111–113) from 2009-04-01 (Legal Notice 51 of 2009); Part II, section 14–15 from 2011-06-10 (Legal Notice 68 of 2011); Part III, section 18 from 2012-07-01 (Legal Notice 82 of 2012). The long title, the preamble and the schedules whose headings tie them to a section are dated with that section; the text of every provision is the 2008-04-10 expression's, the Act as published.
- MLPCA 2008: not applied, because no archived copy gives the consolidated text after them: Amended by Money Laundering and Proceeds of Crime (Amendment) Act, 2016 (dated 2017-02-06 by LesLII); Amended by Money Laundering and Proceeds of Crime Act 2008 (Amendment of Schedule) Notice, 2017 (dated 2017-06-30 by LesLII). LesLII's own latest version (2015-09-25) does not apply them either; so from the earliest of those dates the text here is not the law in force.
- Penal Code: in force 2012-03-09, the day of its publication in Government Gazette 30 (LesLII coverpage), under its s. 1: it "shall come into operation on the date of its publication in the Gazette". The Act cites itself as the Penal Code Act, 2010 (s. 1, as printed); LesLII files it as Act 6 of 2012.
- Penal Code: LesLII's History lists no amendment after commencement (archived copy of 2026-01-12); the one version is the Act as published.
- Children's Protection and Welfare Act: in force 2011-03-31, the day of its publication in Government Gazette 40, the commencement LesLII states. LesLII lists no amendment.
- Arbitration Act: dated 1981-10-01, the commencement LesLII's coverpage states ("Commenced on 1 October 1981"); LesLII links the commencement to the Pension Scheme (Corporate Bodies) Act, 1979, which is how its page reads, not a sourced commencement instrument. LesLII lists no amendment.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (Claude Opus 5.5, claude-opus-5-5) wrote the configuration and the Constitution parser and chose the acts. No model wrote, summarised or transformed legal text: the text is parsed by deterministic code.
- Penal Code: none at data-build time; units are parsed by code from the published page.
- Children's Protection and Welfare Act: none at data-build time; units are parsed by code from the published page.
- Arbitration Act: none at data-build time; units are parsed by code from the published page.
