# Upstream provenance

This project is an **independent downstream** derived from [`teefloo/asuswrt-mcp`](https://github.com/teefloo/asuswrt-mcp). It is maintained as its own product and release line rather than relying on the upstream repository as its release authority.

- Upstream repository: `https://github.com/teefloo/asuswrt-mcp`
- Pinned baseline commit: `46516892cade39177327d404fed09d91b1a3a8dd`
- Baseline date: 2026-04-28
- License: MIT; the upstream copyright and license notice are retained in [LICENSE](LICENSE).

The downstream preserves the upstream allowlisted SSH model while carrying a broader sanitized observability surface, bounded WireGuard client management for already-configured slots, ASUS-specific correctness fixes, and its own release/security verification. Generic fixes that are useful independently can still be proposed upstream; the broader capability and safety boundary remains maintained here.

After the first publication, the intended local Git remote roles are:

- `origin` — the independently maintained `X1pheR/asuswrt-mcp` repository.
- `upstream` — `teefloo/asuswrt-mcp`, retained for provenance, comparison, and selectively integrating relevant upstream changes.

Development remains local-first: upstream changes may be fetched and reviewed locally, but this project does not depend on a platform-level repository relationship to track or integrate them.

## Machine-readable downstream patch register

This inline register is the product-owned logical-patch projection used by SDLC-09 structural verification. Its state does not replace current GitHub issue/PR verification, an actual upstream-compatible tested diff, or any required operator-approved product ADR. Unlinked rows are explicitly nonconformant; no historical fork behavior has been grandfathered. Cross-product integration and release actions remain gated separately. Patch scope and local commit mappings require further semantic review before external contribution.

<!-- SDLC-UPSTREAM-REGISTER:1 -->
```json
{
  "schema_version": 1,
  "upstream": "teefloo/asuswrt-mcp",
  "baseline": "46516892cade39177327d404fed09d91b1a3a8dd",
  "patches": [
    {
      "id": "AS-P01",
      "kind": "upstream",
      "scope": "Broader sanitized SSH router observability and bounded WireGuard slot management",
      "local_commits": [
        "6fff61f"
      ],
      "checked_on": "2026-10-10",
      "issue": null,
      "pr": null
    },
    {
      "id": "AS-P02",
      "kind": "upstream",
      "scope": "Syslog management and verification including active-vs-stored state and complete logger arguments",
      "local_commits": [
        "fbe85a0",
        "cb88615",
        "794ad24",
        "57635d5"
      ],
      "checked_on": "2026-10-10",
      "issue": null,
      "pr": null
    },
    {
      "id": "AS-P03",
      "kind": "upstream",
      "scope": "SSH host-key validation and no implicit ssh-agent lookup",
      "local_commits": [
        "f86b830"
      ],
      "checked_on": "2026-10-10",
      "issue": null,
      "pr": null
    },
    {
      "id": "AS-P04",
      "kind": "upstream",
      "scope": "Transitive vulnerable dependency security updates",
      "local_commits": [
        "ce3ae38"
      ],
      "checked_on": "2026-10-10",
      "issue": null,
      "pr": null
    },
    {
      "id": "AS-P05",
      "kind": "upstream",
      "scope": "Downstream verifier and trusted release packaging",
      "local_commits": [
        "31b543a"
      ],
      "checked_on": "2026-10-10",
      "issue": null,
      "pr": null
    }
  ]
}
```

## Convergence lifecycle

Verify existing upstream issues and PRs, current default-branch equivalence, and source-owned regression evidence before submitting missing contributions. A PR that is closed without merge is nonconformant, and a merged PR is not automatically present in an immutable official release. Remove a downstream patch only on a tested candidate against a suitable released upstream artifact. Retire the fork only after verified patch elimination, accepted distribution/ADR disposition, rollback readiness, consumer parity, and separate operator approval for production/retirement.
