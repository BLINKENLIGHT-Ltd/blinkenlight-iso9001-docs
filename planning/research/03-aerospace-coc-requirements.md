# Certificate of Conformity — aerospace requirements

Research note, 2026-07-20. Feeds the InvenTree Certificate of Conformity (CoC)
template and the Aalto HAPS engagements. Not part of the QMS.

## Summary

AS9100D does **not** prescribe a CoC format or field list. The obligation to
issue one is a customer flow-down. The best available primary source for
BLINKENLIGHT's position is Airbus' own published requirement A1505, which gives
a mandatory 13-field list and a form of words. BLINKENLIGHT must **not** issue
anything resembling an EASA Form 1.

## 1. What the standard actually requires

AS9100D prescribes no CoC format. Clause text below is verbatim from the copy
of AS9100D held in the repository root. Text shown **bold** in the standard is
an aerospace addition to the underlying ISO 9001:2015 wording.

The requirement chain is:

**Clause 8.6 (Release of Products and Services)**

> The release of products and services to the customer shall not proceed until
> the planned arrangements have been satisfactorily completed, unless otherwise
> approved by a relevant authority and, as applicable, by the customer.
>
> The organization shall retain documented information on the release of
> products and services. The documented information shall include:
> a. evidence of conformity with the acceptance criteria;
> b. traceability to the person(s) authorizing the release.
>
> **The organization shall ensure that all documented information required to
> accompany the products and services are present at delivery.**

That last sentence is the hook for the CoC — but *what* documentation is
required comes from the contract, not the standard. Note also (b): release
records must be traceable to the authorising person, which is what REG-07
(Authorised Signatory Register) exists to support.

**Clause 8.5.2 (Identification and Traceability)**

> **The organization shall maintain the identification of the configuration of
> the products and services in order to identify any differences between the
> actual configuration and the required configuration.**
>
> When acceptance authority media are used (e.g., stamps, electronic
> signatures, passwords), the organization shall establish controls for the
> media.

The configuration sentence is an aerospace addition and is the requirement
behind holding each drawing issue as a separate part revision, so that a unit
remains associated with the configuration it was built to. The acceptance
authority media sentence is the requirement behind REG-07 §3 (control of
signature).

The clause Note lists traceability examples — not requirements — including
"for an assembly, the ability to trace its components to the assembly and then
to the next higher assembly" and "for a product, a sequential record of its
production (manufacture, assembly, inspection/verification) to be retrievable".

**Clause 7.5.3.2** lists the activities to be addressed for control of
documented information: "(a) distribution, access, retrieval, and use;
(b) storage and preservation, including preservation of legibility; (c) control
of changes; **(d) retention and disposition**; (e) prevention of the unintended
use of obsolete documented information". No period is specified anywhere in the
standard. Note (a) requires retrieval to be *addressed*, not that a retrieval
deadline be committed to.

The same clause closes with:

> Documented information retained as evidence of conformity shall be protected
> from unintended alterations.

This bears directly on generating a CoC from live data: a certificate
regenerated on demand is not protected from unintended alteration, since a
later change to a part revision or batch code would yield a different
certificate for the same shipment. The generated PDF must be archived as the
record — in InvenTree, via `attach_to_model` on the report template.

## 2. AS9163 / EN 9163:2023

"Aerospace series — Certificate of Conformity Requirements" (IAQG, issued
Dec 2022; EN version 2023). Contains a CoC template and completion
instructions at Annexes B and C.

Application is **mandatory only when quoted by the customer as a contractual
requirement**; otherwise recommended. It is *not* invoked by AS9100D.

AS9163 explicitly **excludes** regulatory Authorised Release Certificates
(EASA Form 1, FAA 8130-3, CAAC Form 038) from its scope — those are governed by
the authority that granted the Production Approval.

- https://iaqg.org/standard/9163-aerospace-series-certificate-of-conformance-requirements/
- https://www.sae.org/standards/as9163-aerospace-series-certificate-conformity-requirements

Structure: clause 4 "minimum information required", clause 5 additional
completion requirements, Annex B (informative) template, Annex C (informative)
completion instructions.

**Version note:** the "DIN EN 9163:2025-07" listing that appears in searches is
the German-language adoption of EN **2023**. There is no 2025 content revision.
EN 9163:2023 is current.

**Not obtained** — paywalled (SAE/ANSI/BSI/DIN/AFNOR, ~£70–100); all preview
routes return HTTP 403. Every field list circulating in search summaries is
secondary paraphrase. Buy BS EN 9163:2023 if Aalto invoke it contractually.

Also worth registering for: the IAQG Supply Chain Management Handbook
Certificate of Conformance tool (free but login-gated), the best free guidance
available. https://scmh.iaqg.org/tools/scmh/

## 3. Airbus A1505 — the mandatory field list

Source: *Airbus general quality requirements for standalone Purchase Order*,
release date 10 October 2024, requirement **A1505 / 05.5013.D §3.2.1
"Certificate of Conformity"**.

> (a) The Supplier shall release all its Products with a Certificate of
> Conformity (CoC).
> (b) The Supplier shall ensure that the CoC: (1) is written in English (or is
> bilingual), (2) contains at least the following information:

| # | Field |
|---|---|
| i | CoC number |
| ii | Supplier name and address **of the manufacturing site** |
| iii | CAGE code if relevant |
| iv | Purchase order |
| v | Part number and Product designation |
| vi | Serial number or batch number if relevant |
| vii | Reference number to an original CoC (or equivalent) from OEM where applicable |
| viii | Quantity and unit as relevant |
| ix | Description and status of work performed, where applicable |
| x | Conformity details or remarks (e.g. reference to non-conformities affecting the Product if any, expiry date, life limitation, and any other conformity elements requested by the Purchaser) |
| xi | Statement of conformity (or equivalent wording): *"We hereby declare that the delivered Product(s) comply with the applicable requirements, specifications, drawings, regulations, standards and have been successfully tested and/or verified"* |
| xii | Authorized signature and name (function also recommended) or individual, unambiguous and traceable signatory code |
| xiii | Date |

https://www.airbus.com/sites/g/files/jlcbta136/files/2023-10/Airbus%20general%20quality%20requirements%20for%20standalone%20Purchase%20Order.pdf

**Caveat:** this is the generic Airbus PO document. Aalto's own flow-down
governs over it and has not been examined — check the purchase order and any
Aalto supplier quality requirements document held as customer property.

## 4. UK Tier-2 comparator — CAV Systems

*CoC Requirements Issue 3*, 22 April 2024. Publicly published, aerospace, close
to BLINKENLIGHT's position in the chain.

Requires: unique serial number, supplier name/address, order number, part
number, specification, description of goods (including material condition and
manufacture/cure dates), serial numbers, batch numbers, quantity, and this
certifying statement for subcontractors and manufacturers:

> "Certified that the whole of the supplies detailed hereon have been
> manufactured, inspected, tested and unless otherwise stated conform in all
> respects to the relevant specifications, drawings, and contract/order"

§2.1 additionally requires **endorsement** on the CoC for: concession number
granted; non-conforming items subject to further work after delivery; shortages
or work outstanding; references to accompanying documents (e.g. First Article
Inspection reports); free-issue material batch numbers; and reject-note number
when re-releasing after rejection.

§4 requires release certificates to be signed by the Quality Manager or an
authorised nominee, and that **authorised signatories be listed in a controlled
document**. Cheap to implement and commonly missed by small suppliers.

https://www.cav-systems.com/documents/supplier-c-of-c-requirements-issue-3/

## 5. Elements with no authoritative CoC sourcing

Real controls, but **no source found making them CoC content**. Include only if
the customer asks, and do not present them as standard-driven:

- Counterfeit parts statement (AS5553/AS6174). The flow-down obligation is real
  and common in US-prime templates; the Airbus CoC clause does not list it.
- Sub-tier special process approval listing. Airbus control this via the
  Qualified Special Process List and Nadcap — a supplier-approval control, not
  a CoC field.
- Calibration traceability statement. A separate QMS requirement.
- "No unauthorised repair or rework". The underlying MRB restriction is real
  (suppliers cannot disposition "use-as-is" or "repair" without customer
  approval) but the phrase appears in no primary source found. Note the
  distinction: repair leaves a permanent deviation and needs approval; rework
  restores conformity and is often permitted. **Do not write a blanket "no
  rework" statement that cannot be honoured.**
- Record retention period stated on the CoC face. Supplier convention.
- Page X of Y. General document-control practice.

Country of origin is common but customer-specific, and absent from the Airbus
CoC clause. Cheap to include; do not claim it is standard-driven.

## 5a. Consensus across eleven primes

Survey of public supplier quality manuals (Lockheed Martin, Boeing, Rolls-Royce,
Leonardo, Collins, BAE ×2, Thales DSI, Safran ×5 divisions, Parker Meggitt,
GKN). Count = number requiring the element **on the CoC**:

| Element | Count | Note |
|---|---|---|
| Concession / deviation / non-conformance reference | **8 / 11** | Strongest consensus after the core fields |
| Country of origin | 4 / 11 | Meggitt requires it on the commercial invoice, not the CoC |
| Sub-tier special process approval listing | 2 / 11 | GKN QC2040, BAE ES 00-315. Airbus requires qualified sources, not a CoC listing |
| Counterfeit parts statement | 1 / 11 | Parker Meggitt QA-016 Q34, and it permits a separate certificate. Genuinely conventional on **distributor** CoCs (AS9120/AS6081), which does not transfer to a manufacturer |
| "No unauthorised repair or rework" | 1 / 11 | BAE ES 00-315 cl. 100 only |
| Calibration traceability statement | **0 / 11** | Always a separate Certificate of Calibration |
| Page X of Y | **0 / 11** | No sourcing found in any prime's public literature |

Additional near-universal fields confirmed by the survey: purchase order
**line item** (not just PO number), and part number **with revision/issue**.

**Airbus Canada QMS-09-01 §8.6.2** adds configuration identification — part
number, **dash number and MOD status** to which the product was built — and
accepts stamp/initials or electronic signature where the supplier has
documented procedures controlling acceptance authority media (cl. 8.5.2).
https://www.airbus.com/sites/g/files/jlcbta136/files/2024-01/QMS-09-01-A220-Suppliers-Quality-Requirements.pdf

Note: **"ASQR" is not a current Airbus-wide document ID.** ASQR4.6 was the
legacy Airbus Canada designation, superseded by QMS-09-01. The governing manual
depends on which Airbus entity issued the purchase order.

Keyword counts across the Airbus general quality requirements document:
counterfeit 0, country of origin 0, RoHS 0, REACH 0, ITAR 0, export 0,
"page 1 of" 0, 9163 0.

## 6. Record retention

**Airbus A1501 / 01.0041.D §3.1.5** ("Data and documentation management —
Records") flows down:

> (1) those supporting the demonstration that an Aircraft or an Item was
> manufactured in a conforming condition and archive them for a minimum of
> **5 years from the release of the Product**,
> (2) those needed by the organization responsible for the aircraft continuing
> airworthiness to establish the airworthiness status of an Aircraft or an Item
> and archive them **throughout its operational life**,
> (3) all details of maintenance work carried out for the last three years.

Clause (b) requires electronic archiving in an independent physical space
protected from loss, modification and unauthorised access.

The commonly cited "20–40 years" / "life of the aircraft" figures are
**unsourced** in any primary document found; they derive from continuing-
airworthiness obligations and individual prime contracts, not from AS9100D,
which sets no period.

### Comparison across primes

| Organisation | Period | **Trigger** |
|---|---|---|
| **Airbus** 01.0041.D §3.1.5 | **5 years** | from **release of the product** |
| Airbus — airworthiness status records | **operational life** | of aircraft/item |
| Lockheed Martin AppQX §1.6.B | 3 years (7 special process) | after **final payment** of PO |
| Boeing D6-87282 SQ02 | 10 years | from **shipment date** |
| BAE Electronic Systems 00-315 | 10 years | after completion of PO |
| BAE Platforms & Services SQAM §8.3 | 7 years (10 Phoenix) | after order completion |
| Collins §5.11.1 | 10 / **40 years** safety-critical | after date of manufacture |
| Leonardo QRS-01 §11.5 | **life of product + 10** | product withdrawal |
| Rolls-Royce SABRe 4 App A | Cat A 10 yrs after **type withdrawn from use**; Cat B 6 yrs | type withdrawal |
| Thales DSI OT16-003 cl. AJ | 10 years | none stated (document ambiguity) |
| Safran EDA SQAM-000 §2.5.2.2 | 10 years + litigation hold | past end of contract |
| Parker Meggitt QA-016 Q5 | **10–50 years** (50 = product conformity) | from delivery |
| Meggitt MPRC-10 | 10 years, reserves "life of aircraft" | from publication |

**10 years is the floor almost everywhere.** The surprise is that Airbus itself
flows down only 5 years for general records — the demanding limb is
operational-life retention for anything establishing airworthiness status.

### The trigger matters more than the number

Six distinct trigger conventions appear above. "10 years" from shipment, from
final payment, from type withdrawal, and life-of-product-plus-10 are wildly
different actual durations. A retention procedure stating only a period is
incomplete.

Three things a procedure must handle beyond a number:

- **Trigger** — state what starts the clock. Product release is the cleanest
  for a manufacturer and matches Airbus.
- **Holds and overrides** — Meggitt reserves "life of the aircraft"; Safran EDA
  imposes a litigation hold suspending disposal indefinitely. Without a hold
  mechanism, a generous flat period still fails these clauses.
- **Access speed and disposal notice** — Collins requires retrieval within 48
  hours, Meggitt within 1 business day. Meggitt requires 90 days' notice before
  disposal; Collins forbids destruction without documented approval; Leonardo
  requires consultation.

Practical position: set the policy at the most stringent of contract, QMS
procedure and regulatory requirement, with an explicit hold mechanism.
Airworthiness-relevant records retained for operational life of the item or
transferred to the customer. Customer property remains returnable/destroyable
under QP-12 and is not overridden by retention. Personal data is minimised
under UK GDPR storage limitation rather than held for the full period.

## 7. EASA Form 1 — BLINKENLIGHT must not issue one

> "The EASA Form 1 is the Authorised Release Certificate released by a POA
> holder for stating that a product, a part, or a component was manufactured in
> accordance with approved/not approved design data."

Only a **Part 21 Subpart G Production Organisation Approval (POA)** holder may
issue it for new production. https://www.easa.europa.eu/en/faq/19466

Two further points:

- Without its own Design Organisation Approval or a documented 21.A.133(d)
  arrangement with the design approval holder, a 21G organisation cannot show
  conformity to approved design data and has no route to Form 1 even if
  approved.
- Where items are **not** delivered with an EASA Form 1, the supplier is treated
  as a **subcontractor working under the direct control of the POA holder's
  quality system**, and the POA holder remains responsible for verification.
  This is BLINKENLIGHT's model: ship on a company CoC; the POA holder issues
  the Form 1 if and when one is needed.

**Scope of the restriction.** There is no prohibition on a non-approved
supplier issuing a *certificate of conformity* — a CoC is a commercial /
manufacturer's document, not an airworthiness release. The restriction is
specifically on the **Authorised Release Certificate**. EASA 21.A.307(c)
expressly contemplates a manufacturer-issued document (for instance a
certificate of conformity) to identify a part and trace it to the original
manufacturer where Form 1 release is not applicable. Airbus Canada QMS-09-01
§8.6.3 states the relationship: an Authorised Release Certificate is provided
only where the supplier is a Production Approval Holder or equivalent, and
where an ARC is provided a CoC is not required.

Accordingly: do not use the words "Authorised Release Certificate", do not
reproduce the Form 1 block layout or its 13-block numbering, do not use a form
number resembling "Form 1" or "8130-3", and make no airworthiness, "approved
design" or "safe for installation / return to service" claim. Certify
conformity to the drawing, specification and purchase order — nothing more.

**FAA equivalent.** FAA Order 8130.21B restricts 8130-3 issue to FAA Aviation
Safety Inspectors, DMIRs, DAR-Fs, ODA units, and Production Approval Holders
with an FAA-approved quality system per 14 CFR 21.137(o). A supplier that is
not a PAH cannot issue one, and even a PAH's authority is bounded to articles
it manufactured. https://www.faa.gov/documentLibrary/media/Order/8130.21B.pdf

EASA's historical position is that competent authorities do not intend to
approve firms performing only subcontract work for main contractors, so
pursuing a POA is not the answer; operating cleanly as a subcontractor under
the prime's quality system is.

## 8. Further Airbus sources — not yet parsed

- Airbus Supplier Quality Requirements Manual —
  https://www.airbus.com/content/dam/channel-specific/website-/us/quality/Supplier%20Quality%20Reqmts%20Manual.pdf
- TT.GOV.D170.EN Generic Supply Chain and Quality Requirements —
  https://www.airbus.com/sites/g/files/jlcbta136/files/2022-09/TT.GOV_.D170.EN_2_0.pdf
- GKN Aerospace SQAR-104 (Airbus-specific Tier-1 flow-down; certification of
  conformance report must accompany each shipment; original test reports kept
  on file and traceable to end items delivered to Airbus) —
  https://www.gknaerospace.com/media/saha03uj/sqar-104_03182021.pdf
- Airbus Helicopters ER070 06-01 — described as fully incorporating CoC
  specifics and aligned to EN9100 section numbering; not fetched.

## Declared gaps

1. AS9163/EN 9163 full text not obtained (paywalled).
2. ~~AS9100D clause text not obtained verbatim.~~ Closed 2026-07-21 — quoted
   above from `planning/reference/AS9100D-2016.pdf`.
3. **Aalto's own flow-down not examined** — governs over the generic Airbus PO
   document.
4. Two Airbus documents and Airbus Helicopters ER070 remain unparsed.
