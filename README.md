![My Pi-hole Dashboard Stats](https://github.com/stevejenkins/pi-hole-lists/blob/main/dashboard.jpg?raw=true)

# My Personal Pi-hole LoL (List of Lists)
This is not a blocklist. Rather, it's a list of the blocklists, whitelists, and regular expressions I use to configure my Pi-hole servers. A "list of lists," if you will. Feel free to browse through my choices, research them, then decide which to add to your own. Or not. This combination works extremely well for me and I hope it can also work well for you.

"Which blocklists do you use?" is a common recurring question on Reddit and other Pi-hole discussion areas. Another purpose of this repo is to have somewhere quick and easy to point to as an answer to that question.

My goal isn't to have as high a number of blocked hosts as possible. Instead, it's to optimize performance while still passing the "family test" where people aren't constantly complaining about the Pi-hole blocking them.

# The Lists
- [`blocklists.txt`](https://github.com/stevejenkins/pi-hole-lists/blob/main/blocklists.txt) - The blocklists I use to limit ads and tracking on my networks
- [`whitelists.txt`](https://github.com/stevejenkins/pi-hole-lists/blob/main/whitelists.txt) - The whitelists I use to allow access to specific services
- [`regex.txt`](https://github.com/stevejenkins/pi-hole-lists/blob/main/regex.txt) - The regular expressions I use to both block and allow traffic, based on patterns in their name (including wildcard domains)

# How / Why I Chose These Lists
This particular selection of lists and regex statements are the result of years of trial and error across multiple residential networks. My goal isn't to have as high a number of blocked hosts as possible. Instead, the goal is optimize performance while still passing the "family test" where people aren't constantly complaining about the Pi-hole blocking them. 

- [Blocklists](https://github.com/stevejenkins/pi-hole-lists/blob/main/blocklists.txt): The "heavy lifting" is performed by well-known blocklists from [StevenBlack](https://github.com/StevenBlack/hosts), [Hegezi](https://github.com/hagezi/dns-blocklists), [UBlockOrigin](https://github.com/uBlockOrigin/uAssets), [URLHaus](https://urlhaus.abuse.ch/), [OSID](https://oisd.nl/), and others. I've chosen lists with a slightly higher chance of false positives, but then mitigate the impact with some whitelisting.

- [Whitelists](https://github.com/stevejenkins/pi-hole-lists/blob/main/whitelists.txt): So far, I'm only using one whitelist: Hegezi's affiliate & tracking referral links that enables links in emails and search results, etc. No need to include this list if those types of referral links aren't important in your household.
  
- [Regex](https://github.com/stevejenkins/pi-hole-lists/blob/main/regex.txt) The regular expressions list is divided into two sections: DENY and ALLOW. The DENY section uses regular expressions to block tracking domains that include words like 'beacon" or "counter" or "affiliates." The original version of this list also blocked domains including "trackers" and "traffic" but that blocked playback of a number of podcasts so those two entries are commented out. The entires in the ALLOW section are individually commented to explain their use. Most are in place to reduce false positives from the DENY regex, but also to whitelist some specific domains that my household accesses frequently.

Use at your own risk.

More information on the Pi-hole application and how to use these files at: https://pi-hole.net/
