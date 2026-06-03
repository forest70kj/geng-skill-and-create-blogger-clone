# Workflow Overview

The core workflow is staged and user-gated:

```text
source retrieval
-> case bite extraction
-> opening only
-> user review
-> body only after locked opening
-> user review
-> ending only after locked opening/body
-> user review
-> full draft assembly
-> final user decision
```

Full-script generation is not the default. If the user asks for unattended generation, keep section boundaries visible and mark review gates as pending.

