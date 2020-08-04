---
title: Blockchain Commons Security Services Terms
edition: Version 1.0.0
blanks: {}
signatures: []
---

# Overview

This document spells out terms under which _Security Firm_ will prepare and deliver one or more written **Reports** analyzing the security of technical systems for _Client_.  _Reports_ may include listings, patches, or other computer source code.

# Work Order

These terms apply to work done under any **Work Order** that references them.  Each _Work Order_, together with these terms, makes up an agreement between _Client_ and _Security Firm_.

# NDA

These terms expect _Security Firm_ and _Client_ to enter into a separate **Nondisclosure Agreement** restricting disclosure of confidential information from both sides.

# Security Firm's Obligations

## Send a W-9

Before beginning any work, _Security Firm_ agrees to send _Client_ a complete United States Internal Revenue Service Form W-9 or W-8BEN.

## Do the Work

_Security Firm_ agrees to perform the services on the _Work Order_ with the care, skill, and knowledge of an expert in the digital security industry.  However, _Security Firm_ cannot and does not guarantee to identify every real or potential _Vulnerability_ in every relevant _System_.  No one can.

## Track Time

If the _Work Order_ set fees at an hourly rate, _Security Firm_ agrees to track time spent working in fairly rounded, quarter-hour increments.

## Send Bills

_Security Firm_ agrees to bill _Client_ for each payment due under the agreement according to _Client_'s billing instructions on the _Work Order_.

## Cover General Expenses

_Security Firm_ agrees to pay for all equipment, licenses, and services needed to develop open software, generally. For example, _Security Firm_ agrees to provide their own computer, operating system, development environment, and Internet access.

## Return Loaned Equipment and Materials

After work is done under the agreement, and at any time on _Client_'s request, _Security Firm_ agrees to promptly return any equipment or materials _Client_ loaned for work under the agreement.

## Manage Subcontractors

If the _Work Order_ allows _Security Firm_ to use subcontractors:

- _Security Firm_ agrees to use only subcontractors that have all the expertise needed to meet the standards in [Do the Work](#do-the-work).

- If _Client_'s technical representative objects to a particular subcontractor, _Security Firm_ agrees to stop using that subcontractor to do work under the agreement.

- _Security Firm_ agrees to sign a contract with each subcontractor requiring them to abide by these terms and the _Nondisclosure Agreement_.

- _Security Firm_ agrees to send _Client_ a copy of any contract with a subcontractor promptly on request.

## Appoint Replacement Technical Representatives

_Security Firm_ agrees to appoint a replacement technical representative, preapproved by _Client_, if the current one leaves or becomes unavailable.

## Vulnerability Reporting

### Process in General

Subject to [Advice of Counsel](#advice-of-counsel), _Security Firm_ agrees to follow this process for any _Vulnerability_ that _Security Firm_, any _Security Firm_'s employee, or any _Security Firm_ subcontractor discovers during work under the agreement:

- _Security Firm_ will identify the maintainer of the _System_ that is vulnerable.  The maintainer may be _Client_, an open source software project, a standards body, or another kind of organization.

- _Security Firm_ will determine whether the maintainer has published a process for reporting the _Vulnerability_.

- If _Security Firm_ determines that the maintainer has a process, and that the process meets [Minimum Standards](#minimum-standards), _Security Firm_ will report the _Vulnerability_ according to that process.

- Otherwise, _Security Firm_ will report the _Vulnerability_ according to [Fallback Disclosure Policy](#fallback-disclosure-policy).

### Advice of Counsel

_Security Firm_ may seek legal advice about the legal risks of reporting or publishing a _Vulnerability_.  If legal counsel recommends against reporting or publication, _Security Firm_ may follow that advice.  _Security Firm_ agrees to notify _Client_ that there are legal concerns about reporting or publishing a _Vulnerability_ when doing so won't itself create significant legal risk.

### Minimum Standards

#### Requirements

A disclosure process must:

- specify a secure means of communicating _Vulnerability_ information

- allow _Security Firm_ to publish of the _Vulnerability_ after a definite period of time

#### Prohibitions

A disclosure process must not:

- require _Security Firm_ to pay any fee or incur any significant expense in order to report

- require _Security Firm_ to agree to any contract, or otherwise take on legal obligations, in order to report

- impose an onerous process that requires an inordinate amount of time

- make _Security Firm_ responsible for engineering a patch

- reserve or establish any right to bring civil, criminal, or any other kinds of legal claims against _Security Firm_

- require _Security Firm_ to provide extra information that might be used to incriminate or sue _Security Firm_

- require _Security Firm_ to waive any privacy right, confidential treatment, or privileges against disclosure

### Fallback Disclosure Policy

- _Security Firm_ will determine whether the vulnerable _System_ has been made _Generally Available_.  If _Client_ is the maintainer, _Security Firm_ will ask _Client_ technical staff to confirm.

- If the _System_ has not been made _Generally Available_, _Security Firm_ will report the _Vulnerability_ to the maintainer immediately, but not publish it.

- Otherwise, _Security Firm_ will report each _Vulnerability_ to the maintainer of the vulnerable _System_ immediately and publish each _Vulnerability_ to the security community more broadly after ninety calendar days.

- When ninety calendar days end on a weekend or US holiday, _Security Firm_ will wait until the next regular workday.

- If the maintainer notifies _Security Firm_ that the maintainer will release a security patch within fourteen days after ninety days would run out, _Security Firm_ will wait until the patch is released or the extra fourteen days run out.

- _Security Firm_ will publish a _Zero-Day_ after seven days, rather than ninety.  _Security Firm_ will not extend the publication timeline for a _Zero-Day_ for holidays or late patch releases.

- In exceptional circumstances, _Security Firm_ may commit to publishing earlier or later, or change a timeline in light of new information.  Whenever possible, _Security Firm_ will immediately notify the maintainer of any changes.

### Confidential Reporting

- Information that _Security Firm_ needs to report a _Vulnerability_ so that a maintainer can reproduce, validate, and patch it is not confidential information of _Client_ under the _Nondisclosure Agreement_.  By reporting the _Vulnerability_, _Security Firm_ will not breach that agreement.

- However, if other information about the circumstances in which the _Vulnerability_ was discovered is confidential information of _Client_ under that agreement, it remains so.  For example, if _Security Firm_ has agreed not to disclose the fact of the working relationship between _Security Firm_ and _Client_, the fact that _Client_ is using or considering the vulnerable _System_, or these terms themselves, these terms do not change those commitments.

## Waive Bounties

_Security Firm_ agrees to waive any bounty for any _Vulnerability_ for which _Client_ offers a bounty, and to require its employees and subcontractors to do so. However, _Security Firm_, its employees, and its subcontractors may claim the bounty offered by anyone else for any _Vulnerability_ they discover during work under the agreement.

## Terminology

- **Vulnerability** means a weakness in a _System_ that attackers can exploit to do things the _System_ wasn't designed to allow.

- **Zero-Day** means a _Vulnerability_ that, as far as _Security Firm_ can tell, hasn't already been discovered, remains unpatched, and affects a system in use.

- **System** means a computer software project, computer system, or security design.

- **Generally Available** means made available for licensing or use outside its maintainer's corporate group.

# Client's Obligations

## Pay Security Firm's Fee

_Client_ agrees to pay _Security Firm_ the fees on the _Work Order_.

## Follow Payment Instructions

_Client_ agrees to make all payments to _Security Firm_ under the agreement denominated in the currency and according to the payment instructions agreed on the _Work Order_.  _Client_ will not increase or decrease payments under the agreement according to, or to offset, changes in the market price of the denominating currency.

## Pay on Time

_Client_ agrees to pay all correctly billed amounts on each bill within seven calendar days of receipt.  If _Client_ does not pay a bill on time, _Security Firm_ can notify _Client_ and stop work until all overdue bills are paid.  Stopping work in this way postpones all deadlines for as long as work stops.

## Cover Extraordinary Expenses

If services on the _Work Order_ require extraordinary equipment, materials, licenses, services or other major expenses, then _Client_ agrees to cover the costs to the _Security Firm_ that _Client_'s technical representative preapproves in writing. For example, _Client_ may approve the costs of proprietary software licenses, testing hardware, technical standards, and specific online services that the services require _Security Firm_ to use. If _Client_ requires _Security Firm_ to use and return specific equipment or materials, _Client_ agrees to pay the costs of packaging and shipping, both ways. If _Client_ cannot pay an approved extraordinary expense directly, _Client_ agrees to advance _Security Firm_ the cost.

## Clarify Requirements

_Client_ agrees to respond promptly to _Security Firm_ requests to clarify the objectives or particulars of services on the _Work Order_.

# Intellectual Property

## Purposes of Intellectual Property Terms

[Intellectual Property](#intellectual-property) gives _Client_ permission to copy, change, and build on _Security Firm_'s _Reports_, while also allowing to develop and use boilerplate, stock explanations, and other building blocks for future reports, for _Client_ and other customers.

## Security Firm Licenses Reports

On payment of fees owed:

- Subject to [Confidentiality](#confidentiality), _Security Firm_ licenses _Client_ to do everything with its _Reports_ that would otherwise infringe _Security Firm_'s copyright in them.

- Subject to [Confidentiality](#confidentiality), _Security Firm_ licenses _Client_ to do everything with its _Reports_ that would otherwise infringe any patent claims _Security Firm_ can license or becomes able to license.

- These licenses continue forever, cannot be revoked, impose no royalty or other charge, and allow _Client_ to sublicense.

# Confidentiality

## Report Texts

The verbatim content of _Security Firm_'s _Reports_, in whole or any substantial part, are the confidential information of _Security Firm_ under the _Nondisclosure Agreement_.  _Client_ agrees not to publish or otherwise distribute significant verbatim parts of the _Reports_ without _Security Firm_'s advance, written permission.

## Report Findings

The contents of _Security Firm_'s _Reports_, such as _Security Firm_'s findings, assessments, and conclusions, are the confidential information of _Client_ under the _Nondisclosure Agreement_.  _Client_ may keep that information confidential or disclose it, as it chooses.

## Report Authorship

The fact that _Security Firm_, as well as each employee, contactor, or other personal affiliated with _Security Firm_, were involved in producing the _Reports_ or their content is confidential information of _Security Firm_.

## Promotion

Each side agrees not to use the other's name or logo, or the name of any employee, contractor, or other person affiliated with them, to promote any product or service without the other side's advance, written permission.

# Working Relationship

## Independence

_Security Firm_ will decide when, where, and how to work, with the discretion of an independent contractor. _Security Firm_ will not have any power to enter agreements or take other legal action on _Client_'s behalf.

## Personnel

_Security Firm_ can use employees to do any work.  If the _Work Order_ allows, _Security Firm_ can also use contractor personnel to do any work. All personnel will be employees and contractors of _Security Firm_, not _Client_.

## No Benefits

Neither _Security Firm_ nor any _Security Firm_ personnel will receive any employee benefits from _Client_.

## Compliance

Both sides will do their respective parts for tax, labor, employment, and immigration law compliance, consistent with their independent-contractor relationship.

## Compliance Indemnity

_Security Firm_ will pay any losses that _Client_ pays or becomes legally responsible to pay, including expenses of defending against any legal claim, related to _Security Firm_'s failure under [Compliance](#compliance) for _Security Firm_ or any _Security Firm_ personnel. _Client_ will promptly notify _Security Firm_ by e-mail whenever it anticipates possible losses that _Security Firm_ might have to pay. If _Client_ fails to notify _Security Firm_ promptly, _Security Firm_ will not pay _Client_ losses that _Security Firm_ could have reduced or defended against if _Client_ had notified _Security Firm_ promptly.

# General Contract Terms

## Governing Law

Wyoming law will govern all rights and duties under the agreement.

## No CISG

The United Nations Convention on Contracts for the International Sale of Goods will not apply to the agreement.

## No UCITA

As far as the law allows, the Uniform Computer Information Transactions Act will not apply to the agreement.

## Whole Agreement

Both sides intend the _Work Order_, these terms, and their _Nondisclosure Agreement_ as the final, complete, and only expression of their terms about _Security Firm_'s work under the _Work Order_.

## Assignment

_Security Firm_ cannot assign any right under the agreement without _Client_'s prior, written, permission. _Client_ can assign the agreement, as a whole, to another business entity that acquires its stock or substantially all its assets, or to a new business entity set up to change its legal form or jurisdiction. Any attempt to assign rights under the agreement against its terms has no legal effect.

## Delegation

Neither side can delegate any duty under the agreement. Any attempt to delegate has no legal effect.

## Unenforceable Terms

If a court decides that any part of the agreement cannot be enforced, for any reason, the rest of the agreement will continue to apply.

## Enforcement

Only _Security Firm_ and _Client_ can enforce the agreement.

## Lawsuits

**Lawsuits** means any legal actions or claims related to the agreement, ignoring the historical distinction between actions "in law" and "in equity".

## Courts

Both sides agree to bring all _Lawsuits_ related to the agreement only in the federal or state courts in Cheyenne, Wyoming.  Both sides consent to the exclusive jurisdiction of those courts, and waive any objection to hearing _Lawsuits_ there.  Both sides can enforce judgments from those courts in other jurisdictions.

## English Rule

Each side agrees to pay the other side's attorney fees and costs if they lose in court.
