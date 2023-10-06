<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Content](#content)
  - [Coding (parameter? I hardly know ‘er)](#coding-parameter-i-hardly-know-er)
    - [No in-code fallbacks for configs](#no-in-code-fallbacks-for-configs)
    - [Extremely strict RPC settings](#extremely-strict-rpc-settings)
    - [Never give up on local testing](#never-give-up-on-local-testing)
    - [Avoid state like the plague](#avoid-state-like-the-plague)
  - [Merging (where we’re going, we don’t need tests)](#merging-where-were-going-we-dont-need-tests)
    - [Use Git](#use-git)
    - [Don’t waste time on code coverage](#dont-waste-time-on-code-coverage)
    - [Prioritize real-world validation](#prioritize-real-world-validation)
    - [For infra changes, make plans extremely obvious](#for-infra-changes-make-plans-extremely-obvious)
    - [For code changes, make regressions extremely obvious](#for-code-changes-make-regressions-extremely-obvious)
  - [Deploying (no sleep til prod)](#deploying-no-sleep-til-prod)
    - [Use Docker](#use-docker)
    - [Deploy everything all the time](#deploy-everything-all-the-time)
    - [Validate deployments as they go](#validate-deployments-as-they-go)
    - [Enable limited “instant” config rollouts](#enable-limited-instant-config-rollouts)
  - [Operating (my god, it’s full of pods)](#operating-my-god-its-full-of-pods)
    - [Use Kubernetes](#use-kubernetes)
    - [Use Helm](#use-helm)
    - [Avoid operators and CRDs](#avoid-operators-and-crds)
    - [Run 3 of everything](#run-3-of-everything)
    - [Structured logs are non-negotiable](#structured-logs-are-non-negotiable)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Content

Font: <https://www.willett.io/posts/precepts/>

## Coding (parameter? I hardly know ‘er)

---

### No in-code fallbacks for configs

### Extremely strict RPC settings

### Never give up on local testing

Containerizing the local test environment can make it easier to keep dependencies straight and consistent across machines

:warning: Tool: [toast](https://github.com/stepchowfun/toast).

### Avoid state like the plague

## Merging (where we’re going, we don’t need tests)

---

### Use Git

Use it for everything – infrastructure, configuration, code, dashboards, on-call rotations. Your git repository is your point-in-time-recoverable source of truth.

### Don’t waste time on code coverage

...

### Prioritize real-world validation

The highest-value-per-time-spent kind of test is just pushing your change to staging (or better, prod!) and showing it does what you wanted and doesn’t break everything. Second best is integration tests, with unit tests notably coming in last place – i.e. “only if you have some time”.

:warning: [estic super en contra del que diu]

### For infra changes, make plans extremely obvious

...

### For code changes, make regressions extremely obvious

...

## Deploying (no sleep til prod)

---

### Use Docker

...

### Deploy everything all the time

Every day that goes by without you deploying increases the chances that it’s actually secretly been broken (by someone’s change, an dependency update, an third-party API removal), and `it’s very hard to track down what went wrong two weeks after the fact`.

### Validate deployments as they go

...

### Enable limited “instant” config rollouts

It might sound counterintuitive (since an “instant” rollout often means “break everything all at once”) `but the ability to disable a problematic feature flag or add an IP to a blocklist in under 5 minutes more than offsets the increased risk`. It enables everyone to move fast, but must be managed carefully!

## Operating (my god, it’s full of pods)

---

### Use Kubernetes

Kubernetes gives infra teams scalability superpowers

### Use Helm

Or some other tool for `managing Kubernetes manifests`, I’m not picky – the important thing is that you ~never directly use kubectl apply, edit, or delete. The resource lifecycle needs to be findable in version control.

### Avoid operators and CRDs

...

### Run 3 of everything

Like with backups, two is one and one is none.

### Structured logs are non-negotiable
