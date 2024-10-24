# WPAD block list for AddGuard
  
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

I found that most of the devices in my home (phones, workstations ( linux and windows ) and servers have tried to do this lookup.   
Most TLD domains have already global sink to 127.0.0.1, aleast for wpad.com and wpad.net. but, this is dependent of owners of the domains so you can never be to sure if owners change.
  
## Ref urls:
- https://www.pcworld.com/article/415991/disable-wpad-now-or-have-your-accounts-and-private-data-compromised.html
- https://en.wikipedia.org/wiki/Web_Proxy_Auto-Discovery_Protocol
- https://www.reddit.com/r/pihole/comments/bgmx9t/wpad_domain_called_over_and_over/
- https://www.reddit.com/r/Adguard/comments/18px2me/is_it_safe_to_block_wapd_queries/
- https://www.youtube.com/watch?v=uwsykPWa5Lc

