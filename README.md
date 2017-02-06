acl url1 dstdomain -i 127.0.0.1
acl url2 dstdomain -i localhost
acl url3 dstdomain -i yaakovserver.sytes.net
acl payload dstdomain -i "/etc/squid3/payload.txt"

http_access allow url1
http_access allow url2
http_access allow url3
http_access allow payload

http_access deny all

http_port 8080
http_port 80
http_port 443
http_port 3128


visible_hostname yaakovsaint

forwarded_for off
via off
