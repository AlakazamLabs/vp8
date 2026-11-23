# Security policy

## Reporting a vulnerability

Please report security problems **privately**. Do not open a public issue, pull request or discussion.

- **How:** GitHub private vulnerability reporting: the **Security** tab of this repository → **Report a vulnerability** ([direct link](https://github.com/AlakazamLabs/vp8/security/advisories/new)).

Include which crate is affected (`vp8-decoder` or `vp8-encoder`) and its version, your platform and CPU, what you found, and how to reproduce it if you can. A minimal reproduction, such as a stream that crashes or hangs the decoder, is the most useful thing you can send.

## What happens next

1. We acknowledge your report within **3 business days**.
2. The maintainers confirm the problem and work on a fix. We keep you informed, and may ask you questions.
3. The fix is prepared **privately, under embargo**. No public branch, tag, pull request or release carries an unpublished fix.
4. We agree a disclosure date with you. Our default is **90 days** from your report, or sooner once the fix is ready. Nothing is disclosed before a fix is ready, unless the problem is already being exploited in public.
5. On that date the fixed release and its advisory publish **together**: a GitHub Security Advisory and a [RustSec](https://rustsec.org) advisory. The fixed version is never published ahead of its advisory. Affected crate versions are yanked when that is safe for users.
6. We credit you in the advisory, unless you would rather stay anonymous.

## For users of these crates

- Pin exact versions and commit your `Cargo.lock`, so a release reaches you only when you choose to take it.
- Formats and documented error codes are API under semver: a breaking change to any of them is a breaking version.
- Watch [RustSec](https://rustsec.org) or this repository's security advisories for announcements.

## Supported versions

| What | Supported |
|---|---|
| Crates before 1.0 | the latest published minor version |
| Anything older | no |
