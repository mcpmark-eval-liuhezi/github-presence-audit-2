# GitHub Presence Audit — HeziLiu

All figures below were pulled **live from the GitHub API for account `HeziLiu`** during this audit run. Nothing is from memory or guesswork.

## 1. Profile summary

| Field | Live value |
| --- | --- |
| Login | `HeziLiu` |
| Display name | Hezi Liu |
| Account ID | 28861483 |
| Public repositories | 4 |
| Public gists | 0 |
| Followers | 5 |
| Following | 5 |

Profile: https://github.com/HeziLiu — company `BUPT/GZU`, location `Beijing/Guiyang`, bio "treat me like a tree", account created 2017-05-22.

## 2. Repository inventory (4 public repositories)

### Forks — flagged, not original work

| Repository | Fork details |
| --- | --- |
| [CodingInterviewChinese2](https://github.com/HeziLiu/CodingInterviewChinese2) | Fork (《剑指Offer》第二版源代码). C++, default branch `master`, issues disabled, license "Other / NOASSERTION" (inherited upstream), 0 stars / 0 forks of this copy. |
| [awesome-chatgpt-prompts-zh](https://github.com/HeziLiu/awesome-chatgpt-prompts-zh) | Fork (ChatGPT 中文调教指南). Default branch `main`, MIT license inherited upstream, issues disabled. |

### Original (non-fork) repositories — deep dive

#### [Little-rookie](https://github.com/HeziLiu/Little-rookie) — "Undergraduate coursework"

| Check | Result |
| --- | --- |
| Default branch | `master` |
| Primary language | Java |
| Open issues | 0 |
| Open pull requests | 0 |
| README | **Present** (`README.md` lists 14 coursework areas: algorithms, Linux, compilers, architecture, graphics, data mining, data structures, databases, AI intro, mobile dev, OS, MCU interfaces, software engineering, web programming) |
| LICENSE | **Absent** (404) |
| Latest release | **None** (no releases published) |
| GitHub Actions | **No workflow files at all → zero workflow runs exist** (nothing to report a conclusion or error log for) |
| Notes | Only repo with a package manifest: Maven `pom.xml` (artifact `testServlet`, version `1.0-SNAPSHOT`). Last pushed 2019-06-02. |

#### [Big-Buzzard](https://github.com/HeziLiu/Big-Buzzard) — "For future...."

| Check | Result |
| --- | --- |
| Default branch | `master` |
| Primary language | **None detected** — repo contains only `.gitattributes` and an empty folder named `Big-Buzzard` |
| Open issues | 0 |
| Open pull requests | 0 |
| README | **Absent** (404) |
| LICENSE | **Absent** (404) |
| Latest release | **None** |
| GitHub Actions | **No workflow files at all → zero workflow runs exist** |
| Notes | Effectively an empty placeholder repo (1 external fork exists of it). |

### CI result for the account

**None of the four public repositories contains any GitHub Actions workflow**, so there are **no workflow runs at all** — no latest run conclusion, and no failed job logs to quote. Stated plainly rather than glossed over.

## 3. Security section

**Ecosystem determination:** across the two original repositories, the only package manifest anywhere is `Little-rookie/pom.xml` (Maven). No `requirements.txt`, `package.json`, or `build.gradle` exists in any repo. → **Maven is the dominant package ecosystem** for this account.

**Relevant advisory from the GitHub Advisory Database (Maven ecosystem):**

| Field | Value |
| --- | --- |
| GHSA ID | `GHSA-445c-vh5m-36rj` |
| Severity | medium |
| Affected package | `org.apache.logging.log4j:log4j-core` (Maven) |
| First patched version | **2.25.4** |
| Vulnerable range | `>= 2.21.0, < 2.25.4` |
| Summary | Apache Log4j Core `Rfc5424Layout` log injection (CRLF) due to silent renames of security-relevant config attributes; TLS users silently downgraded to unframed TCP without newline escaping |
| Link | https://github.com/advisories/GHSA-445c-vh5m-36rj |

## 4. Notable observations

- Half of the public repos (2 of 4) are bare forks with no commits of their own visible as distinguishing work.
- Neither original repository has a LICENSE file — a gap for a portfolio.
- No releases, no open issues/PRs, and no CI anywhere — the account has no demonstrated automation footprint.
- Only 1 of 2 original repositories has a README.
- The account's oldest activity (2017) and newest repo push (2019 for originals; 2023 fork) suggest the public footprint is largely dormant coursework.

## 5. Publication details

- This audit is published in repository `github-presence-audit-2` (the unsuffixed name was already taken in the account, so the `-2` suffix was applied) on the `report` branch as `AUDIT.md`.
- CI workflow `.github/workflows/audit.yml` runs on pushes and pull requests, checks that `AUDIT.md` exists, and uploads it as an artifact named `audit-report`.
