#FROM mysql:8
# When running on ARM64 use MariaDB instead of MySQL
FROM mariadb:latest
ENV force_color_prompt yes

RUN apt-get update;
RUN apt-get install -y cron;

ENTRYPOINT \
  service cron start; \
  printenv | grep -v "no_proxy" >> /etc/environment; \
  docker-entrypoint.sh mysqld
