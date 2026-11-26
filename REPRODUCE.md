# How this repository was made (Lesotho)

This file is written by the build on 2026-11-05, the day the source data was retrieved.

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
| Lesotho Government Gazette 21 (Administration of Estates and Inheritance Act) | <https://web.archive.org/web/20240805134300id_/https://lesotholii.org/akn/ls/act/2024/2/eng@2024-04-02/source.pdf> | 2026-11-05 | LesLII: Creative Commons Attribution-NonCommercial 4.0 International; credit LesLII (https://lesotholii.org). |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `money-laundering` | Money Laundering and Proceeds of Crime Act, 2008 | 5 | 2009-04-01 to 2015-09-25 |
| `anti-trafficking` | Anti-Trafficking in Persons Act, 2011 | 2 | 2011-01-11 to 2021-01-14 |
| `penal-code` | Penal Code Act, 2012 | 1 | 2012-03-09 to 2012-03-09 |
| `childrens-protection-and-welfare` | Children's Protection and Welfare Act, 2011 | 1 | 2011-03-31 to 2011-03-31 |
| `arbitration-act` | Arbitration Act, 1980 | 1 | 1981-10-01 to 1981-10-01 |
| `administration-of-estates-and-inheritance` | Administration of Estates and Inheritance Act, 2024 | 1 | 2024-04-02 to 2024-04-02 |

The build made 11 commits:

| Commits | Kind |
| ---: | --- |
| 6 | first version of an act |
| 5 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-05.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 10 laws in the record.
- 21 tags.

## Dates

Each commit is dated at noon (Africa/Maseru) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: every version is dated by LesLII's own expression date, or by the commencement date LesLII states for the act as published. No date is computed from a default rule. https://lesotholii.org/legislation/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `d1e05dd787292e385e51a93629ab3e55420c2692bb72cdc72bcadbe80b3e1ec3` (824274 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `3024ff164c261807dfc4d5b7b1b4a2cde4357da1`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

11 versions of 6 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

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
- Administration of Estates and Inheritance Act: in force 2024-04-02 under section 1, which makes commencement the date of publication in the Gazette; the Gazette cover and LesLII history both give 2 April 2024.
- Administration of Estates and Inheritance Act: one full-text unit preserves the official native PDF text, its long title, enacting formula, 117 sections, five textual schedules and forms. Printed page numbers and excess typesetting spaces are removed; no legal words are corrected.
- Administration of Estates and Inheritance Act: oldest version available, as published in 2024; no later consolidated version is asserted. There are no normative raster images on the act pages; the Gazette cover contains one decorative coat of arms.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (Claude Opus 5.5, claude-opus-5-5) wrote the configuration and the Constitution parser and chose the acts. No model wrote, summarised or transformed legal text: the text is parsed by deterministic code.
- Penal Code: none at data-build time; units are parsed by code from the published page.
- Children's Protection and Welfare Act: none at data-build time; units are parsed by code from the published page.
- Arbitration Act: none at data-build time; units are parsed by code from the published page.
- GPT-6 wrote extraction and validation code and selected the source boundaries. No model wrote or corrected legal text; native PDF text is extracted by code.

## Laws added from PDF copies (2026-11-26)

LesLII and the other AfricanLII sites now answer with a challenge, so 47 laws were added from copies that
answer without one: WIPO Lex, FAOLEX (through ECOLEX's listing of Lesotho legislation) and the Government of Lesotho
(gov.ls). Each law is one file, `<folder>/full-text.md`, read from the PDF's own text layer (no OCR by Lexifina; where
the PDF is a Gazette scan the layer is the publisher's OCR and keeps its errors). Each commit carries `Source-status:`,
`Text-source:`, `Source-sha256:` (of the PDF) and `In-force-basis:`. The Constitution and its two commencement Orders
were first read from WIPO Lex and then corrected (`Kind: correction`) to the Government of Lesotho's copy of the same
version. The scripts are in `lesotho-acq/tools` (`ecolex.py`, `faolex_dl.py`, `wipo_dl.py`, `extract.py`,
`build_items.py`, `addlaw.py`, `correct.py`); they were written by Claude Code (Claude Opus 5.5). No model wrote or
corrected legal text.

Dates: the commencement the text or the source states; else, for a law that commences on publication, its Gazette day;
else its Gazette day, as this repository dates an act whose commencement is not stated (the trailer says so).

Held back, with no reliable date or text: the Companies Act 2011 and other WIPO Lex records whose PDFs carry no text
layer; the Industrial Property Order 1989 as amended to 1997 and the Constitution as amended (consolidations with no
date for the version); the First (1996) and Third (1998) Amendments to the Constitution (no Gazette day in the copy);
pre-1966 proclamations printed in revised editions; and FAOLEX instruments with neither a commencement nor a Gazette
day (among them the Local Government Act 1997, the Mines and Minerals Act 2005, the Prevention of Corruption and
Economic Offences Act 1999 and the Stock Theft Act 2000). The gov.ls Gazette PDFs of 2018 to 2022 are scans without a
text layer.

| Folder | Title | In force | Source | Basis |
| --- | --- | --- | --- | --- |
| `land-act-2010` | Land Act 2010 | 2010-06-14 | FAOLEX, via ECOLEX | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Government Gazette Extraordinary Vol. LV No. 42 of 14 June 2010, as the FAOLEX copy states), as this repository dates an act whose commencement is not stated |
| `water-resources-act-1978` | Water Resources Act 1978 | 1979-04-01 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 1-4-79 (commencement notice LN 18 of 1979) |
| `tourism-amendment-act-2006` | Tourism (Amendment) Act, 2006 | 2006-02-17 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Extraordinary Vol. LI of Friday 17 February 2006); dated by that Gazette day |
| `land-husbandry-act-1969` | Land Husbandry Act 1969 | 1969-05-16 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 16 May 1969 (assent 23 April 1969) |
| `land-husbandry-amendment-act-1974` | Land Husbandry (Amendment) Act 1974 | 1975-02-28 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 28 February 1975 (assent 14 January 1975) |
| `lesotho-highlands-development-authority-order-1986` | Lesotho Highlands Development Authority Order, 1986 | 1986-10-24 | FAOLEX, via ECOLEX | its commencement section: in operation on 24 October 1986 (printed Date of Commencement 24-10-86) |
| `weeds-eradication-act-1969` | Weeds Eradication Act 1969 | 1969-05-16 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 16 May 1969 (assent 23 April 1969) |
| `environment-act-2008` | Environment Act 2008 | 2008-12-05 | FAOLEX, via ECOLEX | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Supplement No. 1 to Gazette No. 80 of 5 December 2008), as this repository dates an act whose commencement is not stated |
| `water-act-2008` | Water Act, 2008 | 2008-12-30 | FAOLEX, via ECOLEX | section 1: on publication in the Gazette; the Laws.Africa copy gives the Act as published on 30 December 2008 |
| `co-operative-societies-act-2000` | Co-operative Societies Act 2000 | 2000-09-15 | FAOLEX, via ECOLEX | on publication in the Gazette (Supplement No. 1 to Gazette No. 78 of 15 September 2000); dated by that Gazette day |
| `deeds-registry-act-1967` | Deeds Registry Act 1967 | 1967-05-15 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 15 May 1967 (commencement notice GN 51 of 1967; assent 3 May 1967) |
| `agricultural-marketing-act-1967` | Agricultural Marketing Act 1967 | 1967-07-14 | FAOLEX, via ECOLEX | date of commencement printed under the title in the published text: 14 July 1967 (assent 6 July 1967) |
| `agricultural-marketing-egg-control-regulations-1969` | Agricultural Marketing (Egg Control) Regulations 1969 | 1969-08-29 | FAOLEX, via ECOLEX | printed under the notice number: "Commenced 29 August, 1969" |
| `agricultural-marketing-egg-control-amendment-regulations-2014` | Agricultural Marketing (Egg Control) (Amendment) Regulations, 2014 | 2014-02-21 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Vol. 59 No. 10 of Friday 21 February 2014); dated by that Gazette day |
| `lewa-resolution-of-complaints-water-sewerage-rules-2013` | Lesotho Electricity and Water Authority (Resolution of Complaints for Water and Sewerage Services) Rules, 2013 | 2013-09-06 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Vol. 58 No. 47 of Friday 6 September 2013); dated by that Gazette day |
| `livestock-import-export-amendment-act-1984` | Importation and Exportation of Livestock and Livestock Products Proclamation (Amendment) Act 1984 | 1984-08-03 | FAOLEX, via ECOLEX | no commencement provision; dated by its Gazette day (Supplement No. 2 to Gazette No. 29 of 3 August 1984) |
| `agricultural-marketing-dairy-products-regulations-1992` | Agricultural Marketing (Distribution of Dairy Products) Regulations, 1992 | 1992-10-02 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Extraordinary Vol. XXXVII No. 115 of Monday 2 October 1992); dated by that Gazette day |
| `lesotho-electricity-authority-act-2002` | Lesotho Electricity Authority Act 2002 | 2002-06-20 | FAOLEX, via ECOLEX | commencement not legible in the copy; dated by its Gazette day (Government Gazette Extraordinary Vol. XLVII No. 70 of Thursday 20 June 2002), as this repository dates an act whose commencement is not stated |
| `lesotho-electricity-authority-amendment-act-2006` | Lesotho Electricity Authority (Amendment) Act 2006 | 2006-10-13 | FAOLEX, via ECOLEX | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Supplement No. 1 to Gazette No. 81 of 13 October 2006), as this repository dates an act whose commencement is not stated |
| `lesotho-electricity-authority-amendment-act-2011` | Lesotho Electricity Authority (Amendment) Act, 2011 | 2011-03-01 | FAOLEX, via ECOLEX | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Government Gazette Extraordinary Vol. LVI No. 24 of Tuesday 1 March 2011), as this repository dates an act whose commencement is not stated |
| `lea-application-for-licences-rules-2012` | Lesotho Electricity Authority (Application for Licences) Rules, 2012 | 2012-06-08 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Vol. 57 No. 60 of Friday 8 June 2012); dated by that Gazette day |
| `iodization-regulations-1999` | Lesotho Iodization Regulations, 1999 | 1999-03-10 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Extraordinary Vol. XLIV No. 16 of Wednesday 10 March 1999); dated by that Gazette day |
| `lewa-licence-fees-levies-water-sewerage-regulations-2013` | Lesotho Electricity and Water Authority (Licence Fees and Customer Levies for Water and Sewerage Services) Regulations, 2013 | 2013-09-27 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Vol. 58 No. 56 of Friday 27 September 2013); dated by that Gazette day |
| `disaster-management-act-1997` | Disaster Management Act 1997 | 1997-05-13 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Extraordinary Vol. XLII No. 26 of Tuesday 13 May 1997); dated by that Gazette day |
| `land-act-1979` | Land Act 1979 | 1979-12-14 | FAOLEX, via ECOLEX | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Supplement No. 1 to Gazette No. 41 of 14 December 1979), as this repository dates an act whose commencement is not stated |
| `land-regulations-1980` | Land Regulations 1980 | 1980-08-01 | FAOLEX, via ECOLEX | regulation 1: in operation on 1 August 1980 (published in Supplement No. 2 to Gazette No. 29 of 22 August 1980) |
| `lea-resolution-of-disputes-rules-2010` | Lesotho Electricity Authority (Resolution of Disputes) Rules, 2010 | 2010-03-12 | FAOLEX, via ECOLEX | on publication in the Gazette (Supplement No. 1 to Gazette No. 19 of 12 March 2010); dated by that Gazette day |
| `public-health-covid-19-regulations-2020` | Public Health (COVID-19) Regulations, 2020 | 2020-04-22 | FAOLEX, via ECOLEX | its commencement regulation: in operation on 22 April 2020 (Government Gazette Extraordinary Vol. 65 No. 34 of that day) |
| `agricultural-marketing-import-of-sugar-regulations-1989` | Agricultural Marketing (Import of Sugar) Regulations, 1989 | 1989-12-15 | FAOLEX, via ECOLEX | on publication in the Gazette (Supplement No. 3 to Gazette No. 71 of 15 December 1989); dated by that Gazette day |
| `forestry-act-1998` | Forestry Act 1998 | 1998-12-18 | FAOLEX, via ECOLEX | on publication in the Gazette (Supplement No. 1 to Gazette No. 91 of 18 December 1998); dated by that Gazette day |
| `food-grain-self-sufficiency-fund-regulations-1980` | Food Grain Self-Sufficiency Fund Regulations 1980 | 1980-12-19 | FAOLEX, via ECOLEX | no commencement date legible; dated by its Gazette day (Supplement No. 2 to Gazette No. 46 of 19 December 1980) |
| `water-resources-regulations-1980` | Water Resources Regulations 1980 | 1980-09-05 | FAOLEX, via ECOLEX | no commencement date legible; dated by its Gazette day (Supplement No. 2 to Gazette No. 31 of 5 September 1980) |
| `land-agricultural-lease-regulations-1992` | Land (Agricultural Lease) Regulations, 1992 | 1992-05-29 | FAOLEX, via ECOLEX | no commencement date legible; dated by its Gazette day (Supplement No. 1 to Gazette No. 55 of 29 May 1992) |
| `land-amendment-order-1986` | Land (Amendment) Order, 1986 | 1986-01-20 | FAOLEX, via ECOLEX | section 1: in operation on 20 January 1986 (published in Supplement No. 3 to Gazette No. 12 of 6 March 1987) |
| `land-amendment-order-1992` | Land (Amendment) Order, 1992 | 1992-03-10 | FAOLEX, via ECOLEX | commencement not legible in the copy; dated by its Gazette day (Government Gazette Extraordinary Vol. XXXVII No. 25 of Tuesday 10 March 1992) |
| `land-amendment-regulations-1993` | Land (Amendment) Regulations, 1993 | 1993-04-02 | FAOLEX, via ECOLEX | on publication in the Gazette (Government Gazette Extraordinary Vol. XXXVIII No. 54 of Friday 2 April 1993); dated by that Gazette day |
| `tourism-act-2002` | Tourism Act 2002 | 2002-02-26 | FAOLEX, via ECOLEX | WIPO Lex and FAOLEX give entry into force 26 February 2002, the day of Government Gazette Extraordinary Vol. XLVII No. 18 |
| `labour-code-order-1992` | Labour Code Order, 1992 | 1993-04-01 | WIPO Lex | WIPO Lex: entry into force 1 April 1993; section 1 brings the Code into operation on days the Minister appoints by notice |
| `constitution` | The Constitution of Lesotho | 1993-04-02 | WIPO Lex | in operation on 2 April 1993, the day after the appointment of a Prime Minister Designate, under section 5 of Order No. 5 of 1993 as amended by Order No. 16 of 1993 (as the text's own note and WIPO Lex state) |
| `lesotho-constitution-commencement-order-1993` | Lesotho Constitution (Commencement) Order, 1993 | 1993-03-16 | WIPO Lex | on publication in the Gazette (Government Gazette Extraordinary Vol. XXXVIII No. 35 of Tuesday 16 March 1993); dated by that Gazette day |
| `lesotho-constitution-commencement-amendment-order-1993` | Lesotho Constitution (Commencement) (Amendment) Order, 1993 | 1993-03-27 | WIPO Lex | on publication in the Gazette (Government Gazette Extraordinary Vol. XXXVIII No. 43 of Saturday 27 March 1993); dated by that Gazette day |
| `historical-monuments-relics-fauna-flora-act-1967` | Historical Monuments, Relics, Fauna and Flora Act, 1967 | 1967-12-22 | WIPO Lex | date of commencement printed under the title in the published text: 22 December 1967 (assent 13 December 1967); WIPO Lex gives the same entry into force |
| `lesotho-telecommunications-authority-act-2000` | Lesotho Telecommunications Authority Act 2000 | 2000-06-09 | WIPO Lex | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Government Gazette Extraordinary Vol. XLV No. 42 of Friday 9 June 2000), as this repository dates an act whose commencement is not stated |
| `lesotho-telecommunications-authority-regulations-2001` | Lesotho Telecommunications Authority Regulations 2001 | 2001-03-27 | WIPO Lex | the instrument commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Government Gazette Extraordinary Vol. XLVI No. 28 of Tuesday 27 March 2001), as this repository dates an act whose commencement is not stated |
| `lesotho-telecommunications-authority-amendment-act-2001` | Lesotho Telecommunications Authority (Amendment) Act 2001 | 2001-05-30 | WIPO Lex | the Act commences on a day the Minister appoints by notice, which no source here gives; dated by its Gazette day (Government Gazette Extraordinary Vol. XLVI No. 44 of Wednesday 30 May 2001), as this repository dates an act whose commencement is not stated |
| `lesotho-telecommunications-authority-broadcasting-rules-2004` | Lesotho Telecommunications Authority (Broadcasting) Rules 2004 | 2004-04-14 | WIPO Lex | on publication in the Gazette (Government Gazette Extraordinary Vol. XLIX No. 38 of Wednesday 14 April 2004); dated by that Gazette day |
| `lesotho-telecommunications-authority-amendment-act-2006` | Lesotho Telecommunications Authority (Amendment) Act, 2006 | 2006-07-28 | WIPO Lex | on publication in the Gazette (Supplement No. 1 to Gazette No. 41 of 28 July 2006); dated by that Gazette day |
