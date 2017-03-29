FROM buildpack-deps:jessie

RUN apt-get update && apt-get install sudo -y \
 && curl -sSf https://static.rust-lang.org/rustup.sh | sh \
 && cargo install --git https://github.com/paritytech/parity.git parity --tag v1.6.5 \
 && strip /root/.cargo/bin/parity \
 && cp -v /root/.cargo/bin/parity /usr/local/bin/ \
 && /usr/local/lib/rustlib/uninstall.sh \
 && rm -rf /root/.cargo/ \
 && SUDO_FORCE_REMOVE=yes apt-get remove sudo -y \
 && rm -rf /var/lib/apt/lists/*
