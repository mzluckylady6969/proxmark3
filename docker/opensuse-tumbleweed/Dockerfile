FROM opensuse/tumbleweed

ENV LANG C
# libqt5-qtbase-devel skipped
RUN zypper --non-interactive install --no-recommends shadow sudo git patterns-devel-base-devel_basis gcc-c++ readline-devel libbz2-devel bluez-devel python3-devel libopenssl-devel cross-arm-none-gcc11 cross-arm-none-newlib-devel

RUN zypper --non-interactive install cmake python3 python3-pip
RUN python3 -m pip install ansicolors sslcrypto

# Create rrg user
RUN useradd -ms /bin/bash rrg
RUN passwd -d rrg
RUN printf 'rrg ALL=(ALL) NOPASSWD: ALL\n' | tee -a /etc/sudoers

USER rrg
WORKDIR "/home/rrg"

CMD ["/bin/bash"]
