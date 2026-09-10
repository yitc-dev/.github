# yitc

## Releases

**v2.0.2** — released 2026-09-10. The installed engine is now executable: `release install`
carries the verified tree's file modes through, so `<into>/bin/yitc-v2` runs directly after an
install instead of failing with Permission denied. This is the update target for the trial host.

**v2.0.1** — released 2026-09-10. Clean-machine install fixes: the executable bit now
survives publishing, `release verify` no longer needs a yitc session, and the digest covers
the tracked release tree — so a fresh clone verifies, runs and installs on a machine that has
never seen yitc.

**v2.0.0** — released 2026-09-05.

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
