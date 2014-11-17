---
layout: blog
categories: blog
title: Demo 4 Complete
---
Demo 4, our last demonstration for our first contract year, is complete and successful.  This demonstration extends previous demos by including explicit certification of the \\(AIK\\) by an external certificate authority. 

1. Attestation agent takes ownership of its vTPM
1. Appraiser sends a request \\(\langle D,n\rangle\\) to an
   attestation agent for PCRs
	* \\(D=[d_0,d_1,...,d_n]\\) - desire evidence
	* \\(n\\) - nonce
1. Attestation agent selects a protocol based on \\(D\\)
1. Attestation agent executes the protocol
	* Creates an \\(AIK\\) for signing a quote
	* Requests \\(AIK\\) authentication by a certificate authority
	* Receives and decrypts \\( \{[AIK]_{CA^{-1}}\}_{EK} \\)
	* Gathers evidence, \\(E\\), from application
	* Creates an evidence package, \\(\{\langle E,n\rangle\}_{AIK^{-1}}\\)
	* Creates a quote \\(q=\langle\\#\langle E,n\rangle,PCR\rangle_{AIK^{-1}}\\)
1. Attestation returns the quote, evidence and CA authentication using JSON exchange structures
1. Appraiser checks the returned quote and evidence
	* Checks \\(AIK\\) authenticity using \\(CA\\) public key
	* Checks the signature of the quote using \\(AIK\\)
	* Recreates and checks the PCR composite
	* Checks the evidence package using \\(\\#\langle E,n\rangle\\)
	* checks \\(n\\)
	* checks \\(E=[e_0,e_1,...,e_n]\\)

In addition to executing successful runs, the demo checks a number of cases that should cause the protocol to fail or give bad results.  These include:

1. Bad measurement values
2. Bad PCR values
3. Bad nonce
4. Uncertified or improperly certified \\(AIK\\)
5. Bad quote or quote signature

The demo is quite close to being a complete and valid attestation protocol execution.  Following are remaining limitations:

1. The CA is currently simulated, but can easy be replaced by an existing operational CA.
1. The vTPM is currently a stand-alone Berlios TPM emulator
1. The measurer is currently being simulated rather than called
   explicitly

