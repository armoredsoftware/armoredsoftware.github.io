---
layout: blog
categories: blog
title: Demo 1 Complete
---
Today we did our first internal demonstration of an ArmoredSoftware
attestation among two virtual machines.  Demo 1 implemented an
exceptionally naive appraisal whose intent was shaking out
infrastructure issues including cryptography functions and 
communication.  The demo uses a traditional asymmetric key, *k*,
rather than an AIK or EK for signing and assumes the appraiser has a
public key for the target’s TPM. 

1. Appraiser sends a request *<d,n>* to an attestation agent for PCRs
	* *d* - desired PCRs
	* *n* - nonce
1. Attestation agent creates a quote *sign{q,n}{k}* signed with a
   traditional asymmetric key, *k*
1. Attestation returns the quote to the appraiser
1. Appraiser checks the returned evidence
	* checks the signature
	* checks the nonce
	* checks PCR values

Here's what we learned:

1. Communication among VMs with `vchan` through a Haskell interface is
   working for us. Some issues remain concerning communcating large
   data objects, but we have what we need to move forward.
1. Static IPs are still a problem in our cloud configuration.
1. Data is transmitted over the control network rather than the data
   network.  This is an easy fix.
1. We need to address key and ID management after Demo 2.

We're now off and running for Demo 2 where we will add quite a bit
including protocol selection and execution, interaction with the
measurer, and complex data requests.


