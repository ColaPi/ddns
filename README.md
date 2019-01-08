# noip-rpi

This project is based on [freemyip](https://freemyip.com/) which is free dynamic DNS. No login required. No ads, newsletters, links to click, expiration dates, etc.

# setup

* If you have an always-on Linux on your network (or Raspbian on Raspberry Pi), you can install a cron job that will automatically update your IP address every 20 minutes. Make sure you have the "curl" command installed, and then execute the following command:  
`
(crontab -l;echo "*/19 * * * * curl \"https://freemyip.com/update?token=YOUR_TOKEN&domain=YOUR_DOMAIN.freemyip.com\">/dev/null 2>&1")|crontab -
`

* You can set a CNAME record inside your own domain to point to your subdomain at freemyip.com. For example, assuming you own example.com, in the zone file for your domain, you would need to set this record:  
`my.example.com.   CNAME  YOUR_DOMAIN.freemyip.com.`