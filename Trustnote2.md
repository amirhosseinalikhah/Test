<html>

<div align="justify">

<p>1 基础</p>

<h1><b>1. Introduction</b></h1>


<p>系统设置了9个公证人席位，其中1个席位固定为基金会公证人，另外8个公证人席位对应的公证人平均每150秒（2.5分钟）更换1次。</p>

<p><li>The system is set up to provide nine empty position for Attestors. These empty positions are distributed as eight of the Attestors will be selected from supernodes (aka Public Attestors) and one is for fixed Attestor maintained by the TrutNote itself. The Attestors (except the fixed one) will be replaced every 150 seconds (2.5 min).</li></p>

<p>TrustNote基金会维护9个超级节点，这些超级节点的地址将会写在创世块中。其中第1个是固定公证人，另外8个是替补公证人。</p>

<p><li>The TrustNote maintains nine supernodes and their addresses are written in Genesis unit. The first one is the fixed Attestor and the other eight ones are substitute Attestors.</li></p>

<p>每210240个共识轮称为一个共识年，挖矿总时间为20个共识年。</p>

<p><li>Each 210,240 consensus round is called a consensus year and the total mining time is 20 consensus year. </li></p>

<p>每共识轮的公证奖金是以下两部分相加：该轮的Coinbase奖金和该轮单元的公证费。</p>

<p><li>Total Attestation reward consists of two parts: the Coinbase reward of the consensus round and Attestation fee for the consensus round units.</li></p>

<p>Coinbase总矿藏5亿MN。</p>

<p><li>The total Coinbase reward is 500,000,000 MN.</li></p>

<p>1.1 每共识年内每个共识轮的Coinbase奖金</p>

<h2><b>1.1 Annual Coinbase reward for each Consensus Round</b></h2>

<p>年次,	每共识年总挖矿奖金（MN）,	每共识轮挖矿奖金(MN),	共识轮次范围</p>  

<div align="center"> 

| Year	| Total Coinbase Reward per consensus year (MN)	| The Coinbase reward for each consensus round (MN)  | Consensus Round Number (From-To) |
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

<p>单元公证费计算方法</p>

<h2><b>1.2 Method of calculating the Attestion unit fee</b></h2>

<p>单元交易费分为两部分：单元引用费和单元公证费。</p>

<p><li>The unit transaction fee is divided into two parts: the unit reference fee and the unit Attestation fee.</li></p>

<ul><ul>

<p>单元引用费h是固定的，如200 Note。</p>

<p><li>The unit reference fee h is fixed (e.g. 200 Notes).</li></p>

<p>单元公证费b是根据单元体含有消息的费率r_i和消息占用的字节数n_i计算得到的。</p>

<p><li>The unit Attestation fee "b" is calculated based on the rate r<sub>i</sub> of the unit containing the message and the number of bytes n<sub>i</sub> occupied by the message.</li></p></ul></ul>

<div align="center"><math>b = &sum; r<sub>i</sub> × n<sub>i</sub></math></div>

<p>单元引用费分配给直接引用该单元的地址（与TrustNote1.0相同）</p>

<p><li>The unit reference fee is assigned to the address that directly references the unit (same as TrustNote 1.0)</li></p>

<p>单元公证费用计入单元所在共识轮的公证奖金。</p>

<p><li>The unit Attestation fee is included in the Attestation reward of the consensus round of the unit.</li></p>

<ul><ul>

<p>一个单元稳定后，可以确定促使该单元稳定的拥有最小MCI的主链公证单元，该公证单元所在的共识轮就是该单元的共识轮。</p>

<p><li>Once a unit is stabilized, the Attestation unit which lies on the main chain with the smallest MCI - that makes the unit stable - can be determined. The consensus round in which the Attestation unit is located in the consensus round of the unit.</li></p>

<p>该单元的公证费计入该单元所在共识轮的公证奖金。</p>

<p><li>The Attestation fee for this unit is included in the Attestation reward of the unit's consensus round.</li></p>

</ul></ul>

<p>每轮公证奖金分配方案</p>

<h1><b>2. Attestation reward distribution of each round</b></h1>

<p>公证奖金分配比例</p>

<h2><b>2.1 Attestation reward distribution plan</b></h2>

<p>分配比例,	获得者,	用途</p> 

<div align="center">

|  <b>Proportion</b> |	<b>Dedicated to</b>	| <b>Purpose</b> |  
| :---: | :---: | :---: | 
| 10% | Foundation fixed Attestor | Supernode TFans ranking award | 
| 10% | Foundation fixed Attestor | Maintenance and operational costs | 
| 80% | Public Attestors | Public Attestation reward | 

</div>

<p>超级节点TFans排名奖励方案</p>

<h2><b>2.2 Super Node TFans Ranking Reward Program</b></h2>

<p>非链上功能，由运营人员处理。</p>

<p><li>Non-chain functions are handled by the operator.</li></p>

<p>若发现某公证人发送双花、无效或错误单元，则该公证人会被剥夺公证权，并将其从公证人列表中删除。</p>

<p><li>If it is turned out that an Attestor has a double spent, invalid or wrong unit, the Attestor will be deprived of the Attestation and it will be removed from the Attestors list.</li></p>

<p>注意：不能简单的用替补公证人替换，不同节点发现替换的时机可能不同，容易造成不同节点推导出不同的稳定主链</p>

<p><li>Important Note: It's not possible to substitute this Attestor as the other nodes will find out that the timing differs which results in different nodes having different last stable unit.</li></p>

<p> 公证奖金计算方法</p>

<h2><b>2.3 Method of calculating Attestation reward </b></h2>

<p>全节点和超级节点维护记录每一轮的公证人地址。第一轮，该表是基金会固定公证人和替补公证人；之后任意轮，第一位是基金会固定公证人，其它公证人初始值由前一轮内挖矿结果决定。每一轮公证人列表形式如下：</p>

<p>1. The full node and super node keeping the record of the Attestors addresses of each round. In the first round, the list consists of the fixed Attestor and a substitute Attestor both from TrustNote. Once first round finished, in any round, the first Attestor is the fixed Attestor of the TrustNote and the rest of the Attestors will be determined by the mining results (PoW results) of the previous round. </p>

<div align="center">

|  <b>Attestor Priority</b> | <b>Attestor type</b> | <b>Selection method</b> |  
| :---: | :---: | :---: | 
| 1 | Foundation fixed Attestor | Specified in Genesis unit | 
| 2 - 9 | Public Attestors | PoW |

</div>

<p>若在第i轮内挖矿成功并排名靠前，则该超级节点将成为i+1轮的普通公证人。</p>

<p>2. If the mining result (PoW) of the i<sup>th</sup> round is successful and among top results; the supernode becomes one of the eight Attestors of (i + 1)<sup>th</sup> round.</p>

<p>若在第i轮内选出了的8名普通公证人，则第i轮的普通公证人停止发送公证单元，第i+1轮的公证人开始发送公证单元。</p>

<p>3. If eight Attestors for i<sup>th</sup> round are selected, the Attestors of the i<sup>th</sup> round stop sending Attestation units, and the Attestors of the (i + 1)<sup>th</sup> round start sending the Attestion units.</p>

<p>若第i+1轮的第一个公证单元已经稳定，则第i轮的所有公证单元一定都已经稳定。此时，查表确定第i轮的奖金数量A，基金会固定公证人的公证奖金：</p>

<p>4. If the first Attestation unit of the (i + 1)<sup>th</sup> round becomes stable, all the Attestation units of the i<sup>th</sup> round must have stabilized by then. Therefore, The total Attestation reward A is calculated and the Attestation reward of Attestors of i<sup>th</sup> round (except the fixed Attestor) will be calculated as below:</p>

<div align="center"><math>a<sub>1</sub> = 0.2 * A</math></div>

<p>统计稳定主链中第i轮内的各有效普通公证人各自发送的公证单元数量c_n，计算各普通公证单元总量C、各自占比r_n和各自奖金a_n。</p>

<p>5. The number of Attestation units c<sub>n</sub> sent by each valid public Attestor in the i<sup>th</sup> round which became stable on the main chain and the total amount of public Attestors units C can be calculated. Finally, the portion of Attestation reward for each attestor r<sub>n</sub> and the amount of the Attestation reward for them a<sub>n</sub> can be calculated as below:</p>

<div align="center">
  <p><math>C = &sum; c<sub>n</sub>, n∈{2,3,4,5,6,7,8,9}</math></p>
  <p><math>r<sub>n</sub> =  c<sub>n</sub>/C, n∈{2,3,4,5,6,7,8,9}</math></p>
  <p><math>a<sub>n</sub> = r<sub>n</sub> × (A * 8), n∈{2,3,4,5,6,7,8,9}</math></p>
</div>

<p>20个共识年后</p>

<h1><b>20 years of consensus</b></h1>

<p>不再有挖矿奖励，基金会维护的9个超级节点将成为公证人。。。</p>

<p>There will be no more mining reward, and the nine super nodes maintained by the Foundation will become Attestors.</p>

<p>在挖矿的最后一轮，基金会替补公证人会在下一个整百MCI稳定后上线。。。</p>

<p>In the final round of mining, the Foundation substitutes will be activated once the next one hundred units from the end of last round are stable on the main chain.</p>

<p>问题及解决方案（需要更新TR-02）</p>

<h1><b>Problems and solutions</b></h1>

<p>问题1：谁发，什么时候发，如何防止多个coinbase？</p>

<p>Question 1: Who and when sends the coinbase and how to prevent multiple coinbase?</p>

<p>当前共识轮结束后（下一个共识轮的第一个公证单元变稳定），当前共识轮的公证人给自己发一笔coinbase。自己给自己打钱，动力足，别人可以验证</p>

<p>After the current consensus round (when the first Attestation unit of the next consensus round becomes stable), The public Attestor of the current consensus round sends the money to itself, as the power is sufficient, others can verify it.</p>

<p>问题2：如何避免一个公证人为了获得更多coinbase不断发公证单元？</p>

<p>Question 2: How to avoid a public Attestor from issuing more Attestation units in order to get more coinbase?</p>

<p>在计算公证人Coinbase奖励的时候，主链上同一个公证人的有效公证单元之间必须有三分之一以上的其他公证人发送的公证单元。选出下轮最后一个公证人的公证单元按double计算。</p>

<p>When calculating the Coinbase reward, more than one-third of the valid Attestation units on the Main Chain must be from other Attestors. The Attestation unit of the last Attestor in the next round is selected as double spent.</p>

</div>
</html>

