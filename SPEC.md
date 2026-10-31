# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** New launch, runtime verification and fresh fast checks passed. Learner reports a successful personal browser test and a keep decision. Documentation accuracy/publication approved on 2026-10-31. PR/CI review remains pending.
**Next step:** Publish the approved five files on the existing feature branch, open the PR and observe actual CI. Merge and issue closure are not authorized.
**Issue:** [STUDIO-001 #1](https://github.com/kushalpatel71/my-server-studio/issues/1).
**Feature branch:** `studio-001-prerequisite-review`.

## Agreed result and actual implementation

One supplied pinned calculator image was newly launched through existing public
Traefik, preserving practical-prod, practical-qa and Traefik. No existing website
image, DNS record, proxy or server baseline was replaced during this launch.
No application source checkout/build or new Droplet was introduced.

- **Actual public URL:** [Calculator HTTPS](https://calc.192.81.212.73.sslip.io).
- **Deployment:** New launch, not adoption; project/router `is373-studio-calculator`.
- **Existing external network:** `hosting-web`; internal application port 8000.
- **Runtime scope:** non-root user 10001:10001, read-only root filesystem,
  dropped capabilities, 256 MiB memory limit, no published application host port.
- **Release selection:** [studio/calculator-release.json](studio/calculator-release.json).
- **Pinned image:** `docker.io/kaw393939/is373_ci_cd@sha256:aec414c990a5de6ed74c9e8dcb105b78f6358c03a8cea70a9d40dcda51c3a8fa`.
- **Expected and observed source commit:** `4600202bad42da0c5ffb11d83ce8364671293d3d`.
- **Private SSH/configuration/recovery details:** Kept in ignored state or the
  protected Mac recovery folder outside this repository; never public evidence.

## Original workflow · actual results, 2026-10-31

The previously approved plan/release and original doctor safety check passed
again before launch. Both existing sites passed trusted HTTPS/content/redirect
checks and their original identities/start times/networks/ports were recorded.
The actual commands ran from the Mac clone:

```sh
python3 studio.py launch
python3 studio.py report
python3 studio.py verify
python3 studio.py report
```

Launch returned `status: passed`, `provenance: launched`, `new_launch: true`.
Before repeat verification, original raw/dated reports were preserved privately
as read-only copies with SHA-256 fingerprints, and the prepared sanitizer's
original launch export was preserved as [studio/launch-evidence.json](studio/launch-evidence.json).

Repeat verify returned `status: passed`, `provenance: already-managed`,
`new_launch: false`, for the SAME calculator container. This describes repeat
verification, not the origin of the deployment. The latest prepared sanitizer
export is [studio/evidence.json](studio/evidence.json). Both reviewed exports are included in the approved publication scope.

| Prepared runtime check | Actual result |
|---|---|
| Running image digest and source revision | Match the supplied selection |
| Health identity/environment | Expected commit, production, healthy response |
| Trusted public HTTPS | Passed; independent Mac trust/health check also passed |
| Valid `6 × 7` | HTTP 200, result 42 |
| `6 ÷ 0` | HTTP 400 |
| Numeric string `"6"` as arithmetic input | HTTP 422 |
| Prepared unrelated-service preservation | Three unrelated containers unchanged in selected identity/state/published-port checks |

Independent comparison additionally confirmed practical-prod, practical-qa and
Traefik retained original container/image identities, start times, restart
counts, networks and port bindings. Docker service start time and Caddy config
hash stayed unchanged. Traefik remains healthy and both original websites still
pass trusted HTTPS 200, original-content and redirect checks. Calculator runtime
user, memory limit, read-only flag, network and lack of host port publication
were independently checked. Resource headroom remained adequate at sampling.

The original Traefik websecure TLS/resolver defaults supplied trusted HTTPS for
the new hostname; an independently validated certificate covers it. Future
renewal and a reboot remain unobserved/untested. This is a supplied-image launch,
not the learner's image build, CI/CD pipeline, whole-host audit or peak-load test.

## Infrastructure/recovery context

The earlier explicitly approved infrastructure migration installed Compose V2,
created the proxy network and moved existing public HTTPS from Caddy to Traefik.
Caddy originals remain preserved for rollback; its service is inactive/disabled.
Docker is enabled and Traefik uses unless-stopped. Six recovery archives were
copied off-host and SHA-256 verified. Snapshot/application restoration, full
proxy rollback and reboot of the new proxy setup remain untested. Detailed
infrastructure evidence, logs, keys, certificates and ACME material stay private.

## Learner documentation review

The learner wrote the prediction, browser-observation wording, automated-test
interpretation and keep/revise explanation with AI drafting assistance, then
reviewed and corrected the statements. [LEARNING.md](LEARNING.md) discloses this
assistance; it does not present independently written answers or describe the
help as only a hint or organization. Accuracy/publication of the corrected record was approved on 2026-10-31. The learner personally confirmed Chrome
6 × 7 displayed 42 and HTTPS loaded without warnings. This browser observation
is separate from Codex API evidence. No screenshot of the
deployed calculator has been supplied or referenced as evidence.

Fresh local `python3 studio.py check --fast` passed Black, Pylint and 91 tests,
with two browser E2E tests deselected/not run. It does not establish full browser
E2E or successful CI. The launch and verification reports remain distinct and
retain their original provenance; the documentation review did not redeploy.

Documentation review checked 35 local file/anchor references and seven external
HTTPS links across the proposed Markdown files and README: all passed. There
are no screenshot file references to validate. The five-file proposal contains
no passwords, certificate/key material, recovery archives or private server
configuration. Sanitized exports retain intended public URL, image/commit/
container identifiers, timestamps and check results. Only these five reviewed files are approved for publication.

## Remaining lesson/GitHub evidence

| Evidence | Actual result / gap |
|---|---|
| Fresh prepared check --fast, documentation review | Black and Pylint passed; 91 tests passed; two browser E2E tests deselected/not run |
| Full E2E and GitHub CI | Two local browser E2E tests not run; GitHub CI pending and not yet run; no successful CI link claimed |
| Learner prediction | AI-assisted draft reviewed by the learner; assistance disclosed in approved LEARNING.md |
| Learner check interpretation | AI-assisted wording reviewed by the learner: API arithmetic result establishes that case, not all operations or complete browser behavior; record approved for accuracy/publication |
| Learner browser observation | Supplied: Chrome 6 × 7 displayed 42; HTTPS without warnings. Codex API results remain separate; no learner API-panel observation inferred |
| Keep/revise decision and reason | AI-assisted explanation reviewed by the learner; learner chose keep, citing working calculation, HTTPS and preserved QA/production sites; record approved for accuracy/publication |
| LEARNING.md accuracy/publication review | Approved by the learner on 2026-10-31 |
| Actual PR, merge, latest main CI and issue closure | Pending; no PR/CI stage started |

Learner excerpts and sanitized exports were reviewed and approved. Before
merge, verify every Markdown target/anchor and screenshot's existence, label and
environment, add actual direct successful CI run links, and verify required files
reach main and are accessible to the professor. A report, deployment or green
check does not replace learner observations or establish lesson completion.

## Optional instructor history

These records are background, not steps to repeat. Original anchors are retained.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
