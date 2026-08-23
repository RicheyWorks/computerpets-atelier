# Atelier contract

Do not implement against folklore. Implement against this file.

## Identity

- Product: **Atelier**
- Repo: `computerpets-atelier`
- Category: AI & GPU
- Idea: Generative Asset Maker
- Port / surface: `8094`

## Must

- Stay canon with 210 species. No illegal hybrids. No swapped voices.
- Treat the desktop overlay as the main quest. This organ is optional until wired.
- Fail soft: the overlay keeps walking if this service is down, unless this *is* the overlay.
- No PII in public artifacts (Steam id, wallet, home path, webcam frames).

## Data

TraitSlot(id, zIndex, mask) · Candidate(png, seed, score) · CanonGate(pass|fail, reasons[])

## Surface

- POST /v1/generate — prompt + species lock + trait slot → PNG + metadata
- POST /v1/critique — reject if it violates the species silhouette
- GET /v1/slots/{speciesId} — legal trait slots (hat, mark, color, accessory)

## Neighbors

- computerpets-bazaar (list traits)
- computerpets-minter (pin + mint)
- computerpets-studio (human in the loop)
- computerpets-lore (canon checks)

## Failure doctrine

Canon fail → do not upload. GPU OOM → smaller batch. NSFW filter trip → discard, log, no retry of the same seed.

## Stack

Python 3.12 · diffusion (SDXL / Flux) · ControlNet pose · trait JSON schema · S3-compatible asset store
