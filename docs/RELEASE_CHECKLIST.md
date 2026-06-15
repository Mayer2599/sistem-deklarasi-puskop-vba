Release / Testing Checklist
==========================

Follow these steps before merging a PR that changes VBA/UserForms or workbook behavior.

Pre-merge manual tests
- Make a copy of the source workbook (.xlsm) and work on the copy.
- Backup the `Deklarasi` sheet (export or copy to a temporary workbook).
- Open the workbook and enable macros.

Role & Login
- Test login with at least one account per role: `Coorporate`, `Puskop`, `CU Primer`.
- Verify sheet visibility and that protected sheets are read-only for non-Corporate roles.

UserForm (Sistem-Klaim / UserForm2)
- Open `UserForm2` and confirm all labels and textboxes appear correctly.
- Enter a valid NAK and press Enter or click `Cari`:
  - Verify information loads into labels (`LblNAkey`, `LblTLkey`, etc.).
  - Numeric totals (`LblPin1key`, `LblSim1key`, `LblSol1key`) should match sheet aggregates.
- Verify checkboxes enable/disable logic per group:
  - Enabling `CbxDstjX` should enable corresponding `TBtglDstjX` textbox.
  - Enabling `CbxDbyrX` should enable `TBtglDbyrX` textbox.
  - Group checkboxes should maintain mutually-consistent behavior handled by `ManageCheckBoxGroup`.
- Test `CBSimpan` and `CBSimpan2` flows with a copied sheet to ensure rows update as expected.

Edge cases
- Search for NAK that does not exist — confirm graceful message and no UI crash.
- Test with empty or malformed fields.

Security & Data
- Ensure no sensitive production data is committed to the repo.
- Verify the workbook protection password is documented (if acceptable) and changed before production.

Post-merge steps
- Merge PR and run the tests again on `master`.
- Tag release (e.g., `v1.2`) and create GitHub release notes summarizing changes.

Notes
- If functionality touches sheet structure, update `docs/STRUKTUR-DATABASE.md` accordingly.
