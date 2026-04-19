# LinkedIn Launch Checklist

## Publish order

1. Publish the **LinkedIn article** using `launch/aif-announcement-post.md`
2. Publish the **short LinkedIn status update** using the text below
3. Add the **first comment** on your own status post with the paper and one-pager links

---

## 1. LinkedIn article

**Title**

`When Agents Start Spending Money, Who's Accountable? Publishing the Agent Identity Framework (AIF) v1.0`

**Subtitle**

`A proposal for a composable accountability layer for AI agents in the digital economy. Draft for public comment.`

**Body source**

Use:
- `launch/aif-announcement-post.md`

**Suggested hashtags**

`#AIAgents #AgenticAI #DigitalIdentity #StandardsAndProtocols`

---

## 2. Short LinkedIn status update

Publish this after the article is live, then replace `[LINKEDIN_ARTICLE_URL]` with the actual article URL.

```text
Publishing today: The Agent Identity Framework (AIF) v1.0, a proposal for the accountability layer that's missing from agentic commerce.

AI agents are beginning to place orders, sign contracts, commit code, and move money. OAuth, card chargebacks, and KYC were designed for humans and don't extend cleanly to autonomous software. The current crop of agent payment protocols, like x402, MPP, ACP, and UCP, moves settlement forward. The identity side is also moving: Microsoft Agent Mesh, ZeroID, the NIST CAISI initiative, W3C DIDs, and UCAN. What's still missing is the accountability layer that sits between them.

AIF contributes three minimum artifacts:
• Action Envelope, a signed wrapper for every binding agent action carrying authority, typed reversibility, settlement reference, and trustee
• Accountability Escrow, a bonded trustee holding a sealed pointer to the liable root principal, unsealed only on valid dispute
• Receipt protocol, append-only transparency-log receipts with inclusion proofs, anchored on-chain where needed

Five nested conformance levels let adopters start small and advance as counterparties demand. Explicit integration seams with what is already shipping now.

Looking for design partners, co-builders, and reviewers.

Long-form announcement: [LINKEDIN_ARTICLE_URL]

Criticism welcome, this is a draft for comment.

#AIAgents #AgenticAI #DigitalIdentity
```

---

## 3. First comment on your own status post

Post this as the first comment right after the short status update goes live.

```text
Paper + one-pager:

Full paper (PDF): https://wkcwei.github.io/aif-framework/paper/aif-white-paper.pdf
Full paper (Markdown): https://wkcwei.github.io/aif-framework/paper/aif-white-paper.md
One-pager (PDF): https://wkcwei.github.io/aif-framework/summary/aif-one-pager.pdf
One-pager (Markdown): https://wkcwei.github.io/aif-framework/summary/aif-one-pager.md
Repo: https://github.com/wkcwei/aif-framework
```

---

## Live links

- Repo: https://github.com/wkcwei/aif-framework
- GitHub Pages: https://wkcwei.github.io/aif-framework/
- Paper PDF: https://wkcwei.github.io/aif-framework/paper/aif-white-paper.pdf
- One-pager PDF: https://wkcwei.github.io/aif-framework/summary/aif-one-pager.pdf
