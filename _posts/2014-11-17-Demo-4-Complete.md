---
layout: blog
categories: blog
title: Demo 4 Complete
---
Demo 4, our last demonstration for our first contract year, is
complete and successful.  This demonstration extends previous demos by
including explicit certification of the \\(AIK\\) by an external
certificate authority.

1. Attestation agent takes ownership of its vTPM
1. Appraiser sends a request \\(\langle D,n\rangle\\) to an
   attestation agent for PCRs
	* \\(D=[d_0,d_1,...,d_n]\\) - desire evidence
	* \\(n\\) - nonce
1. Attestation agent selects a protocol based on \\(D\\)
1. Attestation agent executes the protocol
	* Creates an \\(AIK\\) for signing a quote
	* Requests \\(AIK\\) authentication by a certificate authority
	* Receives \\(\\{CAcert\\}\_{k}\\) and \\(\\{k\\}\_{EK}\\) where
      \\(CAcert\\) certifies \\(AIK\\)
	* Decrypts \\(k\\) and uses it to decrypt \\(CAcert\\)
	* depricated - Receives and decrypts \\(\\{[AIK]_{CA^{-1}}\\}\_{EK}\\)
	* Gathers evidence makes calles to the measurer to gather \\(E\\)
	* Receives \\(E\\)
	* Creates an evidence package, \\(\\{\langle E,n\rangle\\}\\)
	* Creates a quote \\(q=\langle\\#\langle
      E,n,CAcert\rangle,PCR\rangle_{AIK^{-1}}\\).  Note the hash in
      the quote guarantees integrity of none, the CA certification,
      and evidence. 
1. Attestation returns the quote, evidence and CA certification
1. Appraiser checks the returned quote and evidence
	* Checks \\(AIK\\) authenticity using \\(CA\\) public key
	* Checks the signature of the quote using \\(AIK\\)
	* Recreates and checks the PCR composite
	* Checks the evidence package using \\(\\#\langle E,n\rangle\\)
	* checks \\(n\\)
	* checks \\(E=[e_0,e_1,...,e_n]\\)

All data exchanged among the appraiser, attestation manager, measurer,
and Privacy CA is in the form of standard JSON structures.  This
supports integration with other trusted computing components outside
the ArmoredSoftware ecosystem.

In addition to executing successful runs, the demo checks a number of
cases that should cause the protocol to fail or give bad results.
These include: 

1. Bad measurement values
2. Bad PCR values
3. Bad nonce
4. Uncertified or improperly certified \\(AIK\\)
5. Bad quote or quote signature

The demo is quite close to being a complete and valid attestation
protocol execution.  Following are remaining limitations: 

1. The Privacy CA is currently simulated, but can easy be replaced by an
   existing operational Privacy CA.
1. The vTPM is currently a stand-alone Berlios TPM emulator

Note that the measurer is now being called explicitly and is no longer
simulated.
