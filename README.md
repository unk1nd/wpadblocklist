# wpad block list for addguard
  
Filter for stopping potential man-in-the-middle (MitM) by sending lookups to DNS with use of the Web Proxy Auto-Discovery Protocol  
This filter sets all DNS lookups for the DNS triversal of wpad.* lookups to 0.0.0.0
  
## Why shoud i do this? 
Before fetching its first page, a web browser implementing this method sends a 
DHCPINFORM query to the local DHCP server, and uses the URL from the WPAD option in 
the servers reply. If the DHCP server does not provide the desired information, DNS is used. 
If, for example, the network name of the users computer 
is pc.department.branch.example.com, the browser will 
try the following URLs in turn until it finds a proxy configuration file within the domain of the client:   
  
- http://wpad.department.branch.example.com/wpad.dat
- http://wpad.branch.example.com/wpad.dat
- http://wpad.example.com/wpad.dat
- http://wpad.com/wpad.dat (in incorrect implementations, see Security section on wikipedia and youtube video in ref urls below )
  
## Ref urls:
- https://www.pcworld.com/article/415991/disable-wpad-now-or-have-your-accounts-and-private-data-compromised.html
- https://en.wikipedia.org/wiki/Web_Proxy_Auto-Discovery_Protocol
- https://www.reddit.com/r/pihole/comments/bgmx9t/wpad_domain_called_over_and_over/
- https://www.reddit.com/r/Adguard/comments/18px2me/is_it_safe_to_block_wapd_queries/
- https://www.youtube.com/watch?v=uwsykPWa5Lc

