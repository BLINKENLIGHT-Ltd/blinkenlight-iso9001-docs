# BLINKENLIGHT lab — equipment inventory (planning draft)

Working document. Planning artefact; not part of the QMS. Once
populated and stable, the in-scope subset will be promoted into
`/qms/records/calibration-register.md` in Phase 3.

For each instrument, fields are:

- **Status:** In scope (calibration) / In scope (verification) /
  Out of scope.
- **Manufacturer, model, serial no.**
- **Acquired:** date (and supplier, if known — feeds clause 8.4).
- **Use cases:** which BLINKENLIGHT products / engagements rely on
  this instrument for measurements cited in records.
- **Calibration / verification basis:** what makes its measurements
  traceable, today.
- **Current cert / verification record:** provider, cert number,
  issue date, expiry date.
- **Cadence:** 12 / 24 / 36 months / verify each use, etc.
- **Cert PDF location:** path under `/qms/records/calibration/`
  (Phase 3).

## In scope

### HP 8753ES Vector Network Analyser, 30 kHz – 6 GHz

- **Status:** In scope (verification).
- **Manufacturer, model, serial no.:** Hewlett-Packard, 8753ES,
  `TODO(patrick)`.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** S-parameter measurements (return loss, gain,
  isolation) for antenna design verification — Paradar, Bluespot, HAPS
  programme work.
- **Calibration / verification basis:** User-cal against
  UKAS-accredited SOL cal kit before each controlled measurement;
  frequency referenced to GPSDO; periodic in-house performance
  verification against reference devices.
- **Current cert / verification record:** No instrument calibration
  certificate held. Traceability via cal kit cert (see below) and
  GPSDO.
- **Cadence:** User-cal each measurement; in-house performance
  verification annually.
- **Cert PDF location:** N/A (verification regime).
- **Posting / on-site cal note:** Postal calibration of the 8753ES is
  not recommended. The instrument is out of factory support, parts
  are scarce, and damaged Type-N ports from transit can be
  uneconomical to repair on a unit of this value. UKAS-accredited RF
  VNA cal is also hard to find in the UK; many labs offer
  "traceable" but not UKAS for S-parameters above a few hundred MHz.
  If a UKAS cert ever becomes necessary (e.g. an auditor pushes back
  on the verification regime), the right path is **on-site
  calibration** at Bethnal Green by a UKAS-accredited RF lab
  (Keysight UK Services, Trescal UK, TMD Technologies, or an
  NPL-affiliated specialist). Indicative cost: £600–£1,200 base cal
  plus £500–£1,500 engineer travel and on-site time.

### R&S SML 03 signal generator, 9 kHz – 3.3 GHz

- **Status:** In scope (verification).
- **Manufacturer, model, serial no.:** Rohde & Schwarz, SML 03,
  `TODO(patrick)`.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** Stimulus source for receiver characterisation,
  signal-chain testing, ADS-B (Automatic Dependent Surveillance —
  Broadcast) bench work.
- **Calibration / verification basis:** Frequency locked to GPSDO
  (traceable to UTC); amplitude verified periodically against
  spectrum analyser at known reference levels and against power
  meter (when calibrated power meter available).
- **Current cert / verification record:** No instrument calibration
  certificate held.
- **Cadence:** Verification annually; UKAS calibration recommended
  on the manufacturer-published 3-year interval.
- **Cert PDF location:** N/A pending first UKAS cal.
- **Posting / cal note:** Postal calibration is the standard route
  and is acceptable for this instrument (current form factor,
  available parts). Native cal interval per Rohde & Schwarz is
  **3 years**, which materially reduces ongoing cost. Indicative
  UKAS cost: £400–£900 per cycle. Route options: Rohde & Schwarz UK
  (manufacturer service, premium price but unambiguous UKAS
  schedule), Calibrate.co.uk, Trescal UK, or another UKAS-accredited
  RF lab with the relevant schedule. Verify the schedule covers RF
  signal-generator source calibration to 3.3 GHz before sending.

### Anritsu MS2665C spectrum analyser, 9 kHz – 21.2 GHz

- **Status:** In scope (verification).
- **Manufacturer, model, serial no.:** Anritsu, MS2665C,
  `TODO(patrick)`.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** Emissions characterisation, signal-quality
  measurements, harmonic / spurious analysis for Paradar, Bluespot,
  HAPS work.
- **Calibration / verification basis:** Frequency locked to GPSDO;
  amplitude verified periodically against signal generator output
  at known reference levels.
- **Current cert / verification record:** No instrument calibration
  certificate held.
- **Cadence:** Verification annually; UKAS calibration on a 24–36
  month interval to spread cost.
- **Cert PDF location:** N/A pending first UKAS cal.
- **Posting / cal note:** Postal calibration is acceptable — the
  MS2665C is a portable form-factor instrument designed for
  movement. The current product (MS2667C) is the successor, so
  long-term support is gradually declining, but UK cal labs still
  service the MS2665C routinely. Indicative UKAS cost: £500–£1,200
  per cycle. Route options: Anritsu Service UK (manufacturer
  service), Calibrate.co.uk (handles Anritsu), Trescal UK. Verify
  the lab's UKAS schedule covers spectrum-analyser calibration to
  at least 21.2 GHz before sending. Many UK labs ship "traceable"
  not UKAS for this band — the schedule check is load-bearing.

### Leo Bodnar Precision GPS Reference Clock (GPSDO — GPS-Disciplined Oscillator)

- **Status:** In scope (intrinsic traceability via GPS — no formal
  calibration required).
- **Manufacturer, model, serial no.:** Leo Bodnar Electronics,
  Precision GPS Reference Clock (450 Hz – 800 MHz, dual BNC output),
  serial no. `TODO(patrick)`.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** Frequency reference distributed to HP 8753ES VNA,
  R&S SML 03 signal generator, and Anritsu MS2665C spectrum analyser
  — establishes a single traceable frequency reference across the
  RF (Radio-Frequency) measurement chain.
- **Calibration / verification basis:** GPS lock to satellite
  constellation provides traceability via GPS time → UTC (Universal
  Time Co-ordinated) → caesium primary standards under the BIPM
  (Bureau International des Poids et Mesures). The standard
  explicitly accepts GPS as a traceable measurement reference. Lock
  state is signalled by two solid red LEDs on the unit.
- **Manufacturer-specified accuracy / stability:** Long-term
  stability approaches 1×10⁻¹² (set by GPS caesium reference). TCXO
  (Temperature-Compensated Crystal Oscillator) short-term jitter
  sub-picosecond. Phase noise at 10 MHz: −70 dBc/Hz at 1 Hz offset
  improving to −155 dBc/Hz at 1 MHz offset. GPS acquisition ~30 s
  from power-on; glitch-free reacquisition after GPS loss; PLL
  (Phase-Locked Loop) holdover maintains best-estimate output
  frequency when GPS is lost. Source: Leo Bodnar product page,
  retrieved 2026-05-20, archived at
  `planning/equipment-evidence/leo-bodnar-gps-reference-clock_2026-05-20.pdf`.
- **Current cert / verification record:** N/A — no calibration
  certificate exists or is required. Documented information for
  this instrument consists of: (a) the manufacturer specification
  PDF on file, (b) the per-measurement lock-state record in each
  measurement record, (c) the quarterly verification log entries
  (see Cadence below).
- **Cadence:** Lock state verified before each controlled
  measurement (both LEDs solid red, recorded in measurement
  record). Quarterly cross-check verification log — capture output
  frequency against a second independent frequency reference (e.g.
  Anritsu MS2665C set to count the GPSDO output, or comparison
  against any oven-stabilised reference inside the existing
  instruments), record result, file in verification log. Catches
  the rare failure mode where the unit indicates lock but is
  affected by local interference or GPS spoofing.
- **Cert PDF location:** N/A pending Phase 3 promotion. Manufacturer
  spec held at
  `planning/equipment-evidence/leo-bodnar-gps-reference-clock_2026-05-20.pdf`;
  will be promoted to `/qms/records/calibration/` with proper
  frontmatter and Master Document List entry in Phase 3.

### SOL (Short-Open-Load) cal kit, reference loads, and reference attenuator standards (Kirkby Microwave 85033), certified to 7 GHz

- **Status:** In scope (calibration — this *is* the traceable
  standard). The cal kit additionally includes traceable / calibrated
  reference attenuator standards; these are part of the traceability
  chain for amplitude verification of the signal generator and
  spectrum analyser, as well as for S-parameter reference-plane
  definition on the VNA.
- **Manufacturer, model, serial no.:** Kirkby Microwave Ltd, model
  85033, serial number 0882, options 001, 002, 010 and 022.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** Defines the traceable reference plane for all
  S-parameter measurements made on the HP 8753ES; traceable
  amplitude reference for verification of the R&S SML 03 and the
  Anritsu MS2665C within the 7 GHz ceiling.
- **Calibration / verification basis:** Kirkby Microwave traceable
  calibration (not a UKAS-accredited lab; traceability statement to
  be confirmed — see GAPS.md).
- **Current cert / verification record:** Cert no. K1397, issued
  2025-06-27, expires 2026-06-26. Held at
  `/qms/records/calibration/kirkby-microwave-85033-sma-cal-kit-cert-K1397_2025-06-27.pdf`.
- **Cadence:** 12 months.
- **Cert PDF location:** `/qms/records/calibration/`.

### Rigol MHO954 4-channel digital oscilloscope, 500 MHz

- **Status:** In scope (calibration — manufacturer factory cal
  current).
- **Manufacturer, model, serial no.:** Rigol, MHO954, `TODO(patrick)`.
- **Acquired:** `TODO(patrick — date, new)`.
- **Use cases:** Waveform capture for digital interfaces, time-domain
  signal characterisation cited in design verification records.
- **Calibration / verification basis:** Manufacturer factory
  calibration (traceable per Rigol's accreditation).
- **Current cert / verification record:** Factory cal cert,
  `TODO(patrick — cert ref, date)`.
- **Cadence:** Manufacturer-stated interval (typically 12 months).
- **Cert PDF location:** `TODO`.

### HP 34401A 6½-digit multimeter

- **Status:** In scope (calibration).
- **Manufacturer, model, serial no.:** Hewlett-Packard, 34401A,
  `TODO(patrick)`.
- **Acquired:** `TODO(patrick)`.
- **Use cases:** DC voltage / current / resistance readings cited in
  design verification or release-of-product records.
- **Calibration / verification basis:** UKAS-accredited calibration
  by `TODO(patrick — provider)`.
- **Current cert / verification record:** Cert no. `TODO(patrick)`,
  issued `TODO(patrick — date)`, expires `TODO(patrick — date)`.
- **Cadence:** Per cert — typically 12 or 24 months.
- **Cert PDF location:** `TODO`.

### Reference horn antenna

- **Status:** In scope. Used in antenna measurements that feed
  design verification records.
- **Manufacturer, model, serial no.:** `TODO(patrick)`.
- **Acquired:** `TODO(patrick)` — relatively new.
- **Use cases:** Gain reference / far-field measurements for
  Paradar, Bluespot, HAPS antenna design verification.
- **Calibration / verification basis:** `TODO(patrick — confirm:
  manufacturer-supplied factory S-parameter and gain data, or a
  separate calibration certificate?` See clarification note below.
- **Current cert / verification record:** `TODO(patrick — cert
  details once confirmed)`.
- **Cadence:** `TODO`.
- **Cert PDF location:** `TODO`.

**Clarification needed on this item:** Factory-supplied S-parameter
data and gain curves are usually sufficient for clause 7.1.5.2 if
the manufacturer's documentation includes a traceability statement
(typically "traceable to NIST (National Institute of Standards and
Technology) / NPL (National Physical Laboratory) via cal lab X").
If the data is only "typical" or "as-designed" with no traceability
statement, recharacterisation against a known reference may be
required. The retention period for the cert/data record is the
lifetime of the antenna plus retention period under
`/qms/DOC-CONTROL.md`.

## Out of scope

Each item below carries (or will carry) a physical label per clause
7.1.5.2 c — "identified in order to determine their status" — to
prevent inadvertent use in controlled measurements.

### Marconi 6960B RF power meter + 6910 power sensor, 10 MHz – 20 GHz

- **Reason:** Almost never used. No current calibration certificate.
- **Action:** Apply physical label: "Not calibrated — not for use in
  controlled measurements".
- **Note:** If a future need arises, re-evaluate scope and arrange
  calibration before any in-scope use.

### 2× Ramsey shielded chambers (~50 × 40 × 40 cm)

- **Reason:** Passive RF-isolation enclosures, not measurement
  instruments. Shielding effectiveness is not load-bearing for
  current development uses.
- **Action:** None. If a measurement made inside one of the chambers
  is ever cited in a customer record, the chamber's shielding
  effectiveness would need a one-off characterisation.

### Tektronix TDS794, 4-channel 2 GHz oscilloscope

- **Reason:** Development bench use only. Waveform captures not cited
  in controlled records.
- **Action:** Apply label: "Bench / development use — not for
  controlled measurements". Revisit if measurement use changes.

### Picoscope 2000, 10 MHz USB oscilloscope

- **Reason:** Development bench use only.
- **Action:** Apply label as above.

### Dual output bench PSU 0–30 V, 2 A

- **Reason:** Power source, not measurement instrument. Readings not
  cited externally.
- **Action:** None.

### Single output bench PSU 0–30 V, 20 A

- **Reason:** As above.
- **Action:** None.

### Single output bench PSU 0–300 V, 1 A

- **Reason:** As above.
- **Action:** None.

### Kunkin KP184 electronic load

- **Reason:** Load, not measurement instrument. Not used to produce
  readings cited externally. `TODO(patrick — confirm: is the e-load
  ever used to characterise battery life or power consumption that
  is cited to a customer? If yes, revisit scope.)`.
- **Action:** Confirm; apply label as appropriate.

### Hakko FM-204 desoldering station, Hakko FX-888D soldering iron, WEP 858D hot air gun

- **Reason:** Process equipment.
- **Action:** None.

## EMC (Electromagnetic Compatibility) position

BLINKENLIGHT does not issue formal EMC compliance reports. Two
patterns of EMC activity occur:

- **Indicative audits during development.** Conducted and radiated
  emissions are checked quickly during a project to give the client
  an indication of likely emission peaks. These measurements inform
  design decisions but are not handed over as formal compliance
  evidence.
- **Mock or formal EMC reports for a specific client.** Handled by
  leasing the specific equipment required for that client's
  applicable test standards, per project. Leased equipment carries
  its own current calibration certificate from the leasing supplier;
  the lease arrangement falls under clause 8.4 (control of externally
  provided processes), and the leased instrument's calibration status
  is recorded in that project's records at point of use.

Implications for scope:

- The **LISN (Line Impedance Stabilisation Network)** held in-house
  is in scope of clause 7.1.5 if measurements taken with it are ever
  cited externally (even informally to a client). Status to be
  decided once located and assessed — see TODO in `GAPS.md`. Pending
  that assessment, hold provisionally in scope.
- Broadband EMC antennas, near-field probes, pre-amps held in-house
  are out of scope while emissions audits remain indicative-only;
  in scope at the moment any measurement is cited externally as
  formal evidence.
- The leased-equipment model for formal EMC work is documented as
  a project-specific procedure addendum in Phase 3; the existence
  of leased instruments does not, by itself, require additional
  in-house equipment to be in scope.

## Items to confirm presence / absence

- **LISN — location, model, calibration status.** Currently
  uncertain. See TODO in `GAPS.md` to track down and assess.
- **RF cables and adapters** used in calibrated measurement chains.
  Itemise as a separate register; each cable carrying a unique label.
  See TODO in `GAPS.md`.
- **Connector torque wrench** — `TODO(patrick — confirm presence;
  affects RF measurement repeatability)`.
- **Anechoic chamber** — `TODO(patrick — confirm: none — the Ramsey
  enclosures are shielded only)`.

## Procedure-drafting notes (for Phase 3)

When the calibration / measurement procedure is drafted into
`/qms/procedures/` in Phase 3, the following steps must appear
explicitly. They are not optional and capture the position taken in
this inventory.

1. **Before any controlled measurement:**
   - Confirm and record that the GPSDO is locked (e.g. lock LED
     state, satellite count). A measurement taken with an unlocked
     GPSDO is not traceable in frequency and must be marked
     accordingly.
   - For VNA measurements: perform user-cal against the SOL cal kit
     immediately before the measurement, retain the cal data with
     the measurement record, and cite the cal kit cert number in the
     record.
   - For amplitude-sensitive measurements on the signal generator
     or spectrum analyser: verify against the traceable reference
     attenuator standard at the test frequency and amplitude of
     interest, and record the verification result.
2. **Annual in-house performance verification of the VNA, signal
   generator, and spectrum analyser** against known reference
   devices and the cal kit's loads and attenuators. Results recorded
   in the verification register. Out-of-tolerance results trigger
   a clause 7.1.5.2 (d) action: assess validity of prior
   measurements and notify affected customers if necessary.
3. **Periodic VNA performance verification** — covers source
   flatness sanity check, receiver linearity at known reference
   levels, residual directivity / match after cal. The verification
   procedure cites the specific reference devices used and their
   own traceability.

This block is for drafting reference only; nothing here is yet a
controlled document.

## Calibration / verification regime — written position

Drafted properly in a `/qms/procedures/` document in Phase 3. The
position is:

- The SOL cal kit (Kirkby Microwave cert K1397, traceable; not UKAS)
  is the traceable measurement standard for S-parameter work to 7 GHz.
- The GPSDO is the traceable frequency reference for the VNA, signal
  generator, and spectrum analyser.
- The VNA, signal generator, and spectrum analyser are treated as
  "verified prior to use" per clause 7.1.5.2's "calibrated or
  verified" wording, with annual in-house performance verification
  against the cal kit and known reference devices.
- Instruments with current manufacturer or UKAS calibration certs
  (Rigol MHO954, HP 34401A) are managed per their cert renewal
  cadence.
- The position is documented, with rationale, in the calibration
  procedure. Performance verification records are retained.

A move to UKAS calibration of the VNA, signal generator, and
spectrum analyser on a 24–36 month interval is planned for Year 2
or Year 3 of the certification cycle, to spread cost and reduce
audit-argument friction over time.
