# Adding a New Ranking Year

The website interface does not need to be redesigned.

## Recommended annual workflow

1. Add one ranking record for each institution to `data/rankings.json`.
2. Use the existing `institution_id` when the institution already exists.
3. Add a new institution object only when the school is not already in `institutions`.
4. Add the new year to `metadata.years`.
5. Update `metadata.updated_through`.

Each ranking record uses:

```json
{"institution_id":"national-universities-princeton-university","year":2027,"rank":1,"rank_display":"1"}
```

For a tie, use the numeric rank normally. For a source label such as `T1 (26-40)`, keep `rank` as `null` and place the exact source wording in `rank_display`.

The included `rankings_update_template.csv` can be used as an annual staging file before converting the new rows to JSON.
