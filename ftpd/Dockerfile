FROM stilliard/pure-ftpd

ENV PUBLICHOST localhost

RUN (echo ons; echo ons) | pure-pw useradd ons -d /home/ftpusers/test -u ftpuser
RUN pure-pw mkdb

CMD /run.sh -c 50 -C 50 -l puredb:/etc/pure-ftpd/pureftpd.pdb -E -j -R -P $PUBLICHOST -p 30000:30099

EXPOSE 21 30000-30099

