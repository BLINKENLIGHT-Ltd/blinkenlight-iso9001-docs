# Aviation product / grounding liability insurance — feasibility

Research note for the 2026-11-09 Hiscox renewal decision. Internal
planning material; not part of the QMS. Tracked in `planning/GAPS.md`.

## Why this matters for BLINKENLIGHT

- The current Hiscox policy (PL-PSC10003370426/02) **excludes aviation
  use**. This is normal: general and combined-liability policies are
  either silent on aircraft products or carry an explicit aircraft-
  products exclusion. Even where the exclusion is absent, a standard
  £1M/£5M public/products policy will not respond once a product is
  identified as contributing to an aircraft loss.
- BLINKENLIGHT designs and supplies RF/antenna hardware into the Aalto
  HAPS (High-Altitude Platform Station) programme, an Airbus subsidiary.
  At onboarding, Airbus procurement asked whether we held aviation-
  compatible PL; we disclosed we did not, and they agreed to proceed.
  That agreement does not remove the underlying exposure — it means the
  contractual flow-down risk currently sits with us, uninsured for
  aviation end-use.
- Supply-chain position is not protection. Prime and tier-1 contractors
  increasingly push third-party liability down to lower-tier suppliers.
  After an incident, claimants pursue every company in the chain
  connected to the failed part — designer, manufacturer, distributor.

## What aviation product liability adds over a standard policy

1. **Aviation product liability** — third-party bodily injury / property
   damage arising from a product used in an aircraft application, which
   the standard policy expressly excludes.
2. **Grounding liability** — third-party loss-of-use cover when a fleet
   is grounded by mandatory order of the Civil Aviation Authority (CAA)
   or equivalent following an "occurrence" traced to the product. No
   bodily injury or property damage is needed to trigger a grounding
   claim, so a general-liability policy structurally cannot cover it.
3. **Product recall / rectification** — usually a separate extension;
   often excluded from base product liability. Aviation recall costs
   (fleet-wide removal, replacement, re-test) run to millions.

## Feasibility for a small supplier

Feasible but a specialist placement, not a bolt-on to the Hiscox policy.
Key points:

- These are standalone policies placed through aviation-specialist
  brokers / Lloyd's, not high-street SME insurers.
- Underwriters price the **controls** as much as the risk. A documented
  quality management system is a material rating factor — AS9100 is the
  aerospace benchmark, but a credible ISO 9001:2015 QMS with documented
  design, test and traceability records is exactly the evidence they ask
  for. **The ISO 9001 work directly improves insurability here.** The
  Castlemead claims example below turned on the supplier being able to
  produce test records for parts supplied 13 years earlier — our
  InvenTree-backed traceability and product test procedures (PTP-01/02)
  are the relevant evidence.
- Rating factors: turnover, product type and criticality, end-use
  (civil / defence / space / UAV), territory (US programmes attract
  higher premiums and stricter underwriting), claims history, required
  limit of indemnity, and quality controls.
- Watch-outs when quoting:
  - **Retroactive date** — aviation claims surface years after supply;
    push for a retroactive date covering existing Aalto supply.
  - **Definition of "aircraft products"** — must be broad enough to
    capture our RF/antenna hardware and any airside work.
  - **Contractual liability** — cover typically excludes liability
    assumed by contract beyond common-law negligence; check against the
    Aalto/Airbus flow-down terms.
  - **Grounding sub-limit** — confirm whether included as standard or an
    add-on, and review the sub-limit and CAA-trigger wording.

## Market / provider options (UK)

| Provider | Route | Notes |
|---|---|---|
| **DUAL UK** | Via broker | Standalone aerospace products liability; no requirement to also buy a combined policy. Grounding liability included as standard; airside working-parties cover available. Explicitly built for suppliers where cover is otherwise hard to place. |
| **Castlemead Insurance Brokers** | Direct broker | Aerospace-specialist broker; appointed broker for the West of England Aerospace Forum (WEAF). Publishes a UK supplier grounding-claim case study. Good first call for a small supplier. |
| **Chubb (Aerospace)** | Via broker | Dedicated aviation product liability for manufacturers/distributors. |
| **Allianz** | Via broker | Aviation products liability section available. |
| **Aircraft Builders Council (ABC)** | Lloyd's lineslip via any Lloyd's broker | Bundles aviation products + grounding, non-occurrence grounding, products recall, excess. North-America-oriented but accessible through a UK Lloyd's broker. |

## Recommended next step

At the 2026-11-09 renewal, ask Hiscox whether they can extend/place
aviation product + grounding liability (likely referred out), and in
parallel get a quote from an aerospace-specialist broker (Castlemead /
DUAL) presenting the ISO 9001 QMS, product test procedures and InvenTree
traceability as risk controls. Decision then turns on premium vs the
value of the Aalto/Airbus relationship and any future aerospace work.

## Sources

- DUAL UK — Aviation Products Liability:
  https://www.dualinsurance.com/uk-en/products/commercial/aviation-products-liability
- Castlemead — Understanding Aviation Products Liability Insurance in the UK:
  https://castlemead.com/navigating-the-skies-understanding-aviation-products-liability-insurance-in-the-uk/
- Global Aerospace — Products Liability in the Supply Chain:
  https://www.global-aero.com/mitigating-risk-the-need-for-products-liability-insurance-in-the-supply-chain/
- Chubb — Aviation Product Liability factsheet:
  https://www.chubb.com/content/dam/chubb-sites/chubb-com/uk-en/business/aviation/documents/pdf/Chubb-UK0161-CGM-AviationProductLiability_Factsheet-202103.pdf
- Allianz — Aviation Products Liability section wording:
  https://www.allianz.co.uk/content/dam/onemarketing/azuk/allianzcouk/broker/docs/policy-wording/AL0001-aviation-products-liability-section.pdf
- Aircraft Builders Council — Master Lineslip overview:
  https://www.aircraftbuilders.com/MasterLineslip-Overview
- All Access Insurance — Aviation Products and Grounding Liability:
  https://www.allaccessins.com/blog/aviation-products-and-grounding-liability-insurance
