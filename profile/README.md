# yitc

## What you get and what you need

**What you get.** An AI that works on your project the way a careful developer would: it plans each
change, has it checked, tests it, and keeps a written record of what it did and why. You say what
you want in your own words; the AI does the typing.

**What you need.**
- **A server** — a rented Linux machine is enough.
- **One AI tool with its account.** Either a subscription (a fixed monthly price) or usage-based
  billing (you pay for what you use). Either works.

**Who does the work.** Project work runs as an **ordinary user** on the server. The all-powerful
administrator account (root) is needed only for the first few minutes of setup, and not after.

**Coming back next time.** Log in to the server and open your AI tool. Opened in your home folder,
it lists your projects and you pick one; opened inside a project folder, it starts that project by
itself. The one phrase to remember is **"start the project"**.

**An optional second AI provider.** You can start with just the one AI tool. Adding a second,
different AI provider as an auditor is recommended: it checks the first one's work and catches the
blind spots the first one cannot see in itself.

**Two stands, when the product is iterated.** Not needed on day one. A project can keep two running
copies besides production: the **DEV stand (ДОРАБОТКА)**, where an open spike — an experiment — is
tried, and the **ACCEPTANCE stand (ПРИЁМКА)**, which shows landed `main` so you can click the result
before real users do. While a spike is open, changes to what it explores go into the spike by default.
The recommended order for finished work is card → land → ACCEPTANCE stand → production; `deploy` only
prints advisory reminders and never blocks (SPEC-0205).

## Releases

**v2.6.0** — released 2026-10-09. Fixes and new behaviour, made since v2.5.0 and listed in its signed
release notes — the middle digit changed, so read those notes before updating; an install of v2.5.0
updates with the steps they give under «Updating from the previous release». Signed; verify against the
trust anchor `SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below. This is the install target.

**v2.5.0** — released 2026-10-07. Fixes and new behaviour, made since v2.4.0 and listed in its signed
release notes — the middle digit changed, so read those notes before updating; an install of v2.4.0
updates with the steps they give under «Updating from the previous release». Signed; verify against the
trust anchor `SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below.

**v2.4.0** — released 2026-10-05. Fixes and new behaviour, made since v2.3.0 and listed in its signed
release notes — the middle digit changed, so read those notes before updating; an install of v2.3.0
updates with the steps they give under «Updating from the previous release». Signed; verify against the
trust anchor `SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below.

**v2.3.0** — released 2026-10-05. Fixes and new behaviour, made since v2.2.2 and listed in its signed
release notes — the middle digit changed, so read those notes before updating; an install of v2.2.2
updates with the steps they give under «Updating from the previous release». Signed; verify against the
trust anchor `SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below.

**v2.2.2** — released 2026-10-03. Fixes only, made since v2.2.1 and listed in its signed release
notes; an install of v2.2.1 updates with the steps those notes give under «Updating from the previous
release». Signed; verify against the trust anchor
`SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below.

**v2.2.1** — released 2026-10-03. The re-created mirror starts at this release; earlier releases,
v2.2.0 included, are no longer published. It carries the fixes made since v2.2.0, listed in its signed
release notes; an install of v2.2.0 updates with the steps those notes give under «Updating from the
previous release». Signed; verify against the trust anchor
`SHA256:fxSmnOxwlztBxmGq5ckGI+Xg9XKMfE33WBXeCnrhikY` below.

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

### Before the install — from root to an ordinary user

If you are logged in as **root** (the all-powerful machine account), your AI does this FIRST, before
it clones or runs anything from the mirror. These steps come from HERE, not from the mirror, and they
are ordinary account set-up done with the machine's own standard tools:

1. Create an ordinary working user (with the name you choose).
2. Keep recovery access: root, or your current way in, stays usable until the new login is proven —
   never lock yourself out.
3. Set up SSH (the remote-login key) for that user, copying the key you already log in with.
4. **PROVE a second login before leaving root:** open a NEW connection as the working user while the
   root session is still open, and check that it works. Only then does root step aside.
5. In that new window, start your AI tool and paste ONE line — the link to this page and the word
   «install». There is no hand-off file: that one line is the whole hand-off.

The mirror is cloned, verified and installed only by that working user, never as root. If you are
already an ordinary user, skip this.

### Before you install — four things to know

Your AI says these to you, in your language, before it clones or installs anything:

- **What it is.** A way of working in which the AI does the work in small, checked, recorded steps, so
  you can always see what was done and why.
- **What it costs.** Your own AI tool's subscription or usage-based billing — nothing else is sold here.
  Every check the AI runs uses your AI tool too, so this is slower and uses more of your plan than a bare
  AI agent, in exchange for work that is checked and remembered.
- **How you come back next time.** The same five steps every time — nothing starts by itself, and the
  home folder does not list your projects on its own:

  ```text
  1. ssh <user>@<server>        log in as your working user
  2. tmux attach -t yitc        back into your kept terminal (after a reboot: tmux new -s yitc)
  3. cd ~/<project>             go to the project — or stay in ~ and type /yitc-projects in step 5
  4. <your AI tool>             start the AI tool
  5. "start the project"        say it; the start line "working in YITC mode" must appear
  ```
- **Why a second provider.** A second, different AI provider can later check the first one's work,
  because each misses things the other catches. Recommended, never required — work runs from day one on
  the one AI tool you already have.

### Prerequisites — checked before the install

Your AI checks each of these as the working user and installs only what is missing, with your agreement:

| what | check | if missing |
| --- | --- | --- |
| `git` | `git --version` | Debian/Ubuntu `sudo apt install git` · Fedora/RHEL `sudo dnf install git` · macOS `xcode-select --install` |
| `python3` (3.9+) | `python3 --version` | Debian/Ubuntu `sudo apt install python3` · Fedora/RHEL `sudo dnf install python3` · macOS `brew install python` |
| `PyYAML` (YAML reader for `python3`) | `python3 -c "import yaml"` (silent when present) | Debian/Ubuntu `sudo apt install python3-yaml` · Fedora/RHEL `sudo dnf install python3-pyyaml` · macOS `python3 -m pip install --user pyyaml` |
| `ssh-keygen -Y` (OpenSSH 8.0+, checks the signature) | `ssh-keygen -Y sign` (prints a usage error when supported) | Debian/Ubuntu `sudo apt install openssh-client` · Fedora/RHEL `sudo dnf install openssh-clients` · macOS ships it |

Without `PyYAML`, `release verify` stops with a Python error instead of a verdict; without
`ssh-keygen -Y` there is no signature check at all.

**Where things go.** By default the clone lives in `~/yitc` and the engine is installed into
`~/yitc-engine` (the `<target-dir>` below). **Keep the `~/yitc` clone** after the install — updates are
fetched into it.

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
