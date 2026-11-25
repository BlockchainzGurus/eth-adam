# Evaluation Criterias

## Risk assessment
- i* diagrams
	- SD/SR Supply Chain Roles Without System
	- SD/SR Supply Chain Roles Plus System
	- SD/SR System and Attackers (Internal Attacker, External Attacker, Clumsy User) with Attack Trees
- DUAL-STRIDE
	- system actor assets only
	- references to CAPEC and/or ATT&CK
- Abuse/misuse houses
	- for each asset in STRIDE and for each type of attacker/clumsy actor
## Secure Design
- Architecture
	- use distributed, redundant and diverse architectures and justify their use
	- use architectures based on monitoring, isolation and obfuscation and justify their use
- Asset design
	- use OWASP and/or Saltzer & Schroeder and/or Sommerville guidelines
	- Markov Chain modeling of a unit and verify a Safety property and a Guarantee/Response property using PRISM
- Technological choices
	- motivate technological choices in light of the analysis of resistance, ambiguity and survival
	- motivate technological choices in light of the analysis of weaknesses
## Secure Programming
- synthesize a runtime enforcement monitor of a Safety property and a Guarantee/Response property
- use the Sommerville guidelines
- use OpenZeppelin library
- use one of the following encoding standards for Solidity
	- https://swcregistry.io/ (although it is no longer updated)
	- https://entethalliance.org/specs/ethtrust-sl/v2/ (RECOMMENDED - new security reference portal in Solidity)
	- https://github.com/ComposableSecurity/SCSVS - https://scsfg.io/ - https://docs.soliditylang.org/en/latest/style-guide.html (other reference sites)
- use Remix's static analysis tools: Solidity Analyzer and Solhint
- test all code using Hyperledger BESU as the private blockchain
## Deployment and management
- use GitHub or GitLab
- in the documentation indicate how to install and use the code
- create installation scripts (for MacOS or Linux)
