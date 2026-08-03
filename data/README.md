# Data

`Perioperative_Dataset_csv.csv.enc` is the perioperative case dataset used throughout the
notebooks, encrypted with AES-256 (via OpenSSL). It is **not** de-identified enough to be
stored in plaintext on GitHub — it contains patient DOB, exact surgery timestamps,
city/area, and surgeon IDs, which together can re-identify individuals even though the
MR/visit numbers are hashed.

The plaintext CSV is intentionally excluded via `.gitignore` and must never be committed.

## Decrypting the dataset

You will receive the decryption passphrase separately.

From the repo root, with OpenSSL installed (bundled with Git for Windows / macOS / Linux):

```bash
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 \
  -in data/Perioperative_Dataset_csv.csv.enc \
  -out data/Perioperative_Dataset_csv.csv \
  -pass pass:"PASTE_PASSPHRASE_HERE"
```

This recreates `data/Perioperative_Dataset_csv.csv`, which is what the notebooks expect
(`notebooks/*.ipynb` read it via `../data/Perioperative_Dataset_csv.csv`).

## Handling the decrypted file

- Never commit the decrypted CSV (it's already gitignored, but don't override that).
- Don't upload it to other third-party services (cloud drives, ChatGPT, etc.) without
  the same data-sharing approval this file already required.
- If your institution's data use agreement changes, or the RA relationship ends, delete
  your local decrypted copy.
