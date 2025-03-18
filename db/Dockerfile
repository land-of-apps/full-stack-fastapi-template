FROM postgres:12

# Add healthcheck
HEALTHCHECK --interval=10s --timeout=5s --start-period=30s --retries=5 \
  CMD pg_isready -U postgres -d postgres || exit 1

# Set environment variables
ENV POSTGRES_PASSWORD=postgres \
  POSTGRES_USER=postgres \
  POSTGRES_DB=postgres \
  PGDATA=/var/lib/postgresql/data/pgdata

# Create directory for PostgreSQL data
RUN mkdir -p /var/lib/postgresql/data/pgdata
RUN chown -R postgres:postgres /var/lib/postgresql/data/pgdata

# Expose PostgreSQL port
EXPOSE 5432

# Set the default command
CMD ["postgres"]
