ARG MYSQL_VERSION=5.6
FROM mysql:${MYSQL_VERSION}

LABEL maintainer="Abdelrahman Omran <me@omranic.com>"

# Install nano
RUN apt-get update && apt-get install -y --no-install-recommends nano && rm -rf /var/lib/apt/lists/*
# Set Timezone
#####################################
ARG TZ=UTC
ENV TZ ${TZ}

# Fix filesystem permissions
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone && chown -R mysql:root /var/lib/mysql/

# Copy config file
COPY my.cnf /etc/mysql/conf.d/my.cnf
