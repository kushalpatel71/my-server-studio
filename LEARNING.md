# Lesson 01 · Conversation evidence

Written by me with drafting, then reviewed and corrected by me.
 Documentation accuracy and publication were approved by me on 2026-10-31.

**Lesson:** STUDIO-001.

## Prediction

 prediction reviewed by me and recorded before the detailed
calculator:

> I predict that when someone enters my calculator URL in a browser, DNS will point the request to my DigitalOcean server. Traefik will receive the HTTPS request on port 443 and recognize the calculator hostname. It will then forward the request through the hosting-web Docker network to the calculator container running on port 8000. The calculator will process the request and send the result back through Traefik to the browser.
>
> I think Traefik will also handle the HTTPS certificate, so the calculator can be accessed securely without affecting my existing QA and production websites.


## Check interpretation



> One automated test checked 6 × 7 and received HTTP 200 with the correct answer of 42. This shows that the deployed calculator API can process that calculation correctly.
>
> However, this single test does not prove that every calculator operation or browser interaction works. Other inputs, error cases, and the complete browser experience still need separate tests.

## Browser observation

Learner-reported live URL: [calculator](https://calc.192.81.212.73.sslip.io/).

written and seen by me:

> I opened my calculator website in Chrome and tested 6 × 7. The calculator displayed 42, which is the correct answer. The website loaded using HTTPS without any security or certificate warnings.

The learner personally confirmed the Chrome actions, displayed result and
absence of HTTPS warnings above. The API checks
below were run by Codex; no separate learner API-panel observation is claimed.
Earlier classroom/pre-launch observations are not deployed-calculator evidence.
No deployed-calculator screenshot has been supplied or included in this proposal.

## Keep decision

it is been reviewed by me: 

> I decided to keep the current deployment because the calculator is working correctly, HTTPS is secure, and my existing QA and production websites are still running without problems. I don't think any changes are needed right now for this assignment.

## AI assistance and technical evidence

AI helped draft the prediction, browser-observation, automated-test
interpretation. The learner reviewed the statements
and personally confirmed the browser experience described above, independently written answers.
AI handled setup, staged infrastructure work, deployment, automated
verification and documentation. This record does not establish independent
authorship or constitute a grade.

Codex API checks: 6 × 7 → HTTP 200/result 42; division by zero → HTTP 400;
numeric-string input → HTTP 422. Image/commit and trusted HTTPS checks passed.
Original websites and Traefik passed selected preservation checks. See the
[original launch evidence](studio/launch-evidence.json),
[repeat verification](studio/evidence.json) and [SPEC.md](SPEC.md).

The requested fresh `python3 studio.py check --fast` passed Black, Pylint and
91 tests. Two local browser E2E tests were deselected/not run. Subsequently,
[PR #2](https://github.com/kushalpatel71/my-server-studio/pull/2) was merged with learner approval.
[PR CI](https://github.com/kushalpatel71/my-server-studio/actions/runs/41253368220) and
[main CI](https://github.com/kushalpatel71/my-server-studio/actions/runs/41253684225) passed all three required jobs.
Each CI run passed 91 unit/integration tests and both real-image Chromium E2E
tests using an isolated runner fixture, separate from the personal browser observation. [Issue #1](https://github.com/kushalpatel71/my-server-studio/issues/1)
records the work and its current completion state.

## Review

Approved by me the learner on 2026-10-31 for accuracy and publication of the
reviewed statements and disclosed AI assistance. Publication and PR #2 merge
were separately authorized. See [documentation PR #3](https://github.com/kushalpatel71/my-server-studio/pull/3) and
[Issue #1](https://github.com/kushalpatel71/my-server-studio/issues/1) for current merge, CI and completion state. Learner statements
are unchanged.
Approval confirms record accuracy; it is not a grade or proof of understanding.
