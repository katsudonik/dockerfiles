FROM mysql:5.7.24

RUN apt-get update && \
    apt-get install -y locales && \
    rm -rf /var/lib/apt/lists/* && \
    echo "ja_JP.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen ja_JP.UTF-8
ENV LC_ALL ja_JP.UTF-8

RUN { \
    echo '[mysqld]'; \
    echo 'character-set-server=utf8mb4'; \
    echo 'collation-server=utf8mb4_general_ci'; \
    echo 'sql_mode = NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION'; \
    echo 'general_log=1'; \
    echo 'general_log_file=/tmp/mysql-query.log'; \
    echo '[client]'; \
    echo 'default-character-set=utf8mb4'; \
} > /etc/mysql/conf.d/charset.cnf
