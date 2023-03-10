### recon tools
#### <a href="https://github.com/OWASP/Amass">amass</a>
``amass enum -brute -passive -d target.com -o amass-passive_target.txt -config ~/.config/amass/config.ini``
> configure the ini file at the least with free apis[GitHub, IPinfo, Censys, SecurityTrails]


#### <a href="https://github.com/resyncgg/ripgen">ripgen</a>
``ripgen -d amass-passive_target.txt > target-ripgened.txt``


#### <a href="https://github.com/trickest/resolvers">resolvers</a>
``wget https://raw.githubusercontent.com/trickest/resolvers/main/resolvers.txt``


#### <a href="https://github.com/d3mondev/puredns">puredns</a>
``puredns resolve target-ripgened.txt -r resolvers.txt -w target_purednsed.txt``


#### <a href="https://github.com/projectdiscovery/httpx">httpx</a>
``httpx --list target_purednsed.txt -silent -probe > httpxed_subdomains.txt``

#### <a href="https://github.com/tomnomnom/assetfinder">assetfinder</a>
``assetfinder -subs-only datacamp.com | httpx -silent -probe >> httpxed_subdomains.txt``

``sort -u httpxed_subdomains.txt > target_subdomains.txt``


#### <a href="https://github.com/FortyNorthSecurity/EyeWitness">EyeWitness</a>
``./EyeWitness.py -f target_subdomains.txt``

### other important tools
#### <a href="https://www.google.com">google</a>

#### <a href="https://portswigger.net/burp/communitydownload">burpSuite community</a> 

#### <a href="https://github.com/ffuf/ffuf">ffuf</a>

#### <a href="https://github.com/assetnote/kiterunner">kiterunner</a>

#### <a href="https://github.com/daffainfo/AllAboutBugBounty">payloads & bypasses</a>

#### <a href="https://a.co/d/fECJopO">The Web Application Hacker's Handbook</a>
