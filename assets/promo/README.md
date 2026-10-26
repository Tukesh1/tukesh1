# Terminal profile promo

`tukesh-terminal.gif` — the header loop on the profile README.

`tukesh-terminal.webp` is the same sequence in full colour. Both are written
by [`generate.py`](./generate.py).

```bash
python3 -m venv .venv
.venv/bin/pip install pillow
.venv/bin/python assets/promo/generate.py
```

Run from the `tukesh1` directory. `PROMO_EXPORT` and `PROMO_Q` work the same
as in the original generator.
