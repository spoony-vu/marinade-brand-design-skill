---
marp: true
theme: marinade
paginate: true
header: '![w:120](../assets/logos/marinade-logo.svg)'
footer: ''
---

<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _header: '' -->
<!-- _footer: '' -->

#### Investor update

# Marinade Finance
#### Q1 2026

---

<!-- _class: statement -->

# Solana's leading liquid staking protocol with 8.81% APY and $2.1B in total value locked

---

## The opportunity

Staking on Solana represents one of the largest yield opportunities in DeFi, yet **the majority of SOL remains unstaked** or locked in native validators without liquidity.

Marinade solves this by providing:

- **Liquid staking** — stake SOL, receive mSOL, stay liquid
- **Native staking** — delegate to 400+ validators, earn rewards
- **DeFi composability** — use mSOL across the Solana ecosystem

---

<!-- _class: split -->

## Key metrics

<div style="display:grid;grid-template-columns:1fr 1fr;gap:20px">
<div class="bento">
<div class="metric">$2.1B</div>
<div class="metric-label">Total value locked</div>
</div>
<div class="bento">
<div class="metric metric-teal">8.81%</div>
<div class="metric-label">Current APY</div>
</div>
<div class="bento">
<div class="metric">12.4M</div>
<div class="metric-label">SOL staked</div>
</div>
<div class="bento">
<div class="metric">400+</div>
<div class="metric-label">Validators in delegation strategy</div>
</div>
</div>

---

## How Marinade works

<div class="columns-3">
<div class="card">
<div class="step-num">1</div>
<h3>Deposit SOL</h3>
<p>Users deposit SOL into Marinade's staking pool or select native staking</p>
</div>
<div class="card">
<div class="step-num">2</div>
<h3>Receive mSOL</h3>
<p>Get liquid staking tokens that accrue value over time through staking rewards</p>
</div>
<div class="card">
<div class="step-num">3</div>
<h3>Earn yield</h3>
<p>Use mSOL in DeFi protocols while continuing to earn staking rewards</p>
</div>
</div>

---

## Staking flow

```mermaid
graph LR
    A[User SOL] -->|Deposit| B[Marinade Pool]
    B -->|Mint| C[mSOL Token]
    B -->|Delegate| D[400+ Validators]
    C -->|Use in| E[DeFi Protocols]
    D -->|Rewards| B
    E -->|Yield| F[Compound Returns]

    style A fill:#FFFFFF,stroke:#308D8A,color:#151A1A
    style B fill:#308D8A,stroke:#194544,color:#FFFFFF
    style C fill:#94C9C8,stroke:#2B8784,color:#151A1A
    style D fill:#447579,stroke:#194544,color:#FFFFFF
    style E fill:#59A9A7,stroke:#2B8784,color:#FFFFFF
    style F fill:#194544,stroke:#151A1A,color:#FFFFFF
```

<div class="note">Delegation strategy automatically rebalances across validators based on performance, commission, and decentralization metrics</div>

---

## Protocol architecture

```mermaid
graph TB
    subgraph User Layer
        U1[Staker]
        U2[DeFi User]
    end

    subgraph Marinade Protocol
        SP[Stake Pool]
        DS[Delegation Strategy]
        MS[mSOL Mint]
    end

    subgraph Solana Network
        V1[Validator Set]
        SR[Stake Rewards]
    end

    subgraph DeFi Ecosystem
        D1[Lending]
        D2[AMM Pools]
        D3[Yield Vaults]
    end

    U1 -->|SOL| SP
    SP --> DS
    DS --> V1
    V1 --> SR
    SR -->|Accrues to| MS
    SP -->|Mint| MS
    MS -->|mSOL| U2
    U2 --> D1
    U2 --> D2
    U2 --> D3

    style SP fill:#308D8A,stroke:#194544,color:#fff
    style DS fill:#2B8784,stroke:#194544,color:#fff
    style MS fill:#94C9C8,stroke:#447579,color:#151A1A
    style V1 fill:#447579,stroke:#194544,color:#fff
    style SR fill:#59A9A7,stroke:#2B8784,color:#fff
```

---

<!-- _class: teal -->

## Market sizing

<div class="columns-3">
<div class="bento">
<div class="metric" style="color:#FFFFFF">$48B</div>
<div class="metric-label" style="color:rgba(255,255,255,0.6)">TAM</div>
<p style="font-size:0.7em;color:rgba(255,255,255,0.65);margin-top:0.4em">Total staked SOL market cap</p>
</div>
<div class="bento">
<div class="metric" style="color:#94C9C8">$12B</div>
<div class="metric-label" style="color:rgba(255,255,255,0.6)">SAM</div>
<p style="font-size:0.7em;color:rgba(255,255,255,0.65);margin-top:0.4em">Liquid staking addressable market</p>
</div>
<div class="bento">
<div class="metric" style="color:#FFFFFF">$2.1B</div>
<div class="metric-label" style="color:rgba(255,255,255,0.6)">SOM</div>
<p style="font-size:0.7em;color:rgba(255,255,255,0.65);margin-top:0.4em">Marinade current TVL</p>
</div>
</div>

---

## TVL growth trajectory

<div class="bar-chart">
<div class="bar" style="height:15%"><span class="bar-label">$180M</span><span class="bar-cat">Q1 '24</span></div>
<div class="bar" style="height:28%"><span class="bar-label">$420M</span><span class="bar-cat">Q2 '24</span></div>
<div class="bar" style="height:45%"><span class="bar-label">$890M</span><span class="bar-cat">Q3 '24</span></div>
<div class="bar" style="height:58%"><span class="bar-label">$1.2B</span><span class="bar-cat">Q4 '24</span></div>
<div class="bar" style="height:72%"><span class="bar-label">$1.6B</span><span class="bar-cat">Q1 '25</span></div>
<div class="bar" style="height:85%"><span class="bar-label">$1.9B</span><span class="bar-cat">Q2 '25</span></div>
<div class="bar" style="height:100%"><span class="bar-label">$2.1B</span><span class="bar-cat">Q3 '25</span></div>
</div>

<div class="note">Growth driven by native staking launch (Q2 '24) and DeFi integrations expansion</div>

---

<!-- _class: compact -->

## Competitive *positioning*

|  | Marinade | Jito | Lido (wstETH) | Sanctum |
|---|---|---|---|---|
| **TVL** | $2.1B | $1.8B | $14B (ETH) | $800M |
| **Validators** | 400+ | 200+ | 30 | 300+ |
| **Liquid token** | mSOL | JitoSOL | wstETH | Various LSTs |
| **Native staking** | Yes | No | No | No |
| **Commission** | 2% | 4% | 10% | Varies |
| **Chain** | Solana | Solana | Ethereum | Solana |

<div class="note">Marinade is the only protocol offering both liquid and native staking with the broadest validator set</div>

---

## Validator delegation strategy

```mermaid
pie title Delegation distribution
    "Performance score" : 35
    "Decentralization" : 25
    "Commission rate" : 20
    "Uptime history" : 15
    "Community stake" : 5
```

The delegation strategy optimizes for **network health** while maximizing staker returns. Validators are scored across five weighted dimensions, with automatic rebalancing every epoch.

---

## Roadmap

<div class="columns">
<div>

### Completed

- <span class="dot"></span> Native staking launch
- <span class="dot"></span> 400+ validator network
- <span class="dot-light"></span> Governance v2
- <span class="dot-light"></span> USDC vault beta

</div>
<div>

### Upcoming

- <span class="dot"></span> Cross-chain mSOL bridging
- <span class="dot"></span> Institutional custody support
- <span class="dot-light"></span> Advanced delegation analytics
- <span class="dot-light"></span> Mobile staking app

</div>
</div>

---

## Ecosystem partners

<div class="logo-row" style="justify-content:center;gap:48px;margin-top:40px">

![w:100](../assets/logos/marinade-icon.png) ![w:100](../assets/logos/jito-logo.png) ![w:100](../assets/logos/kamino-logo.svg) ![w:100](../assets/logos/flame-protocol.png) ![w:100](../assets/logos/cloud-mascot.png) ![w:100](../assets/logos/compass-icon.png)

</div>

<div style="text-align:center;margin-top:32px">

Integrated with **30+ DeFi protocols** across the Solana ecosystem for maximum mSOL composability

</div>

---

<!-- _class: invert -->
<!-- _class: lead invert -->

## Revenue model

<div class="columns" style="margin-top:24px">
<div class="bento">
<div class="metric" style="color:#94C9C8">2%</div>
<div class="metric-label" style="color:rgba(255,255,255,0.5)">Staking commission</div>
<p style="font-size:0.75em;margin-top:12px">Applied to staking rewards earned by validators in the Marinade delegation strategy</p>
</div>
<div class="bento">
<div class="metric" style="color:#94C9C8">$42M</div>
<div class="metric-label" style="color:rgba(255,255,255,0.5)">Annual protocol revenue</div>
<p style="font-size:0.75em;margin-top:12px">Sustainable revenue directly tied to network staking activity and SOL price</p>
</div>
</div>

---

## Revenue breakdown

```mermaid
pie title Revenue sources (annualized)
    "Liquid staking fees" : 60
    "Native staking fees" : 25
    "USDC vault fees" : 10
    "Partnership revenue" : 5
```

---

<!-- _class: statement -->

#### Built on proven infrastructure

# Securing $2.1B in staked SOL across 400+ validators with zero slashing events

---

<!-- _class: lead teal -->
<!-- _paginate: false -->

# Start staking with Marinade

Visit **marinade.finance** to get started

<div class="note" style="color:rgba(255,255,255,0.5);margin-top:2em">marinade.finance | @MarinadeFinance | Discord</div>
