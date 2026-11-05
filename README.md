# EquipmentSeal

**Local-first equipment usage, maintenance, and rental hours evidence sealer for field operators.**

Offline. Deterministic. Pay once. Compatible with QuantumGuard CONTRACT-v1, TimesheetSeal, DailySeal, JobSeal, and the Operator Pages suite.

## Why EquipmentSeal?

Field operators lose money and face disputes over equipment hours, idle time, maintenance records, fuel usage, and rental periods.  
EquipmentSeal captures a structured daily/job equipment log (asset ID, operator, hours used, maintenance events, fuel, rental rates) and seals it into a client-verifiable QuantumGuard evidence bundle.

- No SaaS. No subscription. Runs completely offline after key setup.
- Clients (or their auditors) verify the pack with the free QuantumGuard verifier (`qg verify`).
- Pairs with TimesheetSeal for crew hours, MediaSeal for photos, and Chaser for invoicing.
- Deterministic: same inputs → same sealed pack.

## Quick Start

```bash
# Recommended for real Ed25519 signatures
pip install cryptography

python3 src/equipmentseal.py --demo
python3 src/equipmentseal.py --json samples/equipment-001.json --out sealed-equipment.json
```

Verify the output with the QuantumGuard CLI (from the quantumguard repo):

```bash
qg verify sealed-equipment.json
```

Expected verdict: **PASS**.

## What you can sell

| SKU       | Price | Includes                                      |
|-----------|-------|-----------------------------------------------|
| Operator  | $39   | CLI + sample templates + key setup guide + 1-year email support |
| Command   | $129  | + batch mode + CSV/Excel export + reseller rights for client packs |
| Agency    | $349  | + white-label + multi-site key management + design partner onboarding |

Purchase / access: danpennic@gmail.com  
Or use the Operator Pages Stripe checkout flow.

Source remains free under Apache-2.0 OR MIT. Commercial Operator Pack sold separately.

## Stack Fit

- Python CLI (same family as TimesheetSeal, DailySeal, FieldSeal, JobSeal, MediaSeal, SafetySeal)
- Emits QuantumGuard CONTRACT-v1 bundles (Ed25519, deterministic canonical JSON)
- Local key storage (PEM)
- Designed to drop into the Operator Pages field stack

## License

Apache-2.0 OR MIT
