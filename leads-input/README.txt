LEAD SCOUT — INPUT FOLDER
─────────────────────────

Drop any CSV here to feed the leads dashboard.

Supported formats (columns auto-detected):
  • PropStream export:   Address, City, State, Zip, Owner Name, Estimated Value, Signal
  • BatchLeads export:   property_address, city, state, zip_code, owner_full_name
  • Generic:            any CSV with an "address" or "street_address" column

Signal values (optional column): permit, lis_pendens, probate, expired
  → If omitted, defaults to "expired" (general off-market)

Run the scout:
  cd ~/hermes/scripts/laurene-pipeline/lead-scout
  python3 lead_scout.py              # reads this folder, enriches via BCPA, publishes
  python3 lead_scout.py --no-enrich  # skip BCPA (faster, less data)
  python3 lead_scout.py --dry-run    # preview only, no deploy

After processing, CSVs are moved to leads-input/processed/
