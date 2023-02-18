#### <a href="https://github.com/OWASP/Amass">amass</a>
``amass enum -brute -passive -d target.com -o amass-passive_target.txt -config ~/.config/amass/config.ini``
> configure the ini file at the least with free apis[GitHub,IPinfo,Censys,SecurityTrails]


#### <a href="https://github.com/resyncgg/ripgen">ripgen</a>
``ripgen -d amass-passive_target.txt > target-ripgened.txt``


#### <a href="https://github.com/trickest/resolvers">resolvers</a>
``wget https://raw.githubusercontent.com/trickest/resolvers/main/resolvers.txt``


#### <a href="https://github.com/d3mondev/puredns">puredns</a>
``puredns resolve target-ripgened.txt -r resolvers.txt -w target_purednsed.txt``


#### <a href="https://github.com/projectdiscovery/httpx">httpx</a>
``httpx --list target_purednsed.txt -silent -probe > target_subdomains.txt``


#### <a href="https://github.com/FortyNorthSecurity/EyeWitness">EyeWitness</a>
``./EyeWitness.py -f target_subdomains.txt``

