# 🪙 FOM token

<figure><img src=".gitbook/assets/ill-fom.jpg" alt="🪙 FOM token"><figcaption><p>Formion — 🪙 FOM token</p></figcaption></figure>

**FOM is Formion’s token on Base (Ethereum L2)** — an ERC-20 with a fixed supply of **1,000,000,000 FOM**, minted once to a 2-of-3 Safe. The contract is OpenZeppelin v5.4 ERC-20 + Permit, with no owner, no mint function, no transfer tax, no pause and no blacklist, and it is not upgradeable. FOM grants no ownership, dividend, profit-share or claim on Formion. Full details: [formion.ai/fom](https://formion.ai/fom).

{% embed url="https://www.youtube.com/watch?v=ASPAioevc7k" %}
🎬 **FOM — the key to the Formion AI trading ecosystem.** The FOM launch film (1:12).
{% endembed %}

## Launch and liquidity

FOM launches on **Uniswap (Base) on Wednesday, 14 October 2026**. The launch pool is **Uniswap v3 FOM/WETH**: **40,000,000 FOM + 3 ETH**, with a 1% pool fee. The LP position is locked for **24 months on UNCX**, held by a **2-of-3 Safe**. The remaining 60,000,000 FOM of the liquidity allocation is a reserve that moves only through published programmes.

There is **no presale, no private sale, no ICO and no launchpad**. Launch liquidity (3 ETH) and launch costs (~1.08 ETH) are funded by the founder's own funds. The **contract address is TBA at launch** and will be published on [formion.ai/fom](https://formion.ai/fom) — only trust the address from official Formion channels, and verify it before you swap.

**Audit: SolidProof — token contract** (0 critical · 0 high): [audit project](https://app.solidproof.io/projects/formion-ai). **Vesting: unmodified OpenZeppelin v5.4 `VestingWallet`** (7 contracts). The token’s fixed supply does not remove vesting schedules.

## Audit and KYC

### Smart-contract audit

<figure><img src=".gitbook/assets/ill-fom-audit.jpg" alt="FOM smart-contract audit by SolidProof"><figcaption></figcaption></figure>

**SolidProof** audited the FOM token contract: **0 critical, 0 high, 0 medium and 0 low findings**, plus 1 optimization and 6 informational notes, with a **TrustNet score of 92.45**. The contract is **ownerless**, has **no mint function**, **no blacklist** and is **not upgradeable** — after the one-time mint there is no function that can create new tokens, pause, tax or block a transfer. Read the full report on the [SolidProof project page](https://app.solidproof.io/projects/formion-ai).

### KYC

<figure><img src=".gitbook/assets/ill-fom-kyc.jpg" alt="Founder KYC verified by SolidProof"><figcaption></figcaption></figure>

The **founder's identity (KYC) is verified by SolidProof**. The KYC badge and its status are public on the same [SolidProof project page](https://app.solidproof.io/projects/formion-ai), so anyone can check it independently. Entity and team KYC are on the roadmap.

{% hint style="warning" %}
An audit and a KYC reduce specific risks — hidden mint or admin functions, an anonymous team — but they are not a guarantee of price or returns. Only trust the contract address published on [formion.ai/fom](https://formion.ai/fom).
{% endhint %}


## Allocation and vesting

| Allocation | FOM | Supply | Release schedule |
|---|---:|---:|---|
| Community | 300,000,000 | 30% | 260M linear over 36 months to the Safe; 40M in the Safe from day one for the airdrop and launch programmes |
| Treasury | 245,600,000 | 24.56% | Linear over 36 months |
| Team | 150,000,000 | 15% | 12-month cliff, linear through month 36 |
| Liquidity | 100,000,000 | 10% | Pool and reserves |
| Marketing & partners | 100,000,000 | 10% | 6-month cliff, linear over 18 months |
| Core contributor | 54,400,000 | 5.44% | 1% (544,000) linear over months 0–6, rest linear months 6–25; complete at month 25 |
| Advisors | 50,000,000 | 5% | 6-month cliff, linear over 18 months |

Every locked allocation sits on a public vesting contract; the rest (40M Community and the 60M liquidity reserve) sits in the labeled 2-of-3 Safe. The Core contributor line sits on two of these contracts, and released tokens are pushed to the contributor's wallet daily. This allocation is separate from the pool tokens.

## Platform licences and FORA Agent levels

Platform licences are priced in **USD** and govern platform limits. FOM does not replace or discount a licence. Planned FOM access levels unlock agent capabilities within those licence limits.

| Level | Locked FOM | Planned utility |
|---|---:|---|
| Holder | 100,000 | 30 extra FORA messages/day, realtime screener, 20% lower add-on prices when paid in FOM |
| FORA Agent | 1,000,000 | Browser agent for chart navigation, pages and research; frontier models |
| Agent Pro | 5,000,000 | Pine writing and testing, backtests, strategy search and paper-to-live workflows |
| FORA AGI | 10,000,000 | Autonomous workflows on the user’s own accounts and priority access |

FOM is planned for **add-ons, marketplace purchases and agent credits**, rather than platform licences. Locked FOM stays yours, with a 7-day unbonding when you unlock; 75% of the FOM paid for agent credits is burned. Agent levels and future capabilities roll out in phases; they are not all available at launch. See the [roadmap](roadmap.md). Access locks describe product eligibility, not a promised financial return.

```mermaid
flowchart LR
  Licence[USD platform licence] --> Limits[Platform limits]
  FOM[Locked FOM] --> Agent[Agent level]
  Agent --> Limits
```
