# Use Oracle Linux 8 as base image
FROM oraclelinux:8

# Set environment variables for Oracle Instant Client
ENV LD_LIBRARY_PATH=/usr/lib/oracle/23/client64/lib \
    PATH=/usr/lib/oracle/23/client64/bin:$PATH

# Install Oracle Instant Client
RUN dnf -y install oracle-release-el8 && \
    dnf config-manager --enable ol8_oracle_instantclient && \
    dnf -y install oracle-instantclient-release-23ai-el8 && \
    dnf -y install oracle-instantclient-basic && \
    dnf -y install oracle-instantclient-sqlplus && \
    dnf -y install git && \
    dnf clean all

# Verify installation by printing sqlplus version
CMD ["sqlplus", "-v"]
