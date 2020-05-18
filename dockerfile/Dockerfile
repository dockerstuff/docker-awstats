FROM debian:stretch

RUN DEBIAN_FRONTEND='noninteractive'      && \
    apt-get update                        && \
    apt-get install -y apache2 awstats    && \
    apt-get clean

ADD etc/apache2_awstats.conf /etc/apache2/conf-available/awstats.conf
#ScriptAlias /awstats/ /usr/lib/cgi-bin/
#Alias /awstats-icon/ /usr/share/awstats/icon/
#Alias /awstatsclasses/ /usr/share/java/awstats/
#<Directory "/usr/lib/cgi-bin/">
#    Options None
#    AllowOverride None
#    <IfModule mod_authz_core.c>
#        Require host localhost
#    </IfModule>
#</Directory>

RUN a2enmod cgi && a2enconf awstats

ADD /etc/awstats.conf /etc/awstats/awstats.conf.local
#LogFile="/access.log"
#SiteDomain="localhost"
#AllowToUpdateStatsFromBrowser=1

#ENTRYPOINT while `/bin/true`; do /usr/lib/cgi-bin/awstats.pl -update-config=localhost; sleep 5; done

