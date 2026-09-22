# India Rx Studio

Clinician-facing prescription template builder for Indian primary and secondary care. It uses an offline, citation-aware retrieval layer over curated disease modules and guideline metadata, so core decision support works without an API key.

## Safety model

- For registered clinicians; not for patient self-medication.
- Emergency/high-risk syndromes block routine outpatient prescription generation.
- User-supplied brand names are normalized to generics and do not override guideline pathways.
- Every template requires review of allergies, pregnancy, renal/hepatic function, interactions, duplication and local susceptibility/formulary.
- The generated document is an editable template, not an autonomous prescription.

## Run and build

```bash
npm install
npm run dev
npm run build
```

## Knowledge base

The initial source set includes ICMR Standard Treatment Workflows, NCDC antimicrobial guidance, MoHFW dengue guidance, NTEP tuberculosis guidance, and selected current international specialty sources. Source links and dates are visible in the Evidence tab. Clinical content should be reviewed and versioned before production use.

## Planned production hardening

- Auth and clinician registration verification
- Audit log and signed template versions
- Institution-specific formulary and antibiogram
- Server-side, versioned guideline chunk store with scheduled clinical review
- DPDP-aligned patient-data controls; avoid storing identifiable data in the current browser-only prototype
