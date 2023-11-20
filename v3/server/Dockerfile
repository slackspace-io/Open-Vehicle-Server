FROM perl:latest
# Update package lists and install dependencies
#RUN apt-get update && apt-get install -y wget gnupg lsb-release
#
#RUN apt-key adv --keyserver keys.gnupg.net --recv-keys 467B942D3A79BD29
#
## Add MySQL repository and install MySQL 8.x
#RUN wget https://dev.mysql.com/get/mysql-apt-config_0.8.16-1_all.deb \
#    && dpkg -i mysql-apt-config_0.8.16-1_all.deb \
#    && apt-get update \
#    && apt-get install -y mysql-client-8.0
#RUN apt-get update && \
#    apt-get install -y libdbd-mysql-perl mysql-common

#https://cpan.metacpan.org/authors/id/K/KI/KILINRAX/DBD-mysql-4.018_01.tar.gz
#RUN cpan KILINRAX/DBD-mysql-4.018_01.tar.gz
#RUN cpan DBD::mysql
RUN cpan Config::IniFiles
RUN cpan Digest::MD5
RUN cpan Digest::HMAC
RUN cpan Crypt::RC4::XS
RUN cpan MIME::Base64
RUN cpan EV
RUN cpan AnyEvent
RUN cpan AnyEvent::HTTP
RUN cpan AnyEvent::HTTPD
RUN cpan HTTP::Parser::XS
RUN cpan Data::UUID
RUN cpan Email::MIME
RUN cpan DBI
RUN cpan DVEEDEN/DBD-mysql-4.051.tar.gz
RUN cpan Email::Sender::Simple
RUN cpan Net::SSLeay
RUN cpan JSON::XS
RUN cpan Protocol::WebSocket
RUN cpan Time::Piece

#conf not provided, expected to be provied during deployment
WORKDIR /app
COPY . /app
RUN chmod +x /app/start.sh
EXPOSE 6867
ENTRYPOINT ["/app/start.sh"]
CMD ["perl", "ovms_server.pl"]
