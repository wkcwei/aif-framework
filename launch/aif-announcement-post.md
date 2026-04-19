# When Agents Start Spending Money, Who's Accountable?
## Publishing the Agent Identity Framework (AIF) v1.0

*A proposal for a composable accountability layer for AI agents in the digital economy. Draft for public comment.*

**By William Wei** · April 2026 · [Full paper](#) · [One-pager](#)

---

AI agents are beginning to do things that used to require a person clicking a button. They place orders, sign contracts, commit code, vote in governance, and move money. Some of this already works. Most of it, if we're honest, works because we've wired agents into identity and accountability systems that assume a human is behind every click — OAuth, card chargebacks, KYC, court-adjudicated tort. Those systems carry us through the easy cases. They break on the hard ones.

The break is specific. Authorization is all-or-nothing: an agent with `scope=payments:write` can execute any payment, not just the one its user asked for. Accountability is ambiguous: when a chain of delegations crosses models, operators, orchestration layers, and sub-agents, the question "who is responsible?" has no crisp cryptographic answer. Reversibility is implicit: card networks, ACH, marketplaces, and stablecoin rails each handle reversal differently and inconsistently. Agents transact across all of them, and across a long tail of APIs that have no refund path at all.

The current crop of agent-payment protocols — x402 (Google, OpenAI, Circle, under the Linux Foundation), MPP (Stripe and Paradigm), ACP (OpenAI), UCP (Google) — moves the settlement plumbing forward. The identity side is also moving: Microsoft's Agent Governance Toolkit, ZeroID, the NIST CAISI AI Agent Standards Initiative, the W3C DID and VC work, UCAN. What's still missing is the **accountability layer that sits between them** — the part that makes a binding action cryptographically traceable to a liable party, tags it with typed reversibility semantics, and leaves a dispute-ready receipt.

I've been working on this for a while. Today I'm publishing the first public draft of the **Agent Identity Framework (AIF) v1.0**, a proposal for exactly that layer.

## What's in the paper

The framework contributes three minimum artifacts:

- The **Action Envelope** — a canonical signed wrapper for every binding action, carrying the authority formula, a structured reversibility descriptor, the settlement reference, and the accountability trustee.
- The **Accountability Escrow** — a bonded trustee role that holds a sealed pointer to the liable root principal. Counterparties see who would be liable, not who the end user is, in the happy path. A valid dispute trigger unseals.
- The **Receipt protocol** — append-only transparency-log receipts with Merkle inclusion proofs, optionally anchored on-chain for high-value flows. Selective redaction honors deletion obligations.

Around these sit a small capability algebra for expressing authority (`AND`, `OR`, `THRESHOLD`, `WITHIN` over capability tokens), a typed reversibility descriptor that replaces the usual A/B/C/D letter grade, a tiered issuer market structure with bonds and slashing, and a framework-membership liability allocation that is honest about what a protocol can and cannot do — namely, that a protocol cannot bind a court, but it can make evidence reconstructable and allocations predictable between consenting parties.

Two design moves are worth calling out as slightly unusual.

**Agent identity binds to behavior, not weights.** An agent's DID commits to a behavior contract (allowed action classes, ceilings, refusals, circuit breakers) and a TEE-rooted attestation of the harness that enforces it, not to a hash of the model weights. Fine-tuning and continuous training do not churn identities. Proprietary models remain compatible. The vendor's model-provenance credential becomes one more Verifiable Credential in the stack, not the root of identity.

**Five nested conformance levels.** L0 is the envelope and authority algebra — cheap, adoptable in a sprint. L1 adds the Accountability Escrow. L2 adds enforced reversibility. L3 adds bonded issuers and anchored receipts. L4 adds reputation and an insurance pool. Adopters start at L0 and advance under commercial pressure from counterparties. The framework is not a take-it-or-leave-it stack.

## Where this fits in the landscape

The paper is deliberately complementary to what's being built. An AIF envelope wraps an x402 payment call; the escrow role is defined so Microsoft Agent Mesh and ZeroID implementations can fill it; UCAN capability tokens drop straight into the authority algebra; Sigstore/Rekor is the reference transparency log; EVM L2s provide the anchoring and programmable escrow when needed. Integration seams for each of these are explicit in Section 13 of the paper.

The contribution AIF makes in this landscape is the accountability surface between the identity primitives and the settlement primitives. It's the glue that turns "an agent can pay" into "an agent can pay with dispute-ready receipts, cryptographically traceable authority, typed reversibility, and a trustee who can unseal to a regulator when something goes wrong."

## Where this goes next

The paper is draft v1.0. I'm publishing it now because the standards conversations are live — NIST CAISI stood up its AI Agent Standards Initiative in February, and the Linux Foundation AAIF umbrella is absorbing several of the agent-protocol efforts. A framework that wants to contribute into that process needs to be in public, citable, and composable with what exists.

Next milestones:

- **Reference implementation.** Envelope v0 in Go and TypeScript, Accountability Escrow stub, transparency-log receipt service, one integration adapter (x402 is the obvious first target). Target: six months.
- **Pilots.** Two domains where the economics reward the new primitives immediately: corporate procurement and regulated fiduciary flows. LOIs, then pilots in Q3 2026.
- **Standards engagement.** Formal comment to NIST CAISI; working-group introduction to the Linux Foundation AAIF; contributions to W3C Credentials Community Group, IETF SPICE, UCAN WG.

## Open calls

I'm looking for three things from the people who read this:

1. **Design partners.** If you're at an enterprise in corporate procurement, corporate expense, or regulated fiduciary flows (robo-advisory, benefits administration, healthcare intake) and you're interested in piloting L1 or L2 conformance in Q3 2026 — or you want an LOI conversation with no commitment further than that — please reach out.
2. **Co-builders.** Two engineers to help ship Envelope v0. One with DID/PKI experience; one with payments/escrow experience. Twelve-week scope. Open-source reference implementation; the intent is to contribute to a foundation, not to ship a closed product.
3. **Advisors and reviewers.** DID community, enterprise payments, insurance underwriting, agent-safety governance, regulatory counsel. A second reviewer on the trustee-regulation question (money transmitter vs. notary vs. transfer agent vs. bonded agent) would be particularly valuable.

The paper is a draft for comment. I fully expect parts of it to be wrong; I'd rather find out now than after a reference implementation has baked the mistakes in. Criticism, corrections, and integration requests are all welcome.

[Full paper (PDF)](#) · [One-pager](#) · [Reach out on LinkedIn](https://www.linkedin.com/in/williamwei)

---

*If you're working in this space — standards body, protocol author, enterprise pilot candidate, potential co-builder — I want to hear from you. A line on LinkedIn is the fastest way to reach me.*
