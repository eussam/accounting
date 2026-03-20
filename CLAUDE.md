# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is an accounting document repository for **EURL EUSSAM DEVELOPPEMENTS** (a French single-member LLC). It stores fiscal year documents exported from the **Shine** business bank account and official accounting documents (bilan, PV assemblée, etc.).

## Repository Structure

- `{year}/Bilan/` — Official accounting documents from the accountant (balance sheet PDF, confidentiality declaration, INPI mandate, PV d'assemblée)
- `{year}/EUSSAM_DEVELOPPEMENTS_{start}_{end}_EXPORT/` — Shine bank export containing:
  - `ACHATS_{dates}/` — Purchase receipts/invoices (PDF), one per transaction
  - `VENTES_{dates}/FACTURES/FACTURES_PAYEES/` — Issued invoices (sales)
  - `BANQUE_{dates}/` — Bank statements in CSV, QIF, and OFX formats

## Key Data

- **Bank**: Shine (IBAN FR7617418000010000880534221)
- **CSV separator**: semicolons (`;`), values quoted, French number format (comma as decimal separator)
- **CSV columns**: Transaction ID, Date valeur, Date opération, IBAN, Type transaction, Transaction personnelle, Category, Débit, Crédit, Solde mouvement, Solde bancaire, Libellé, Nom contrepartie, Montant HT, TVA totale, TVA 20%, TVA 10%, TVA 8.5%, TVA 5.5%, TVA 2.1%, TVA personnalisée, Pièces, Date ajout pièces, Commentaire
- **Bilan PDF**: Image-based (Print To PDF), requires `poppler` (`brew install poppler`) + `pdftoppm` conversion to PNG for reading

## Contexte business

Le gérant est également salarié en parallèle. Les exercices 2024 et 2025 correspondent à une **pause d'activité** sur l'EURL : l'activité salariée n'a pas permis de trouver des clients à côté. Cela explique :
- La chute du CA (53 150 € en 2023 → 5 000 € en 2024)
- Le maintien des charges courantes (abonnements, outils, déplacements) pour garder l'EURL opérationnelle
- La perte comptable de -14 684 € en 2024, absorbée par les réserves accumulées

## Working with this repo

- All interactions should default to French language when explaining accounting concepts to the user
- The user is not an accounting expert — explanations should be pedagogical and jargon-free
- When analyzing the bilan, cross-reference with the Shine CSV export to verify/explain line items
- Purchase PDFs are named with pattern: `ACH_{date}_{vendor}_{uuid}.pdf`
- Sale invoices are named with pattern: `VT_{date}_{vendor}_{uuid}.pdf`
