# python-cwe90 — CWE-90 / python deterministic oracle

Concorde's **ratified** python-AST taint engine (vendored verbatim in `oracle/engine/`) proving
**recall 1.0 / FP0** on 11 discriminating probes (5 FLAG / 6 negative) for **CWE-90**. The probes
come from the cuda GPU-lane corpus, **semgrep-taint-mode adjudicated** — external, independent
ground truth (not this engine's output). Non-degenerate: it must FLAG the vulnerable cases AND
abstain on the safe/sanitized ones.

```
python3 verify.py
```

Exits 0 iff every FLAG probe
is flagged and no negative probe is. Apache-2.0.
