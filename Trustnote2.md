<html>
<div align="justify">

<h1><b>1. Introduction</b></h1>

<li>The system is setup to provide nine empty position for Attestors. These empty positions are distributed as eight of the Attestors will be selected from supernodes (aka Public Attestors) and one is for fixed Attestor maintained by the TrutNote itself. The Attestors (except the fixed one) will be replaced every 150 seconds (2.5 min).</li>
<li>The TrustNote Foundation maintains nine supernodes whose their addresses is written in Genesis unit. The first one is the fixed Attestor and the other eight ones are substitue Attestors.</li>
<li>Each 210,240 consensus round is calles a consensus year and the total mining time is 20 consensus year.</li>
<li>Total Attestation reward consists of two parts: the Coinbase reward of the consensus round and Attestation fee for the consensus round units.</li>
<li>The total Coinbase reward is 500,000,000 MN.</li>

<h2><b>1.1 Coinbase reward for each Consensus Round per Consensus Year</b></h2>

<div align="center"> 
  
| year	| Total Coinbase Reward per consensus year (MN)	| The Coinbase reward for each consensus round (MN)  | Consensus Round Number (From-To) |
| :---: | :---: | :---: | :---: |
| 1 | 45745654.16 | 217.59 | 1 - 210240 |
| 2 | 37157017.22 | 176.74 | 210241 - 420480 |
| 3 | 32901330.89 | 156.49 | 420481 - 630720 |
| 4 | 30180876.28 | 143.55 | 630721 - 840960 |
| 5 | 28226617.69 | 134.26 | 840961 - 1051200 |
| 6 | 26724184.86 | 127.11 | 1051201 - 1261440 |
| 7 | 25516460.44 | 121.37 | 1261440 - 1471680 |
| 8 | 24514489.08 | 116.60 | 1471681 - 1681920 |
| 9 | 23663396.98 | 112.55 | 1681921 - 1892160 |
| 10 | 22927137.86 | 109.05 | 1892161 - 2102400 |
| 11 | 22280864.47 | 105.98	| 2102401 - 2312640 |
| 12 | 21706783.19 | 103.25	| 2312641 - 2522880 |
| 13 | 21191750.72 | 100.80 | 2522881 - 2733120 |
| 14 | 20725806.14 | 98.58 | 2733121 - 2943360 |
| 15 | 20301235.29 | 96.56 | 2943361 - 3153600 |
| 16 | 19911952.5 | 94.71 | 3153601 - 3363840 |
| 17 | 19553079.5 | 93.00 | 3363841 - 3574080 |
| 18 | 19220650.9 | 91.42 | 3574081 - 3784320 |
| 19 | 18911403.55 | 89.95 | 3784321 - 3994560 |
| 20 | 18622622.67 | 88.58 | 3994561 - 4415040 |
| 21 | 0 | 0 | 4415041 - XXXXXXX |

</div>

<h2><b>1.2 Method of calculating the Attestion unit fee</b></h2>

<li>The unit transaction fee is divided into two parts: the unit reference fee and the unit Attestation fee.</li>
<ul><ul><li>The unit reference fee h is fixed (e.g. 200 Notes).</li>
<li>The unit Attestation fee "b" is calculated based on the rate r<sub>i</sub> of the unit containing the message and the number of bytes n<sub>i</sub> occupied by the message.</li></ul></ul>
<div align="center">
<math>b = &sum; r<sub>i</sub> × n<sub>i</sub></math>
</div>

<li>The unit reference fee is assigned to the address that directly references the unit (same as TrustNote 1.0)</li>

<li>The unit Attestation fee is included in the Attestation reward of the consensus round of the unit.</li>

<ul><ul><li>Once a unit is stabilized, the Attestion unit which lies on the main chain with the smallest MCI - that makes the unit stable - can be determined. The consensus round in which the Attestation unit is located is the consensus round of the unit.</li>
<li>The Attestation fee for this unit is included in the Attestation reward of the unit's consensus round.</li>
</ul></ul>

<h1><b>2. Attestation reward distribution of each round</b></h1>

<h2><b>2.1 Attestation reward distribution plan</b></h2>

<div align="center">
  
|  <b>Proportion</b> |	<b>Dedicated to</b>	| <b>Purpose</b> |  
| :---: | :---: | :---: | 
| 10% | Foundation fixed Attestor | Supernode TFans ranking award | 
| 10% | Foundation fixed Attestor | Maintenance and operational costs | 
| 80% | Public Attestors | Public Attestation reward | 

</div>

<h2><b>2.2 Super Node TFans Ranking Reward Program</b></h2>

<li>Non-chain functions are handled by the operator.</li>

<li>If it is turned out that an Attestor has a double spent, invalid or wrong unit, the Attestor will be deprived of the Attestion and it will be removed from the Attestors list.</li>

<li>Important Note: It's not possible to substitute this Attestor as the other nodes will find out that the timing differs which results in different nodes having different last stable unit.</li>

<h2><b>2.3 Method of calculating Attestation reward </b></h2>

<p>1. The full node and super node keeping the record of the Attestors addresses of each round. In the first round the list consists of the fixed Attestor and a substitute Attestor both from TrustNote. Once first round finished, in any round, the first Attestor is the fixed Attestor of the TrustNote and the rest of the Attestors will be determined by the mining results (PoW results) of the previous round. </p>

<div align="center">
  
|  <b>Attestor Priority</b> | <b>Attestor type</b> | <b>Selection method</b> |  
| :---: | :---: | :---: | 
| 1 | Foundation fixed Attestor | Specified in Genesis unit | 
| 2 - 9 | Public Attestors | PoW |

</div>

<p>2. If the mining result (PoW) of the i<sup>th</sup> round is successful and among top results; the supernode becomes of one the eight Attestors of (i + 1)<sup>th</sup> round.</p>

<p>3. If eight Attestors for i<sup>th</sup> round are selected, the Attestors of the i<sup>th</sup> round stop sending Attestation units, and the Attestors of the (i + 1)<sup>th</sup> round start sending the Attestion units.</p>

<p>4. If the first Attestation unit of the (i + 1)<sup>th</sup> round becomes stable, all the Attestation units of the i<sup>th</sup> round must have stabilized by then. Therefore, The total Attestation reward A is calculated and the Attestion reward of Attestors of i<sup>th</sup> round (except the fixed Attestor) will be calculated as below:</p>

<div align="center">
<math>a<sub>1</sub> = 0.2 * A</math>
</div>

<p>5. The number of Attestion units c<sub>n</sub> sent by each valid public Attestor in the i<sup>th</sup> round which became stable on the main chain and the total amount of public Attestors units C can be calculated. Finally, the portion of Attestion reward for each attestor r<sub>n</sub> and the amount of the Attestion reward for them a<sub>n</sub> can be calculated as below:</p>

<div align="center">
  <p><math>C = &sum; c<sub>n</sub>, n∈{2,3,4,5,6,7,8,9}</math></p>
  <p><math>r<sub>n</sub> =  c<sub>n</sub>/C, n∈{2,3,4,5,6,7,8,9}</math></p>
  <p><math>a<sub>n</sub> = r<sub>n</sub> × (A * 8), n∈{2,3,4,5,6,7,8,9}</math></p>
</div>

<h1><b>20 years of consensus</b></h1>

<p>There will be no more mining reward, and the nine super nodes maintained by the Foundation will become Attestors.</p>

<p>In the final round of mining, the Foundation substitues will be activated once the next one hundred units from end of last round is stable on the main chain.</p>

<h1><b>Problems and solutions</b></h1>

<p>Question 1: Who and when sends the coinbase and how to prevent multiple coinbase?</p>

<p>After the current consensus round (when the first Attestation unit of the next consensus round becomes stable), The public Attestor of the current consensus round sends the money to itself, as the power is sufficient, others can verify it.</p>

<p>Question 2: How to avoid a public Attestor from issuing more Attestation units in order to get more coinsbase?</p>

<p>When calculating the Coinbase reward, more than one third of the valid Attestation units on the Main Chain must be from other Attestors. The Attestation unit of the last Attestor in the next round is selected as double spent.</p>

</div>
</html>
