# The Risks of LSD

*Originally posted May 30, 2022 on [notes.ethereum.org](https://notes.ethereum.org/@djrtwo/risks-of-lsd)*

### Liquid Staking Derivatives cannot safely exceed consensus thresholds

Liquid staking derivatives (LSD) such as Lido and similar protocols are a stratum for cartelization and induce significant risks to the Ethereum protocol and to the associated pooled capital when exceeding critical consensus thresholds. Capital allocators should be aware of the risks on their capital and allocate to alternative protocols. LSD protocols should self-limit to avoid centralization and protocol risk that can ultimately destroy their product.

*Note, although current LSD protocols such as Lido have a lot of room for improvement, this article does not target short-comings in currently implemented designs. Instead, the aim is to show that LSD protocols have **inherent** issues when they exceed consensus thresholds.*

## Stratum for cartelization

In the extreme, if an LSD protocol exceeds critical consensus thresholds such as 1/3, 1/2, and 2/3, the staking derivative can achieve outsized profits compared to non-pooled capital due to coordinated MEV extraction, block-timing manipulation, and/or censorship -- the cartelization of block space. And in this scenario, staked capital becomes discouraged from staking elsewhere due to outsized cartel rewards, self reinforcing the cartel's hold on staking.

LSD protocols can minimize governance, upgradability, and other risks over time, but the question of "who" gets to be a part of the Node Operator (NO) set remains. This lever is the primary cause of cartelization.

Deciding "who" gets to be a NO is a matter of two questions -- who is added to the set and who is removed the set. This can be designed in one of two ways in the long run -- either via governance (a coin vote or other similar mechanism) or via an automated mechanism around reputation and profitability.

### Option 1: Governance of Node Operators

In the former -- governance deciding NOs -- the governance token (e.g. LDO) becomes a major risk to Ethereum. If the token can decide who can be a node operator in this theoretical majority-LSD, then the token holders can force cartel activities of censorship, multi-block MEV, etc, or else the NO is removed from the set.

In fact, the enforcement of such economically monopolistic activies only strengthens the token's control over the NOs. In the event that the token exercises its monopoly to gain outsized profits through destructive mechanisms, then, in the extreme, NOs would not be nearly as profitable operating independently. Thus the governance token deciding NOs can become a self-reinforcing cartelization and abuse of the Ethereum protocol.

Governance deciding NOs has another distinct risk which is regulatory censorship and control. If pooled stake under one LSD protocol exceeds 50%, this pooled staked gains the ability to censor blocks (and worse-so at 2/3 due to being able to finalize such blocks). In a regulatory censorship attack, we now have a distinct entity -- the governance token holders -- that a regulator can make requests of censorship. Depending on the token distribution, this is likely a much simpler regulatory target than the Ethereum network as a whole. And, in fact, DAO token distributions are generally pretty terrible with just a few entities deciding most votes.

In any sort of token governance control over a majority-LSD, we thus rely on the benevolence of the DAO or however control is structured. Relying on such an entity's benevolence, anonymity, or geographic distribution to prevent attacks is not safe, and we must assume not sufficient in the long run.

### Option 2: Economic selection of Node Operators

In the alternative design -- economic and reputation based NOs -- we actually end up in a similar, albeit automated cartelization. Firstly, entering the set would require time and capital (i.e. put some ETH on the line, akin to rocketpool design, and slowly show profitability and get more pooled ETH allocation). Although the entering of the set requiring time and money could make it hard for new entrants, it is not the true cartelization vector here. Instead it's the requisite automated removal of NOs in the event that they do not perform to some profitability standard.

Kicking from the NO set on profitability is likely the only trustless (non-governance) method to ensure that NOs are good for the pool. Defining profitability is problematic -- either you define some absolute number (e.g. getting good baseline issuance rewards) or you need to define some relative number (e.g. within 10% of average/normal profitability). Given the unpredictability of MEV/TX rewards in some time window but also given the importance of MEV rewards to profits in the long term, this needs to be dynamic and a comparison over some time period to other operators/validators. That is, the system cannot be designed to just have some absolute metric -- must make X in TX fees -- due to the high variance in economic activity of the system over time.

This profitability comparison metric works well when all operators are using "honest" techniques, but if any amount of the NOs defect to utilizing destructive techniques such as multi-block MEV or adjusting block release times to capture more MEV, then they skew the profitability target such that honest NOs will eventually be automatically ejected if they do not join in on the destructive techniques.

This means that in either method -- governance of NOs or economic selection/ejection -- such a pool exceeding consensus thresholds becomes a stratum for cartelization. It's either a direct cartel by governance or it's a destructive, profitability cartel through smart contract design.

### Staked ETH governance fallback

An aside -- some suggest that LSD ETH holders could have a say in governance of their underlying LSD protocol, and thus become a safety backstop on what might be a poorly distributed, plutocratic token.

It is important to note here that ETH holders are not by definition Ethereum users, and in the long run, we expect that there are massively more Ethereum *users* than ETH *holders* (people with ETH held beyond the amount needed to facilitate TXs). This is a critical and important fact that informs Ethereum governance -- there is no on-chain governance granted to ETH holders or stakers. Ethereum is the protocol that *users* choose to run.

ETH holders in the long run are just a subset of users, so staked ETH holders are even a subset from there. In the extreme of all ETH becoming staked ETH under one LSD, governance vote weights or aborts by staked ETH do not protect the Ethereum platform for *users*.

Thus even if the LSD protocol and the LSD holders are aligned on subtle attacks and capture, users are not and can/will react.

## Insidious nature of governance

Even with time-delays in LSD governance such that pooled capital can exit the system before a change occurs, LSD protocols suffer from frog-boil governance attacks. Small, slow changes are unlikely to get staked capital to exit the system, but the system can still drastically change over time.

Additionally, as mentioned above, LSD holders are not the same as Ethereum users. LSD holders might be fine with some sort of censorship-requisite governance vote, but this is still an attack on the Ethereum protocol and one that users and developers will mitigate through the means at their disposal -- social intervention.

*Note*: "Staked ETH can always exit in the event of malicious governance" is not actually technically true today and is not certain to be true in the future. The validator's active key is the only key allowed to exit from staking in the current Ethereum PoS design. Although there are a number of proposals to add the feature for BLS and smart contract withdrawal credentials to initiate exits, these are not yet agreed upon in either intent or design.

## Risks-on-Capital vs Risks-to-Protocol

Much of the above discussion focuses on risks an LSD pool, such as Lido, pose to the Ethereum protocol and not actually the risk to those holding capital in the pooled system. Thus this appears to suffer from the tragedy of the commons -- each individual making a rational decision to stake with the LSD protocol is making a good decision for the user but an increasingly bad decision for the protocol. But, in fact, risk to the Ethereum protocol and risk to capital allocated to the LSD protocol when exceeding consensus thresholds are *tied together*.

Cartelization, abusive MEV extraction, censorship, etc are all threats to the Ethereum protocol and ones that users and devs will respond to in the same methods available for traditional centralization attacks - leak or burn through social intervention. Thus pooling of capital into this stratum for cartelization puts not only the Ethereum protocol at risk, but, in turn, the pooled capital.

These may seem like "tail risks" that are hard to take seriously or that might never happen, but if we've learned anything in crypto it's -- if it can be exploited or has some unlikely "critical edge case", then it will be exploited or collapse much sooner than you think. Time and time again in this open and dynamic setting brittle systems collapse and vulnerable systems are exploited for both fun and profit.

The Ethereum protocol and users can recover from an LSD centralization and governance attack, but it won't be pretty. I recommend that Lido and similar LSD products self-limit for their own sake, and I recommend capital allocators to acknowledge the pooling risks inherent to LSD protocol designs. Capital allocators should not allocate to LSD protocols exceeding 25% of total staked Ether due to the inherent and extreme risks associated.

