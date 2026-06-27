## Rule-to-Finding Coverage

| Finding | Rule | Caught? |
|---------|------|---------|
| SCR-01 SQLi (login) | taint_mode.yml | ✅ |
| SCR-02 SQLi (search) | taint_mode.yml | ✅ |
| SCR-03 eval RCE | eval.yml | ✅ |
| SCR-04 path traversal | path-traversal.yml | ✅ |
| SCR-05 hardcoded secret | hardcoded-secret.yml | ✅ |
| SCR-06 IDOR | — | manual-only |
| SCR-07 auth bypass | — | manual-only |
| SCR-08 business logic | — | manual-only |

**Manual-only:** SCR-06, 07, 08 require understanding of ownership 
and intended behavior — pattern-based SAST cannot detect these.


## Ruleset Results
Ran all 6 custom rules against Juice Shop: 21 findings.
- Rules successfully caught all documented findings (SCR-01 to 05 + path traversal family).
- Output also includes known false positives (captcha eval — server input) and 
  test fixtures (codefixes/*), which require manual triage — demonstrating that 
  SAST output always needs human review.