FROM perl:latest

RUN cpan Config::IniFiles
RUN cpan Digest::MD5
RUN cpan Digest::HMAC
RUN cpan Crypt::RC4::XS
RUN cpan MIME::Base64
RUN cpan DBI
RUN cpan DBD::mariaDB
RUN cpan EV
RUN cpan AnyEvent
RUN cpan AnyEvent::HTTP
RUN cpan AnyEvent::HTTPD
RUN cpan HTTP::Parser::XS
RUN cpan Data::UUID
RUN cpan Email::MIME
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
