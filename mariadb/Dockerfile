# Inherits from official MariaDB
FROM mariadb:10.1

# Clean image
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Start MariaDB
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["mysqld"]
