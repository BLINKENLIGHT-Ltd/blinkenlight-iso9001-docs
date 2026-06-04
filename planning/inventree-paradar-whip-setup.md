# InvenTree setup — Paradar 5 dBi whip (batch acceptance)

Internal planning / implementation guide (not part of the controlled
QMS). One-time setup plus the recurring per-bag flow, supporting PTP-02
and REG-06. Doc reference: <https://docs.inventree.org/en/latest/>.

## Model in one line

One **batch-tracked** part (not serialized). Each **bag of 50** is a
separate stock item; all bags from one delivery/production lot share the
lot batch code **`B-YYYYWWNN`** (the `B-` prefix keeps it distinct from
`YYYYWWNN` serials). Incoming stock carries the custom **`Untested`**
status (logical Quarantined → unavailable) in `Untested stock only`; a
bag is sample-tested at order time (PTP-02);
the acceptance **test results are recorded against the bag stock item in
InvenTree**; on acceptance it moves to **`Tested ok stock only`** and
ships; defectives are scrapped. REG-06 tracks only the cross-bag
**inspection severity** for the switching rules.

## One-time setup

1. **Supplier / manufacturer.** Shenzhen Qifan Communication Equipment
   Co., Ltd. as a Company (mark *manufacturer* and *supplier*); approval
   statement in the **Company description** per QP-16 §4; add the supplier
   part to the antenna part. No certificate (REG-05).
2. **Part.** `Paradar 5 dBi whip antenna` (SKU ANT-868-5): *Salable* =
   yes; *Component* = no; *Trackable* = no; **batch tracking** on; mark it
   **testable** so test templates apply.
3. **Test templates** on the part (these are the per-bag acceptance
   record — see PTP-02 §7). Use the Result toggle for pass/fail; no
   `Choices` on the value fields:
   - **Sample testing — measured VSWR readings** — *requires value*.
     Value = comma-separated VSWR-at-868 readings. Result PASS if every
     sampled unit meets both PTP-02 §3 criteria (min within 853–883 MHz;
     ≤ 1.5 at 868), else FAIL.
   - **Whole bag screened?** — Value = `na` if the sample passed; on a
     sample fail, the **number discarded** after the 100 % screen.
   - **Bag size and sample size** — Value = `50, n 8` (`n 13` tightened).
   - **VNA calibration confirmed** — Value = `user-cal vs SOL kit cert
     <K1397>; GPSDO locked`. Result PASS. The QP-06 traceability record
     for the measurement (one user-cal covers a test session — copy the
     same value to each bag tested in that session).
4. **Stock locations** (created under Pill Box): **`Untested stock only`**
   (incoming, awaiting test) and **`Tested ok stock only`** (accepted,
   ready to ship). Defectives are scrapped by status — no separate
   quarantine location needed.

## Per delivery (receipt of ~3,000)

1. Receive the purchase order into `Untested stock only` with the custom
   **`Untested`** status. Assign the **delivery-lot batch code**
   `B-YYYYWWNN` (e.g. `B-20262201`) — one code for the whole lot.
2. **Split into per-bag stock items** (qty 50); every bag carries the same
   lot batch code, its own test results, and a **QR label linking to its
   stock item**. Each bag is then individually testable and traceable.

## Per bag (at order / test time) — recurring

1. Pick a bag stock item from `Untested stock only`.
2. **Confirm the VNA user-cal** against the SOL kit with the GPSDO in lock
   (QP-06), then **test the sample** (n = 8) on the VNA per PTP-02.
3. **Record the test results on the bag stock item** (Test Results tab):
   the four templates above. ← the acceptance record.
4. **Accept (Sample VSWR = PASS):** move the bag to `Tested ok stock
   only`, status **OK**; allocate to the sales order and ship.
5. **Reject (Sample VSWR = FAIL):** 100 % screen the bag; enter the
   discard count in *Whole bag screened?*; **remove the defectives** by
   stock adjustment (status *Rejected*/*Destroyed*, reason noted) → QP-13;
   move the conforming remainder to `Tested ok stock only`. Apply the
   PTP-02 §6 switching rule; if a supplier failure, raise REG-03 + REG-05.
6. **Ship:** allocate `Tested ok stock only` stock to the sales order; if
   the customer requires assurance, issue **one batch Certificate of
   Conformity for the shipment** (not per unit).

## QMS records outside InvenTree

The per-bag acceptance evidence now lives **in InvenTree** (the test
results on the bag stock item). Outside InvenTree you only maintain:

1. **REG-06** — update the inspection-severity table **only when the
   switching rules change severity** (Normal ↔ Tightened). To apply the
   trigger, read the last five bags' *Sample VSWR* results in InvenTree.
2. **On a supplier-caused reject:** a **REG-03** corrective action and a
   **REG-05** supplier re-evaluation note (QP-16 §8).
3. **Per shipment (optional):** a batch **Certificate of Conformity**.

Everything else (batch code, stock movement, scrap of defectives, the
per-bag readings, pass/fail and calibration confirmation) is the
InvenTree record.
