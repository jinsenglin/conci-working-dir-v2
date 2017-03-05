# Install

https://concourse.ci/binaries.html

# Launch

```bash
concourse web \
  --basic-auth-username myuser \
  --basic-auth-password mypass \
  --session-signing-key session_signing_key \
  --tsa-host-key tsa_host_key \
  --tsa-authorized-keys authorized_worker_keys \
  --external-url http://127.0.0.1
```

# Demo

```bash
git clone https://github.com/jinsenglin/conci-working-dir-v2.git
cd conci-working-dir-v2
export PATH=$PATH:$PWD

concourse web \
  --basic-auth-username myuser \
  --basic-auth-password mypass \
  --session-signing-key session_signing_key \
  --tsa-host-key tsa_host_key \
  --tsa-authorized-keys authorized_worker_keys \
  --external-url http://127.0.0.1

cd ci/helpers
bash demo.sh
```
