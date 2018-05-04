<html>
<div align="center">
<font face="cambria">
  
<h1><p><b>TrustNote Technical White Paper</b></p></h1>

<p><a target="_blank" href="Docs/ICO.png"><img align="center" src="Docs/ICO.png"></a></p>

<h2><p><b>TrustNote Institute of Technology</b></p></h2>

<h4><p><b>April 2018</b></p></h4>

</font>
</div>

------

<div align="justify">

<font face="cambria" size="3">

<h1><b>Overview</b></h1>

<p>The TrustNote Development Team commissioned by the TrustNote Foundation is pleased to release V1.2 of the TrustNote Technical White Paper.  This document introduces TrustNote’s background, technical characteristics, and user scenarios, it will be updated by the TrustNote Development Team from time to time to reflect evolving the advancements in design and implementation process.  For the latest information about technical white papers, software releases and technical support for developer community, please visit our official website at <a href="www.trustnote.org" target="_blank" rel="external">www.trustnote.org</a>.</p>

<h1><b>Disclaimer</b></h1>
<p><!--justify-->TrustNote Institute of Technology hereby declare that: The current package is experimental and a work-in-progress, and you are using TrustNote at your own risk.  TrustNote also declares that we might change (add/remove packages) without informing the users.  In addition, because of the existence of “private equity” scams targeting crypto-currency investors, TrustNote hereby declare that participation in crypto-currency investment through unauthorized trading channels should always take precautionary measures against such risks.  Neither TrustNote Institute of Technology nor the TrustNote Development Team take responsibility for any consequences of investments via unauthorized trading channels.  Finally, we declare that, TrustNote White paper can be only accessed from:</P>
<ul>
<li><p><a href="https://github.com/trustnote/document" target="_blank" rel="external">https://github.com/trustnote/document</a></p></li>
<li><p><a href="https://trustnote.org/" target="_blank" rel="external">https://trustnote.org/</a></p></li>
</ul>
<p>We do not guarantee the faulty or misleading data available in documents downloaded from any other website rather than two official websites introduced above.</P>

<p><b>© 2018 TrustNote Institute of Technology. All rights reserved.</b></p>

------

<h1><b>Contact Us</b></h1>
<ul>
<li><p>Business Enquiries:  <a href="foundation@trustnote.org" target="_blank" rel="external">foundation@trustnote.org</a></p></li>
<li><p>Technical Support:  <a href="community@trustnote.org" target="_blank" rel="external">community@trustnote.org</a></p></li>
</ul>

</font>
</div>

------

<div align="justify">

<font face="cambria" size="3">
  
<h1><b>Abstract</b></h1>
<p>Today’s blockchain technologies face many challenges such as network congestion, high transaction fees, and long transaction confirmation delay.  TrustNote seeks to address these problems by building the world-leading public Directed Acyclic Graph (DAG) ledger which is minable, capable of handling high concurrent transactions yet still maintain quick transaction confirmation.  TrustNote is focused on creating an easy-to-use, decentralized, low-level digital token blockchain that leverages declarative Smart Contracts with enhanced expression capability, while empowering users to create and publish digital tokens without having to write complex Smart Contracts.  TrustNote has an extensible wallet that provides security and rich API interfaces for digital tokens, blockchain games and social networks, which allowing new innovative ideas to run smoothly on the blockchain network and making user friendly blockchain applications accessible to everyone.  TrustNote has an innovative two-tier consensus mechanism and the TrustME consensus algorithms.  These algorithms are working by selecting a number of Super Nodes periodically to act as attestation authorities which they receive mining rewards according to amount of their validated attestations.</p>

</font>
</div>

------

<div id="toc_container" align="left">
<font face="cambria" size="3">

<h1><b>Contents</b></h1>
<ul class="toc_list">
  <li><a href="#BACKGROUND">BACKGROUND</a></li>
  <li><a href="#WHAT-IS-TRUSTNOTE?">WHAT IS TRUSTNOTE?</a></li>
    <ul><li><a href="#KEY-FEATURES">KEY FEATURES</a></li>
    <li><a href="#DIRECTED-ACYCLIC-GRAPH">DIRECTED ACYCLIC GRAPH</a></li>
    <li><a href="#COMPARISON">COMPARISON</a></li></ul>
  <li><a href="#DATA-STRUCTURES">DATA STRUCTURES</a></li>
    <ul><li><a href="#UNIT">UNIT</a></li>
    <li><a href="#MESSAGE-TYPES">MESSAGE TYPES</a></li></ul>
  <li><a href="#CONSENSUS">CONSENSUS</a></li>
    <ul><li><a href="#NODES">NODES</a></li>
    <li><a href="#UNIT-INTER-REFERENCE">UNIT INTER-REFERENCE</a></li>
    <li><a href="#MAIN-CHAIN">MAIN CHAIN</a></li>
    <li><a href="#TRANSACTION-CONFIRMATION">TRANSACTION CONFIRMATION</a></li>
    <li><a href="#TRANSACTION-FEES-AND-MINING-REWARD">TRANSACTION FEES AND MINING REWARD</a></li>
    <li><a href="#TRUSTME-POW">TRUSTME-POW</a></li>
    <li><a href="#TRUSTME-BA">TRUSTME-BA</a></li>
      <ul><li><a href="#Design-Goals">Design Goals</a></li>
      <li><a href="#Final-Consensus-and-Tentative-Consensus">Final Consensus and Tentative Consensus</a></li>
      <li><a href="#Lottery-Algorithm">Lottery Algorithm</a></li>
       <li><a href="#Byzantine-Agreement">Byzantine Agreement</a></li></ul></ul>
  <li><a href="#SMART-CONTRACT">SMART CONTRACT</a></li>
  <li><a href="#TRUSTNOTE-PLATFORM-AND-APPLICATIONS">TRUSTNOTE PLATFORM AND APPLICATIONS</a></li>
  <li><a href="#ISSUANCE-AND-DISTRIBUTION">ISSUANCE AND DISTRIBUTION</a></li>
  <li><a href="#REFERENCES">REFERENCES</a></li>
<ul>
</font>
</div>

------

<div align="justify">

<font face="cambria" size="3">
  
<h1><a id="BACKGROUND"></a>BACKGROUND</h1>
<p>For nearly 10 years, since January 3, 2009, Bitcoin has been operating safely, a miracle in the history of computer network technology.  The success of Bitcoin unlocked the doors to the future of the world’s economy for digital crypto-currencies; a new world full of imagination. Satoshi Nakamato creatively proposed the Blockchain - a chained data structure based on hash functions - and succeeded in building a well-operated, decentralized peer to peer network which opened the new era of digital crypto-currencies.  Blockchain technologies are developing fast, driving change across many industries, sparking innovation and creativity.</p>
<p>Blockchain has provided a decentralized trust mechanism and has become a brand-new paradigm and key methodology in data protection and data value exchange.  Now in its booming period, blockchain is constantly being integrated with various technologies, various scenarios are also being explored in terms of how to utilize the technical characteristics of blockchain, blockchain applications have been expanded from data tamper resistance and data value exchange to digital tokens and social-networking arenas.  The growing number of blockchain user scenarios pose many challenges for blockchain technology, demanding stronger security, higher transaction concurrency, and shorter transaction acknowledgment delay.</p>
<p>In Bitcoin's blockchain, all the data blocks are aligned in one continuous chain, but due to the limitations on block size and consensus mechanism, the amount of concurrent transactions is limited and transaction confirmations are slow, which resulting in the rise of transaction fees and frequent trading congestions.  To address these issues, the Bitcoin developer community has come up with solutions such as block size increases, segregated witness, and lightning networks, but none of them is perfect.  Those solutions either just ease the problem, or sacrifice security or consistency, and none of them have reached full agreement within the community.  The recent emergence of multiple bitcoin forks, has heated up the debate even further.</p>
<p>The structure of the ‘traditional’ blockchain is the bottleneck that hinders the technology from improving its concurrency. More efficient forms of distributed ledger technology are being sought and a solution which combines Directed Acyclic Graph (DAG) and blockchain (hereinafter referred to as "DAG-ledger") was proposed.  The DAG-ledger has no concept of blocks, so there is no limit to the size of the blocks.  In addition, DAG-ledger uses a new form of transaction verification which referencing the old transaction for transaction confirmation. This allows minor temporary differences between the users’ ledgers, to achieve the goal of preventing transaction obstruction by weakening the consistency of the entire network in a short period. The larger the network is and the greater the transaction volumes are, the shorter the transaction confirmation delay is.</p>
<p>IOTA and Byteball both developed their own public DAG-ledgers in 2016 to accommodate high-frequency trading scenarios.  However, the downside is that although DAG-ledger supports high-frequency trading, in the case of low-frequency trading, the old transaction cannot get enough new transactions to verify and reference, resulting in the old transaction not being confirmed in time, in extreme cases the transaction may never get confirmed.  To address this problem, IOTA proposes a temporary centralized actor called coordinator, which is used to protect the network when the volume of transactions is low, however IOTA does not disclose the design details of such coordinator; Byteball introduces 12 witnesses, implementing transaction confirmation via witness attestation, although Byteball claims its users have the right to choose their own witness, but the transaction quoting rules make it very difficult for users to change witnesses if they choose to do so. TrustNote resolved all these issues by proposing a robust and innovative design. </p>

<h1><a id="WHAT-IS-TRUSTNOTE?"></a>WHAT IS TRUSTNOTE?</h1>
<p>TrustNote is a minable public DAG-ledger with an innovative, two-tier consensus mechanism designed for new applications such as digital tokens issuance, blockchain games and social networks, its digital token is called “TTT”.  TrustNote's goal is to be Light, Fast, and Trust.  "Light" means TrustNote has a light architecture and intelligent contracting system that supports lightweight application extensions and micro wallets; "Fast" means TrustNote supports high concurrency transactions, enjoys fast transaction confirmation, and makes distributed application (DApp) development and deployment much easier; "Trust" means creating a platform that allows new innovative ideas to run smoothly on the ledger, and making user-friendly DApps  accessible to everyone.</p>

<h2><a id="KEY-FEATURES"></a>Key Features</h2>
<ul>
 	<li>Two-tier consensus mechanism, a minable public DAG-ledger </li>
 	<li>Supports high concurrency transactions, benefits from fast transaction confirmation</li>
 	<li>Supports advanced declarative Smart Contracts</li>
 	<li>Token issuance system</li>
 	<li>Cryptographic Algorithm: BLAKE2, EdDSA</li>
 	<li>Multi-platform wallet, light wallet, micro wallet, support third-party extensions</li>
</ul>

<h2><a id="DIRECTED-ACYCLIC-GRAPH"></a>Directed Acyclic Graph</h2>
<p>A Directed Acyclic Graph (DAG), is a finite directed graph with no directed cycles. It consists of finitely many vertices and edges, with each edge directed from one vertex to another, such that there is no way to start at any vertex V and follow a consistently-directed sequence of edges that eventually loops back to V again.  The use of the DAG data structure to store ledger data is gradually getting more developers’ attention.  Projects like IOTA and Byteball have successfully established stable public-ledgers using DAG, the feasibility of a DAG-ledger is proven.</p>
<p>In TrustNote terms, transactions are viewed as messages. Various types of messages are supported, multiple messages can be combined into a data block which is called a “Unit”, and a DAG is formed by inter-referenced Units.  Since each Unit can reference any previous Unit or multiple previous Units, there is no need to spend more computing power and time for solving the consensus problem, nor need to wait for the completion of strong inter-node data synchronization, and because there is no need to assemble multiple Units into blocks, the performance of concurrent transactions is considerably improved and the confirmation delay are reduced to minimum.</p>
</font>
</div>

<div align="center">
<p><a target="_blank" href="Docs/DAG.png"><img align="center" src="Docs/DAG.png"></a></p>
  <p><b>Figure 2-1 DAG</b></p>
</div>

<div align="justify">

<font face="cambria" size="3">

<p>TrustNote uses the following technique to solve the double-spending problem .  First, try to find a Main Chain (MC) starting from Genesis Unit on the DAG and assign indexes to the Units that located on the MC, the Genesis Unit’s index is 0, and so on.  Second, for those Units that do not located on the MC, define their indexes equal to the first MC Unit references this Unit.  Eventually, every transaction on the DAG has an index.  If two transactions try to use the same output, we just need to compare the value of their indexes named Main Chain Index (MCI). The Unit with a smaller index is valid, the Unit with a larger index is invalid, and thus it solves the double-spending problem.  For example, when double-spending occurs (as shown in figure 2-2), after the MCIs are assigned to each transaction, we can determine the transaction whose MCI is 8 is valid, the other transaction whose MCI is 10 is rejected.</p>
</font>
</div>

<div align="center">
<p><a target="_blank" href="Docs/MC.png"><img align="center" src="Docs/MC.png"></a></p>
  <p><b>Figure 2-2 Main Chain (MC)</b></p>
</div>

<div align="justify">

<font face="cambria" size="3">  
  
<p>For security concerns, unlike Bitcoin’s blockchain which is guaranteed by the massive computing power of the network, DAG based TrustNote relies on the fast advance of transactions and the uncertainty of the relationship between the transactions as the "firewall", which leaves the entire system looks too lawless to be attacked.  TrustNote benefits from a two-tier consensus mechanism and an innovative TrustME Consensus Algorithm. Those Super Nodes that participate in the TrustME consensus and contribute to the healthy expansion of DAG-ledger will get the mining reward.</p>

<h2><a id="COMPARISON"></a>Comparison</h2>
<p>Standing on the shoulders of giants, absorbs the advantages of existing blockchain projects and addresses their major issues, a more prosperous TrustNote platform becomes possible.  A comparison of current well-known DAG-ledgers (IOTA and Byteball) with TrustNote is shown in Table 2-1.</p>  
  
</font>
</div>

<div align="center">
<p><b>Table 2-1 DAG-Ledger Comparison</b></p>
  </div>
  
<div align="center"> 
  
|  |	IOTA |	Byteball	| TrustNote |
| :---: | :---: | :---: | :---: |
|Token	| IOTA	| Byte |	TTT |
|Consensus Mechanism |	PoW Cumulative Weight |	12 Witnesses |	Decentralized TrustME Consensus Mechanism |
|Smart Contract	| N/A |	Declarative Contract |	Advanced Declarative Contract |
|Reward	| N/A	| Transaction Reference and Attestation	| Transaction Reference and Mining |
|Nodes	| Full Node, Light Node	| Full Node, Light Node |	Super Node, Full Node, Light Node, Micro Node |
|Transaction Fee |	No |	Yes |	Yes|
|Double Spending | 	PoW Weight Comparison |	Main Chain Sequencing |	Main Chain Indexing|
|Low-frequency Trading |	Centralized Coordinator |	Weak Centralized Attestor	| TrustME Attestor|

   </div>


<div align="justify">
<font face="cambria" size="3">  

<h1><a id="DATA-STRUCTURES"></a>DATA STRUCTURES</h1>

<h2><a id="UNIT"></a>Unit</h2>
<p>When a Node initiates a transaction or sends a message, it creates a new data block called a "Unit" and broadcasts the Unit to its peers.  A Unit may contain multiple messages of various types, each Unit contains the following information:</p>
<ul>
  <li>Header: The hash value of the previous Unit (parent).</li>
<li>Messages: A Unit contains one or more messages, there are various types of message, and each message type has its own unique data structure.</li>
<li>Signatures: A Unit contains one or more users’ signatures.</li>  
<li>Address: A user can have multiple addresses; the addresses are generated with BIP-0044 algorithm.</li>
  </lu>
<p>Definition of each Unit’s field is shown in table 3-1.</p>
</font>
</div>

<div align="center">
  
<p><b>Table 3-1 Field Definition of Unit</b></p>
</div>

<div align="center">
  
| Field Name |	Definition |	Remarks |
| :---: | :---: | :--- |
| version |	TrustNote protocol version number |	e.g. ‘1.0’ |
| alt |	Token identification |	e.g. ‘1’ |
| messages |	Message array |	for more information please see 2.2 |
| authors |	Author array |	Address array of the Unit’s author/authors |
| parent_units |	Parent Unit’s hash array |	Hash values of the Unit’s parent/parents |

</div>

<div align="justify">
<font face="cambria" size="3"> 

<p>The message’s field stores the actual data of the Unit, it is an array of one or more messages. TrustNote supports various types of messages which are distinguished by the app field.</p>
</font>
</div>

<div align="center">
  
<p><b>Table 3-2  Field Definition of messages</b></p>
</div>

<div align="center">

| Field Name | Definition | Remarks |
| :---: | :---: | :---: |
| app | Message type |	e.g. “payment” or “text”, for more information please see 2.2 |
| payload_location |	Location of the message body |	“inline” indicates the message body is stored in the current message; “uri” indicates | the message body is retrievable from a URL address; “none” indicates there is no message body
| payload_hash |	Hash value of the message body	|   |
| Payload	| Message body	| Various message types are used to kept different data format, e.g. a transaction message includes various number of input and output |
| payload_input	| Message input array	| Includes the hash value of the Unit who generated the message, message index, output index etc. |
| payload_output |	Message output array | Includes addresses of recipients, amount of transaction and etc.|

</div>

<div align="justify">
<font face="cambria" size="3"> 

<h2><a id="MESSAGE-TYPES"></a>Message Types</h2>
<p>TrustNote supports various message types which can be further extended if needed, different types of messages are used to store different data formats interpretable by different parsing rules.  Different types of TrustNote message are recognizable by the message’s app field.</p>


<h3>Attestor (app = TrustME)</h3>
<p>No Nodes other than the Attestor Nodes can generate “<b>Attestor</b>” messages, Attestation messages are used to store the attesting results the Node has.  If the first message of a Unit is an Attestation message, then this Unit is an Attestation Unit.  The contents of Attestor’s message include: Consensus Round, Attestation Unit Index, Latest Stable Consensus Round, Attestation Reward of Latest Stable Consensus Round, Seeds, Difficulty, Attesting Priority, etc.  For more information about the Attestation Unit and how to get attested, please refer to chapter 4: Consensus Mechanisms.</p>

```JavaScript
messages:[{
  app:'TrustME',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    round: 'round number',
    sequence: 'sequence number in current round',
    last stable round：'number of the last stable round',
    coinbase of the last stable round：[
      {address:'...',amount:218 MN},
      {address:'...',amount:195 MN},
      ...
    ],
    seed: 'string of seed',
    difficulty: 'difficulty number',
    proof_of_work: 'equihash result unit',
    priority: 'priority of notary'
  }
}]
```

<h3>Transaction (app = payment)</h3>
<p>“<b>Transaction</b>” messages are used to hold tokens’ transactional information.  More than one input and output can be included in a transaction message.  For user defined assets, it is necessary to specify the hash value of the Unit which defines the asset.  A standard transaction message is as follows:</p>

```JavaScript
messages:[{
  app:'payment',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    inputs:[{
      unit:'...',
      message_index:0,
      output_index:0
    }],
    outputs:[
      {address:'...',amount:1200},
      {address:'...',amount:2800}
    ]
  }
}]
```
<h3>Text (app = text)</h3>
<p>“<b>Text</b>” messages are used to hold arbitrary string data.</p>

```JavaScript
messages:[{
  app:'text',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:'any text'
}]
```

<h3>Structured Data (app = data)</h3>
<p>“<b>Structured Data</b>” messages are used to store arbitrary structured data</p>

```JavaScript
messages:[{
  app:'data',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    any structured data
  }
}]
```

<h3>Data Feed (app = data_feed)</h3>
<p>“<b>Data Feed</b>” messages are sent by trusted third parties to trigger Smart Contract.</p>

```JavaScript
messages:[{
  app:'data_feed',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    'data feed name':'...',
    'another data feed name':'...'
  }
}]
```

<h3>Address Definition Change (app = address_definition_change)</h3>
<p>“<b>Address Definition Change</b>” messages are used to update the address definition while retain the old address.</p>

```JavaScript
messages:[{
  app:'address_definition_change',
  definition_chash:'...'
}]
```

<h3>Asset Definition (app = asset)</h3>
<p>“<b>Asset Definition</b>” messages are used to define new digital assets.</p>

```JavaScript
messages:[{
  app:'asset',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    cap:1000000000,
    is_private: true,
        is_transferrable: true,
        auto_destroy: false,
        fixed_denominations: false,
        issued_by_definer_only: true,
        cosigned_by_definer: false,
        spender_attested: false,
    attestors:[...]
  }
}]
```
<p>Definition of each field is shown in table 3-3.</p>

</font>
</div>

<div align="center">
  
<p><b>Table 3-3 Field Definition of Asset Definition message</b></p>
</div>

<div align="center">
  
| Field Name |	Definition |	Remarks |
| :---: | :---: | :---: |
| cap	| Maximum amount of assets which can be defined	|  |
| is_private |	Indicates whether the exchange of assets is private or public	|  |
| is_transferrable |	Indicates if the asset can be transferred between third parties while bypassing the asset definer |	If set as “false”, the asset definer must be either the sole sender or the sole receiver of each transfer |
| auto_destroy |	Indicates if the asset should be destroyed when it is sent to the definer	|   |
| fixed_denominations |	Indicates if the asset can be sent in arbitrary integer amount, or in fixed denominations like traditional currency or coins, e.g. 1, 2, 5, 10, 20, etc.	|   |
| issued_by_definer_only |	Indicates if the asset can only be defined by the definer himself	|   |
| cosigned_by_definer |	Indicates if every transfer must be cosigned by all asset definers |	Useful for regulated assets |
| spender_attested |	Indicates if the spender of the asset must get attested before he spends. If he happens to receive the asset but it is not yet been attested, he must get attested by one of the listed attesters before spending the asset	| Useful for regulated assets |
| attesters |	The list of attesters’ addresses recognized by the asset definer (only when spender attested is set as “true”) |	The list can be later-on updated by the definer, by sending an “asset_attestors” message |
| denominations |	Lists every supported denominations and total amount of each denomination |	Used for fixed_denominations assets only, not shown in the example |
| transfer_condition |	Defines the condition when assets are allowed to be transferred. The syntax of this definition is the same as address, except that it cannot reference any attestation data, such as “sig” |	Usually there are no restrictions except those already defined by other fields |
| issue_condition |	Same as transfer_condition but for issue transactions only	|

</div>

<div align="justify">
<font face="cambria" size="3">

<h3>Asset Attestors (app = asset_attestors)</h3>
<p>“<b>Asset Attestors</b>” messages are used by asset definers to update the Attestors of the asset.</p>

<h3>Poll (app = poll)</h3>
<p>“<b>Poll</b>” messages are used to initiate a poll.</p>

```JavaScript
messages:[{
  app:'poll',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    question:'...',
    choices:['A','B']
  }
}]
```

<h3>Vote (app = vote)</h3>
<p>“<b>Vote</b>” messages are used for initiating a vote.</p>

```JavaScript
messages:[{
  app:'vote',
  payload_location:'inline',
  payload_hash:'hash of payload',
  payload:{
    unit:'hash of the unit where the poll was defined',
    choice:'A'
  }
}]
```

<h1><a id="CONSENSUS"></a>CONSENSUS</h1>
<p>TrustNote adopts a two-tier consensus mechanism comprising “base consensus” and “attested consensus”.  The base consensus, also known as “DAG consensus”, requires new transaction Units to be sent out by Nodes to verify and reference previous transaction Units.  The attested consensus, or “TrustME Consensus”, requires that the sequences of Non-Attestation Units be rigorously determined by Attestation Units generated from the Attestor Nodes.  Such two-tier consensus mechanisms can improve transaction throughput and reduce transaction confirmation delay, thus effectively solving the problem of Excessive Bifurcation and double-spending.</p>
<p>For a more robust TrustNote ecosystem, two TrustME consensus schemes are developed.  Initially, TrustNote uses a Proof of Work (PoW) based scheme called TrustME-PoW; in the future, TrustNote will adopt a Byzantine Agreement (BA) based scheme called TrustME-BA.  No matter which scheme is used, any Super Node participating in the consensus will receive a reward in the form of TTT if they are selected as Attestor Node.</p>
<p>Under the TrustME-PoW scheme, Super Nodes getting the attestation authority by proving their superior computing power; under the TrustME-BA scheme, a pseudo-random algorithm is used to select Attestor Nodes among Super Nodes.  In both scenarios, Attestation Units issued by Attestor Nodes always comply with the unit inter-reference rules, and do not affect the existing references between other Units.  Only after an Attestation Unit becomes a stable Unit in the Main Chain, it could finally justify that an Attestor Node has contributed to TrustNote positively, and thus receive the Attestation reward.  In addition, both schemes encourage fair participation of all Nodes, TrustME consensus mechanisms are fairer, more trustworthy, and safer than the centralized and weak centralized schemes.</p>

<h2><a id="NODES"></a>Nodes</h2>
<p>TrustNote supports four types of Nodes : Super Node, Full Node, Light Node and Micro Node.  The comparison of these Nodes is shown in table 4-1.</p>

</font>
</div>


<div align="center">
  
<p><b>Table 4-1 Comparison of Nodes</b></p>

</div>

<div align="center"> 
  
<div align="center"> 
 
| | Super Node	| Full Node |	Light Node |	Micro Node |
| :---: | :---: | :---: | :---: | :---: |
| ledger	| full ledger	 | full ledger	| light ledger |	N/A |
| transaction |	√ |	√	 | √ |	commissioned |
| DAG consensus |	√ |	√ |	indirect |	× |
| TrustME-PoW |	√ |	× |	×	| × |
| TrustME-BA	| √	| × |	× |	× |
| Hosting Micro Node |	√ |	× |	× |	× |
| deployment |	Mining systems, Cloud Host Server/Workstation, PC	| Cloud Host Server/Workstation, PC |	Smartphone, Tablet PC |	MCU, Smart Card |

</div>

<div align="justify">

<font face="cambria" size="3">

<p>TrustNote has a peer to peer network similar to bitcoin, each Node can select a random set of peer Nodes to propagate messages.  To ensure the messages cannot be changed, each message is signed by the private key of its original sender, other Nodes must validate the signature before forwarding the message.  To avoid message forwarding loop, one Node does not forward the same message twice.</p>
<p>To qualify as a TrustNote Super Node, the following requirements must be met:</p>
<ul>
 	<li>Resource: Has good internet bandwidth, large storage space and enough computing power, ideally with public IP address;</li>
 	<li>TTT:  Hold a certain amount of TTT in multiple consensus rounds;</li>
 	<li>Credibility:  Has a reputable history of always submitting valid Units.</li>
</ul>
<p>A Super Node can participate in the TrustME consensus and become an Attestor Node.  Attestor Nodes will get an Attestation Reward by sending Attestation Units and earn attestation fees from attesting ordinary Units.</p>
  
<h2><a id="UNIT-INTER-REFERENCE"></a>Unit Inter-Reference</h2>
<p>Each Unit in TrustNote can reference multiple Units that have no Parent-Child relationship with each other, the new Unit will preferentially reference the Units with more Parents.  When following a Parent Unit in its Child Unit’s direction, we would see many forks if a Unit is referenced by many Child Units. A certain number of Parent Units will merge into one if these Parents are referenced by one Child.</p>
<p>The purpose of referencing a Parent Unit is to establish an approximated order among the Units.  Before referencing a Parent Unit, a Node needs to validate the Parent Unit. This validation process involves checking whether the signature is valid or not, whether the reference is legal or not, etc.  TrustNote does not require strong synchronization between Nodes, different Nodes may see temporarily inconsistent DAGs.  But this does not undermine the Parent-Child relations that has already been established among the Units, and it may only because the Parent Node has many Childs.  TrustNote supports high transaction throughput with low network latency simply because TrustNote does not enforce strong data synchronization among Nodes.</p>
<p>To minimize the number of garbage Units generated in the DAG, a transaction fee must be paid when any Node submits a new Unit.  The transaction fee is divided and paid to:</p>
<ul>
  <li>The Node(s) who generate newer Unit and reference this Unit as Parent.</li>
  <li>The Attestor Node who attested the Unit.</li>
</ul>

<p>If a Unit is referenced by multiple Child Units, the Node who sends the Child Unit with the smallest hash value will get the referencing fee.  In addition, to qualifying the rewards, the Main Chain Index (MCI) of the Child Unit must equal or be slightly greater than its Parent’s MCI, this restriction encourages Nodes to reference the most recent Parent Unit as quickly as possible and as much as possible so they can get more referencing fees, thus helping the DAG to get fast convergence and reduce the number of forks.</p>

<h2><a id="MAIN-CHAIN"></a>Main Chain</h2>
<p>To choose a single chain along Child-Parent links within the DAG, and then relate all Units to this chain. All the Units will either lie directly on this chain or be reachable from it by a relatively small number of hops along the edges of the graph, this single chain is called Main Chain (MC).  If we build two MCs from two different Childless Units follow the same rule, the two MCs will completely overlap with each other when and after the two MCs intersect at some point.  The worst-case scenario is that two MCs intersect at the Genesis Unit.  Although Nodes are independent from each other when generating new Units, and there is no existence of any possible coordination, we still expect the intersection of the MCs to be as close to the Childless Unit as possible.</p>
<p>Once a Unit has selected an MC, it can establish an index for two conflicting Units that haven’t been indexed.  First, indexing the Units that located on the MC, the index for the Genesis Unit is 0, the index for the Genesis Unit’s Child on the MC is 1, and so on, until all Units lying on the MC are indexed.  For those Units not located on the MC, we can always find the first Unit located on the MC and reference the Unit directly or indirectly, thus assigning a MCI to each Unit.  Consequently, given two Units, the Unit with a smaller MCI must be generated earlier.  If the MCIs of two Units happen to be the same and these two Units are in conflict, the Unit with the smaller hash value is considered the valid one.  TrustNote will keep all double-spending Units including those deemed to be invalid.</p>
<p>The process of building the MC applies the Parent Selection Algorithm recursively. By participating in the TrustME consensus, Super Nodes gain the opportunity to become Attestor Nodes that can send Attestation Units.  By comparing the number of Attestation Units among the available paths, the Parent Selection Algorithm will pick-up one of the Parent Units as the "Best Parent Unit".  For different Nodes, the MC building processes are completely independent and only rely on the DAGs that each Node sees.  Starting from a DAG’s Childless Unit, following the path of the Best Parent Unit, a Node can build an MC through to the Genesis Unit.</p>

<h2><a id="TRANSACTION-CONFIRMATION"></a>Transaction Confirmation</h2>
<p>As new Units are created, each Node keeps track of its current MC as if they are going to create a new Unit for every live Childless Unit or not.  Current MCs may be different for different Nodes because they may see different sets of unstable Units.  The current MC will constantly change itself as new Units arrive.  However, certain parts of the MC that are old enough, will remain unchanged.
When traveling back, all MCs will come to some point, this point and any previous Units are stable and won’t be changed by the arrival of new Units.  In fact, the Genesis Unit is a natural initial stable point.  Assuming we have built a current MC based on the current set of unstable Units, and there are some Units that located on this MC that were previously believed to be stable, this means that all future MCs believe they will meet the same stable Units and travel back along the same path.  If we can find a way of advancing this stable point forward in the opposite direction of the Genesis Unit, then we should be able to prove the existence of such stable point by Mathematical Induction.  Those Units referenced by this stable point will get a definite MCI, and all messages contained in these Units will also get confirmed.</p>

<h2><a id="TRANSACTION-FEES-AND-MINING-REWARD"></a>Transaction Fees and Mining Reward</h2>
<p>The transaction fee must be paid for confirmation and storing the transaction on the network. The node, proposed the transaction, calculates the transaction fee based on the number of bytes generated and pay it instantaneously. The transaction fee is divided into two parts:</p>
<ul>
  <li>60% Referencing Fee</li>
  <li>40% Attestation Fee</li>
</ul>
<p>The Referencing fee will be obtained by the child of the Unit (This indicates that users can earn TTT as they are generating new Units, by referencing a Child Unit).</p>
<p>In TrustNote, the growth of DAG-ledger and the TrustME consensus are asynchronous. At the end of each consensus round, top twenty Super Nodes will be selected and they will be given the authority to submit the Attestation Units. Before the MC becomes stable, there is no way to decide which Attestation Units located on the MC, or to evaluate the effectiveness of the Attestation Units’ references. After each consensus round, and when every Attestation Unit issued by all Attestor Nodes becomes stable, the amount of Attestation Reward for each Attestor Node can be determined. The Attestation Fee will be added to the attestation bonus pool of the current consensus round. The Attestors (on the current consensus round) who their corresponding Attestation Units are located on the MC will receive the Attestation Fee (The share of each of them will be determined by the number of the Attestation Units they generated on the MC in the current round).</p>
<p>The sending Attestation Unit also needs to pay the transaction fee, the calculation of transaction fee is the same as sending ordinary Units.  Since Attestation Units usually containing more information and taking up more storage space than ordinary Units, so its transaction fees are a bit higher, thus this encouraging other Units to reference the Attestation Units.</p>
<p>TrustME consensus is carried out periodically with a certain number of Attestor Nodes always selected for each round. Each time when the TrustME consensus is achieved, the first Attestation Unit generated by the current round’s Attestor Node must contain the list of Attestation Rewards for the previous consensus round. In the same consensus round, Attestation Units generated by other Attestor Nodes no longer contain the Attestation Reward, instead they validate and reference the first Attestation Unit to confirm the Attestation Reward of previous consensus round.  By doing so, the capabilities of Attestor Nodes are weakened, thus preventing malicious Super Nodes from disturbing the Attestation Reward income of Attestor Nodes of previous consensus round, by obtaining the attestation authority multiple times.</p>

<h2><a id="TRUSTME-POW"></a>TrustME-PoW</h2>
<p>TrustME-PoW is a consensus mechanism which selects a small number of Nodes as Attestor Nodes using proof of work at each round and determines the priority of Attestor Nodes accordingly.  The TrustME-PoW consensus algorithm is executed every 5 minutes, each time when a consensus is reached, no more than 20 Super Nodes will be selected as Attestor Nodes. These Attestor Nodes have the authority to send Attestation Units and are rewarded accordingly.</p>
<p>TrustME-PoW is based on the Equihash algorithm, using BLAKE2 as the underlying hash function, to reduce the unfair advantages of ASIC mining, and to encourage equitable participation from more Super Nodes, thus making the probability distribution of Super Nodes becoming Attestor Nodes more reasonable.  The input of the Equihash algorithm include Current Round’s Number, Seeds, the Difficulty Factor and etc.  The Current Round Number begins at 0, incrementing by 1 after each round.  The Seeds of each round of consensus are calculated from the Seeds of the last round of consensus and the consensus results, which can be retrieved publicly and verified.  The Difficulty Factor is calculated from the average computing power of the whole network, and the average time interval of consensus is controllable by adjusting the Difficulty Factor.</P>
<p>Attestation Units must comply with the previously mentioned Unit inter-reference rules.  The Attestation Unit can only reference unstable Unit and must validate the Units it references, and the correctness of the "Child-Parent" relationship, until the stable MC unit is verified.  Attestation Units are encouraged to reference multiple Best Parent Units that are not stable yet, thus to accelerate the stabilization of the Units and promote DAG-ledger’s forward advancement and convergence.</p>
<p>Only when the Attestation Unit becomes the Unit on the MC, the corresponding attestation reward can be obtained.  In a consensus round, the Attestation Units on the MC calculate their proportion of current consensus round’s attestation reward according to the number of effective references.  When each Attestation Unit becomes the MC Unit and stabilizes, the Attestation Unit’s effective references are calculated.</p>  

<h2><a id="TRUSTME-BA"></a>TrustME-BA</h2>
<p>TrustME-BA is a consensus mechanism based on Verifiable Random Function (VRF) and Byzantine Agreement (BA) algorithm, it randomly selects a small number of Super Nodes as Attestor Nodes and determines the priority of the Attestor Nodes.</P>
<p>TrustME-BA is executed once every minute, and every time when a consensus is reached, a number of Super Nodes will be selected as Attestor Nodes in random.  Attestor Nodes have the authority to send Attestation Units which must comply with DAG consensus’ Parent-Child inter-reference rule.  Once the Attestation Unit sent by the Attestor Node stabilizes on the MC, the Attestor Node will get the attestation reward.  When transactions are active and new Units continued to be generated, Attestor Nodes will receive their Attestation rewards in a short time.  When the transactions are less active or even in the worst cases when there is no new Units been generated in the current BA round, Attestor Node will receive its attestation reward after their Attestation Units become stable MC units.</p>

<h3><a id="Design-Goals"></a>Design Goals</h3>
<p>TrustME-BA consensus mechanism is designed to achieve the following two goals:</p>
<h4>Security</h4>
<p>With significant probability, all Super Nodes will agree on the set of selected Attestor Nodes, which means when most of the honest Super Nodes accept a consensus result, then any consensus processes in the future can be traced back to this consensus result.  TrustME-BA assumes: </p>
<ul>
  <li>Honest Super Nodes hold more than two thirds of total TTT in circulation.</li>
  <li>Attackers can participate in consensus and receive the appropriate rewards.</li>
</ul>
<p>The rationale for this assumption is that in order to attack TrustME-BA successfully, attackers must invest enough TTT tokens.  TrustME-BA assumes an attacker can control a certain amount of target Super Nodes, but he cannot control a large quantity of Super Nodes to hold more than two thirds of total TTT in circulation.</p>
<h4>Robustness</h4>
<p>Beyond Security goals, TrustME-BA assumes network reachability to rigorously determine the priorities among Attestor Nodes.  This goal is that all Super Nodes can reach a consensus on a new set of Attestor Nodes selected within one minute.  To establish a robust platform, TrustME-BA makes a strong synchronization assumption that all honest Super Nodes send messages to most of other honest Nodes within a known time frame.  This assumption acknowledges that an attacker may control some of the honest Super Nodes, but he cannot control the entire network in a large scale nor divide the network.</p>  

<h3><a id="Final-Consensus-and-Tentative-Consensus"></a>Final Consensus and Tentative Consensus</h3>
<p>TrustME-BA has two types of consensus status:  </p>
<ul>
  <li>Final consensus</li>
  <li>Tentative consensus</li>
</ul>
<p>When a Super Node reaches final consensus, it means that any other Super Nodes also reached final consensus.  In other words, Super Nodes in the same round must agree on the same consensus result (tentative consensus), regardless of the strong synchronization assumption.  Tentative consensus means that some Super Nodes may have reached a tentative consensus on other Attestation Units, and no Super Node has reached the final consensus.  All Attestation Units must directly or indirectly reference the Attestation Units that were generated before, which ensures the security of TrustME-BA.</p>
<p>There are 2 cases where TrustME-BA may reach tentative consensus.  In the first case scenario (with low probability), if the network is strongly synchronized, an attacker may, let TrustME-BA reaches tentative consensus.  In this case, TrustME-BA will not reach final consensus, and will not confirm that the network has strong synchronization.  But after a few rounds, it is highly probable that the final consensus will be reached.  In the second case, if the network is weakly synchronized and the entire network is compromised by the attacker, in such case TrustME-BA can reach tentative consensus and selects different sets of Attestor Nodes, multiple consensus forks are formed.  This will prevent TrustME-BA from reaching final consensus, because the Super Nodes are divided into different groups, and the groups do not agree with each other.  In order to start the activity again, TrustME-BA will be executed periodically until the disagreement is resolved.  Once the network returns to strong synchronization status, final consensus will be reached in a short period of time.</p>

<h3><a id="Lottery-Algorithm"></a>Lottery Algorithm</h3>
<p>The lottery algorithm is constructed on the basis of a Verifiable Random Function (VRF) that selects a random subset of Super Nodes based on the weightings of each Super Node participating in the TrustME-BA consensus.  The probability of a Super Node being selected is approximately the same as the ratio of its own weighting to total weighting.  The randomness of the lottery comes from the VRF and a publicly verifiable random seed.  Each Super Node can verify whether it is selected using the random seed.</p>
<p>Definition of VRF:  Given an arbitrary string, the VRF outputs the hash value and the result of the proof.</p>
</font>
</div>

<div align="center">
<font face="cambria" size="3">
  <MATH> < hash, &pi; > &larr;	VRF<sub>sk</sub>(seed||role)  </MATH>
</font>
</div>

<div align="justify">

<font face="cambria" size="3">


</html>
