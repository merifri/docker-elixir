FROM elixir:1.6.5

RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main" > /etc/apt/sources.list.d/pgdg.list \
    && wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - \
    && curl -sL https://deb.nodesource.com/setup_8.x | bash - \
    && wget --quiet -O libssl1.0.0.deb "http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.0.0_1.0.1t-1+deb8u8_amd64.deb" \
    && dpkg -i libssl1.0.0.deb && apt-get update -qq \
    && apt-get install -y postgresql-client-10 libpq5 libpq-dev nodejs python-pip python-dev groff locales

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && locale-gen
ENV LC_ALL en_US.utf8

CMD ["iex"]
