# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000

# Dev environment

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# dev scripts and tools in path
ENV PATH="/transport/dev:${PATH}"

RUN apt-get update

RUN apt-get install apt-utils -y \
  && apt-get install -y language-pack-en-base \
  && locale-gen en_US en_US.UTF-8 \
  && dpkg-reconfigure locales

RUN apt-get install -y --no-install-recommends \
  apt-transport-https \
  ca-certificates \
  clang \    
  curl \
  file \
  ftp \
  git \
  gnupg \
  iproute2 \
  iputils-ping \
  libicu-dev \
  net-tools \
  openssl \
  openssh-client \
  sudo \
  telnet \
  time \
  unzip \
  wget \
  zip \
  # Cleanup temporary data and cache
  && apt-get clean \
  && apt-get autoclean

# Install MS SQL Server client tools (https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-2017)
# Accept EULA - needed for certain Microsoft packages like SQL Server Client Tools
ENV ACCEPT_EULA=Y
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
  && curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list | tee /etc/apt/sources.list.d/msprod.list \
  && apt-get update \
  && apt-get install -y mssql-tools unixodbc-dev \
  && rm -rf /var/lib/apt/lists/* \
  && rm -rf /etc/apt/sources.list.d/* \
  || echo -n
ENV PATH=$PATH:/opt/mssql-tools/bin

# Install Docker
ENV DOCKER_VERSION 18.03.1-ce
RUN curl -fsSLO https://download.docker.com/linux/static/stable/x86_64/docker-$DOCKER_VERSION.tgz \
  && tar --strip-components=1 -xvzf docker-18.03.1-ce.tgz -C /usr/local/bin
RUN rm docker-$DOCKER_VERSION.tgz

ENV COMPOSE_VERSION "1.22.0"

# Install latest docker-compose from releases
RUN curl -L "https://github.com/docker/compose/releases/download/$COMPOSE_VERSION/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose

# https://dotnet.microsoft.com/download/dotnet-core/3.0

#dotnet sdk
RUN mkdir dotnetsdk && wget https://dot.net/v1/dotnet-install.sh
ENV PATH="/dotnetsdk:${PATH}"
RUN bash dotnet-install.sh --channel 2.1 --install-dir dotnetsdk --version 2.1.700
RUN bash dotnet-install.sh --channel 3.0 --install-dir dotnetsdk --version 3.0.100-preview6-012264

# dotnet runtime
RUN mkdir /usr/share/dotnet
RUN bash dotnet-install.sh --channel 3.0 --runtime dotnet --install-dir /usr/share/dotnet --version 3.0.0-preview6-27804-01
RUN bash dotnet-install.sh --channel 3.0 --runtime aspnetcore --install-dir /usr/share/dotnet --version 3.0.0-preview6.19307.2

EXPOSE 7000-8000
