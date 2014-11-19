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
1. Appraiser sends a request \\(\langle D,n,PCRSelect\rangle\\) to an
   attestation agent for PCRs
	* \\(D=[d_0,d_1,...,d_n]\\) - desire evidence
	* \\(n\\) - nonce
	* \\(PCRSelect\\) - PCRs to include in the TPM quote
1. Attestation agent selects a protocol based on \\(D\\)
1. Attestation agent executes the selected protocol:
	* Creates an \\(AIK\\) for signing a quote
	* Requests \\(AIK\\) authentication by a certificate authority
	* Receives \\(\\{CAcert,AIK\\}\_{k}\\) and
	  \\(\\{k,AIKdigest\\}\_{EK}\\) where 
	  * \\(\\{CAcert,AIK\\}\\) certifies the \\(AIK\\)
	  * \\(CAcert\\) is \\([AIK]_{CA^{-1}}\\), the \\(AIK\\) signed by
      the certificate authority
	  * \\(AIKdigest\\) is \\(\\#AIK\\), the hash of public \\(AIK\\)
	* Decrypts \\(k\\) and uses it to decrypt \\(\\{CAcert,AIK\\}\\)
	* Gathers evidence makes calls to the measurer based on the
      requst, \\(D\\), to gather \\(E\\)
	* Receives \\(E\\)
	* Creates an evidence package, \\(\\{\langle E,n\rangle\\}\\)
	* Creates a quote \\(q=\langle\\#\langle
	  E,n,CAcert\rangle,PCR\rangle_{AIK^{-1}}\\).
	  * \\(\\#\langle E,n,CAcert\rangle\\) guarantees integrity of the
      evidence, the nonce, and the CA certification
	  * \\(PCR\\) is a PCR composite built using \\(PCRSelect\\) sent
        with the request.
1. Attestation returns the quote, evidence and CA certification
1. Appraiser checks the returned quote and evidence
	* Checks integrity of evidence, nonce and \\(CACert\\) using
      \\(\\#\langle E,n,CACert\rangle\\) from the quote
	* Checks \\([AIK]_{CA^{-1}}\\) authenticity using \\(CA\\) public key
	* Checks the signature of the quote using the now certified \\(AIK\\)
	* Recreates and checks the PCR composite
	* checks \\(n\\) against the original nonce sent to the
      attestation manager
	* checks \\(E=[e_0,e_1,...,e_n]\\) against known good values

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
