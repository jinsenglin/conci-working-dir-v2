# Install

https://concourse.ci/binaries.html

# Prerequisites

```bash
brew install postgresql
brew services start postgresql
createdb atc
```

# Launch

```bash
concourse web \
  --basic-auth-username myuser \
  --basic-auth-password mypass \
  --session-signing-key session_signing_key \
  --tsa-host-key tsa_host_key \
  --tsa-authorized-keys authorized_worker_keys \
  --external-url http://127.0.0.1


sudo concourse worker \
  --work-dir /opt/concourse/worker \
  --tsa-host 127.0.0.1 \
  --tsa-public-key tsa_host_key.pub \
  --tsa-worker-private-key worker_key
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

sudo concourse worker \
  --work-dir /opt/concourse/worker \
  --tsa-host 127.0.0.1 \
  --tsa-public-key tsa_host_key.pub \
  --tsa-worker-private-key worker_key

cd ci/helpers
bash demo.sh
```
