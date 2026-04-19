# The Agent Identity Framework (AIF)
### Composable Accountability for AI Agents in the Digital Economy

**Author:** William Wei · <https://www.linkedin.com/in/williamwei> · April 2026

---

**The gap.** AI agents are beginning to place orders, sign contracts, commit code, vote in governance, and move money on behalf of people and organizations. The internet's identity and accountability primitives — OAuth, card chargebacks, KYC, court-adjudicated tort — were designed for human principals. They do not extend cleanly to software that acts, delegates, copies itself, and upgrades continuously. Authorization is all-or-nothing. Accountability is ambiguous. Reversibility is implicit and inconsistent across rails.

**What AIF is.** A composable accountability layer between the identity plane (W3C DIDs, Verifiable Credentials, UCAN, OpenID SSF/CAEP) and the settlement plane (x402, MPP, ACP, UCP, card networks, stablecoin escrow). AIF does not replace either. It contributes the accountability surface between them — the part today's landscape leaves underdefined.

**Three minimum artifacts.**

1. **Action Envelope** — a canonical signed wrapper for every binding action, carrying the authority formula, a structured reversibility descriptor, the settlement reference, and the accountability trustee.
2. **Accountability Escrow** — a bonded trustee role that holds a sealed pointer to the liable root principal. Counterparties see who would be liable, not necessarily who the end user is, in the happy path. A valid dispute trigger unseals the pointer.
3. **Receipt protocol** — append-only transparency-log receipts with Merkle inclusion proofs, optionally anchored on-chain for high-value flows. Selective redaction honors deletion obligations without invalidating commitments.

**Identity binds to promises, not weights.** An agent's DID commits to a *behavior contract* and a *harness attestation* (the TEE-rooted policy engine that enforces the contract), plus an optional model-provenance credential from the vendor. Fine-tuning and continuous training do not churn identities; counterparties get a crisp statement of what the agent promised to do.

**Authority is an algebra.** Capability tokens compose with `AND`, `OR`, `THRESHOLD(k of n)`, and `WITHIN(caveat)` — covering joint principals, multi-tenant operators, and cross-org hops natively. Interoperable with UCAN.

**Reversibility is a typed descriptor**, not a letter grade. Fields: window, recoverable value, cooperation requirement, external visibility, compensation policy reference. Shipped-and-returnable and published-and-retractable differ on the right axes; a coffee refund and a million-dollar return no longer share a class.

**Liability is honest.** A protocol cannot bind a court. AIF specifies a **framework-membership allocation** between consenting participants — operator first-loss → reputation bond → per-task bond → insurance pool → residual to root principal — that does not preempt tort law, regulatory rules, or consumer-credit carve-outs.

**Five conformance levels.**
- **L0** — Envelope + authority algebra. Minimum interoperability.
- **L1** — + Accountability Escrow. Enables pseudonymous consumer flows.
- **L2** — + Enforced reversibility + compensation policy. Cross-rail rollback.
- **L3** — + Bonded issuers + anchored receipts. High-value B2B.
- **L4** — + Reputation + insurance pool. Consumer commerce at scale.

Nested: every L*n* is an L*(n-1)*. Adopters start small and advance under commercial pressure.

**Composes with everything shipping now.** Explicit integration seams for x402, MPP, ACP/UCP, A2A, MCP, Microsoft Agent Mesh / IATP, ZeroID, UCAN, SSF/CAEP, Sigstore/Rekor, EAS, and TEE attestations (SEV-SNP, TDX, Nitro).

**Roadmap.** White paper v1.0 published April 2026. Target: Envelope v0 reference implementation (Go, TypeScript) + Accountability Escrow stub + one integration adapter within six months. Two pilot domains: corporate procurement and regulated fiduciary flows. Open governance under Linux Foundation AAIF.

**Open calls.**

- **Design partners** — enterprises in corporate procurement or regulated fiduciary flows willing to pilot L1 or L2 in Q3 2026. LOI, not contract.
- **Co-builders** — one DID/PKI engineer, one payments/escrow engineer, for a twelve-week reference implementation sprint.
- **Standards engagement** — NIST CAISI AI Agent Standards Initiative, Linux Foundation AAIF, W3C CCG, IETF SPICE, UCAN WG.
- **Advisors** — DID community, enterprise payments, insurance underwriting, agent-safety governance.

**Contact.** <https://www.linkedin.com/in/williamwei>

**Full paper:** *The Agent Identity Framework — Composable Accountability for AI Agents in the Digital Economy* (v1.0, April 2026).
