# yitc

## Releases

**v2.0.3** — released 2026-09-11. The mirror was republished as a single clean lineage: this is
the only release on it (earlier tags were retired). Signed; verify against the trust anchor
`SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below. This is the install target.

### Trust anchor

Every yitc release is signed. The trust root is anchored on this key fingerprint, published
**here** — on a channel independent of the release mirror, because the mirror cannot vouch
for itself:

```
SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY
```

Pin it at first install and verify against it before anything is written.

**In plain words, if you are not sure what this is.** The anchor fingerprint is a public `SHA256:…`
line that lets your AI check the release was not tampered with: it is not a secret, not a password
and not an account — you need no key and no login, because this repository is public. You do not
have to understand it or keep it safe. Either copy the one line above and hand it to your AI, or
simply hand your AI the link to the mirror — its README names this page, and the AI comes here for
the line itself, shows you this page's address and the exact line it took, and asks you to confirm
one thing: that this is the `yitc-dev` organization page. That confirmation is the whole of your
part. The AI must never take the anchor from the mirror it is about to check — a thing does not get
to vouch for itself — which is why the line lives here and not there.

### Install

```
git clone https://github.com/yitc-dev/yitc yitc
yitc/bin/yitc-v2 release verify yitc --anchor SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY
yitc/bin/yitc-v2 release install yitc --into <target-dir> --anchor SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY
```

`release verify` writes nothing under any outcome — it is the gate. `release install` runs that
same gate to a verdict before the target directory is opened, so a refused install leaves the
destination byte-identical. A tampered artifact, a tampered trust root and a revoked signing key
are each refused by name.

### After the install — the bootstrap order

The anchor and the three commands above are the whole pre-trust set: take them from HERE, never
from the mirror. Once `release verify` has passed, the installed release carries the rest of the
order at `<target-dir>/onboarding/bootstrap-order.md` — prerequisites and their check commands,
`init`, the `yitc-ops.yaml` kernel pin, the external-auditor install and binding, and the first
session. You install your AI tool, open it, point it at this page and say «install»; it reads that
order and drives the rest with your agreement.

The external auditor is recommended, not required: work runs from day one on the one AI provider
you already have, a second, different provider is recommended because it catches the first one's
blind spots, every audit that ran on the same provider is stamped as such, a reminder prints at each
session start until one is bound, and binding is a few `config set auditor.<tier>.*` lines in one
machine-settings file outside the engine tree.
