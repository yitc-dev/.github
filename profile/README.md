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

Pin it by hand at first install and verify against it before anything is written.

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
