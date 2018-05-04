<html>
<div align="center">
<p><font face="cambria" size="12"><b>TrustNote Technical White Paper</b></font></p>

<p><a target="_blank" href="Docs/ICO.png"><img align="center" src="Docs/ICO.png"></a></p>

<p><font face="cambria" size="5"><b>TrustNote Institute of Technology</b></font></p>

<p><font face="cambria" size="3"><b>April 2018</b></font></p>
</div>

------

<div align="justify">

<font face="cambria" size="3">

<b>Overview</b>

<p>The TrustNote Development Team commissioned by the TrustNote Foundation is pleased to release V1.2 of the TrustNote Technical White Paper.  This document introduces TrustNote’s background, technical characteristics, and user scenarios, it will be updated by the TrustNote Development Team from time to time to reflect evolving the advancements in design and implementation process.  For the latest information about technical white papers, software releases and technical support for developer community, please visit our official website at <a href="www.trustnote.org" target="_blank" rel="external">www.trustnote.org</a>.</p>

<b>Contact Us</b>
<ul>
<li><p>Business Enquiries:  <a href="foundation@trustnote.org" target="_blank" rel="external">foundation@trustnote.org</a></p></li>
<li><p>Technical Support:  <a href="community@trustnote.org" target="_blank" rel="external">community@trustnote.org</a></p></li>
</ul>

<b>Disclaimer</b>
<p><!--justify-->TrustNote Institute of Technology hereby declare that: The current package is experimental and a work-in-progress, and you are using TrustNote at your own risk.  TrustNote also declares that we might change (add/remove packages) without informing the users.  In addition, because of the existence of “private equity” scams targeting crypto-currency investors, TrustNote hereby declare that participation in crypto-currency investment through unauthorized trading channels should always take precautionary measures against such risks.  Neither TrustNote Institute of Technology nor the TrustNote Development Team take responsibility for any consequences of investments via unauthorized trading channels.  Finally, we declare that, TrustNote White paper can be only accessed from:</P>
<ul>
<li><p><a href="https://github.com/trustnote/document" target="_blank" rel="external">https://github.com/trustnote/document</a></p></li>
<li><p><a href="https://trustnote.org/" target="_blank" rel="external">https://trustnote.org/</a></p></li>
</ul>
<p>We do not guarantee the faulty or misleading data available in documents downloaded from any other website rather than two official websites introduced above.</P>

<p><b>© 2018 TrustNote Institute of Technology. All rights reserved.</b></p>

</font>
</div>

------

<div align="justify">

<font face="cambria" size="3">
  
<b>Abstract</b>
<p>Today’s blockchain technologies face many challenges such as network congestion, high transaction fees, and long transaction confirmation delay.  TrustNote seeks to address these problems by building the world-leading public Directed Acyclic Graph (DAG) ledger which is minable, capable of handling high concurrent transactions yet still maintain quick transaction confirmation.  TrustNote is focused on creating an easy-to-use, decentralized, low-level digital token blockchain that leverages declarative Smart Contracts with enhanced expression capability, while empowering users to create and publish digital tokens without having to write complex Smart Contracts.  TrustNote has an extensible wallet that provides security and rich API interfaces for digital tokens, blockchain games and social networks, which allowing new innovative ideas to run smoothly on the blockchain network and making user friendly blockchain applications accessible to everyone.  TrustNote has an innovative two-tier consensus mechanism and the TrustME consensus algorithms.  These algorithms are working by selecting a number of Super Nodes periodically to act as attestation authorities which they receive mining rewards according to amount of their validated attestations.</p>

</font>
</div>

------

<div align="left">

<font face="cambria" size="3">

<b>Contents</b>
<ul>
  <li><a href="#BACKGROUND">BACKGROUND</a></li>
  <li><a href="#WHAT-IS-TRUSTNOTE">WHAT IS TRUSTNOTE</a></li>
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
















</html>
