## gasmask

All in one Information gathering tool - OSINT

Written by: [maldevel](https://github.com/maldevel) ([twitter](https://twitter.com/maldevel))

---

### Dependencies

* Python 2.x
* validators
* python-whois
* dnspython
* requests

### Information Gathering

* ask
* bing
* crt
* dns
* dnsdumpster
* dogpile
* github
* google
* googleplus
* instagram
* linkedin
* censys.io
* netcraft
* pgp
* reddit
* reverse dns
* twitter
* vhosts
* virustotal
* whois
* yahoo
* yandex
* youtube

---

### Dependencies

```
sudo pip install -r requirements.txt
```

---

### Usage

```
    ______           __  ___           __ __
  / ____/___ ______/  |/  /___ ______/ //_/
 / / __/ __ `/ ___/ /|_/ / __ `/ ___/ ,<
/ /_/ / /_/ (__  ) /  / / /_/ (__  ) /| |
\____/\__,_/____/_/  /_/\__,_/____/_/ |_|

GasMasK - All in one Information gathering tool - OSINT
Ver. 1.0
Written by: @maldevel
https://www.twelvesec.com/

usage: gasmask.py [-h] [-d DOMAIN] [-s NAMESERVER] [-x PROXY] [-l LIMIT]
                  [-i MODE] [-o BASENAME] [-m MATCH] [-f FILTER] [--count]
                  [-R REPORT] [-B REPORT_BUCKET] [-1 CENSYS_API_ID]
                  [-2 CENSYS_API_SECRET] [-r] [-u] [-a ASN] [-c COUNTRY]
                  [-O CERT_ORG] [-I CERT_ISSUER] [-z CERT_HOST]
                  [-S HTTP_SERVER] [-t HTML_TITLE] [-b HTML_BODY] [-T TAGS]
                  [-L LIMIT] [-D] [-v] [-H]
                  [arguments [arguments ...]]

positional arguments:
  arguments             Censys query

optional arguments:
  -h, --help            show this help message and exit
  -d DOMAIN, --domain DOMAIN
                        Domain to search.
  -s NAMESERVER, --server NAMESERVER
                        DNS server to use.
  -x PROXY, --proxy PROXY
                        Use a proxy server when retrieving results from search engines (eg. '-x http://127.0.0.1:8080')
  -l LIMIT, --limit LIMIT
                        Limit the number of search engine results (default: 100).
  -i MODE, --info MODE  Limit information gathering (basic,whois,dns,revdns,vhosts,google,bing,yahoo,ask,dogpile,yandex,censys,linkedin,twitter,googleplus,youtube,reddit,github,instagram,crt,pgp,netcraft,virustotal,dnsdump).
  -o BASENAME, --output BASENAME
                        Output in the four major formats at once (markdown, txt, xml and html).
  -m MATCH, --match MATCH
                        Highlight a string within an existing query result
  -f FILTER, --filter FILTER
                        Filter the JSON keys to display for each result (use value 'help' for interesting fields)
  --count               Print the count result and exit
  -R REPORT, --report REPORT
                        Stats on given field (use value 'help' for listing interesting fields)
  -B REPORT_BUCKET, --report_bucket REPORT_BUCKET
                        Bucket len in report mode (default: 50)
  -1 CENSYS_API_ID, --censys_api_id CENSYS_API_ID
                        Provide the authentication ID for the censys.io search engine
  -2 CENSYS_API_SECRET, --censys_api_secret CENSYS_API_SECRET
                        Provide the secret hash for the censys.io search engine
  -r, --read_api_keys   Read the API Keys stored in api_keys.txt file. (e.g. '-i censys -r')
  -u, --update_api_keys
                        Update the API Keys stored in api_keys.txt file. (e.g. '-i censys -u')
  -a ASN, --asn ASN     Filter with ASN (ex: 5408 for GR-NET AS)
  -c COUNTRY, --country COUNTRY
                        Filter with country
  -O CERT_ORG, --cert-org CERT_ORG
                        Certificate issued to organization
  -I CERT_ISSUER, --cert-issuer CERT_ISSUER
                        Certificate issued by organization
  -z CERT_HOST, --cert-host CERT_HOST
                        hostname Certificate is issued to
  -S HTTP_SERVER, --http-server HTTP_SERVER
                        Server header
  -t HTML_TITLE, --html-title HTML_TITLE
                        Filter on html page title
  -b HTML_BODY, --html-body HTML_BODY
                        Filter on html body content
  -T TAGS, --tags TAGS  Filter on specific tags. e.g: -T tag1,tag2,... (use keyword 'list' to list usual tags
  -L LIMIT, --Limit LIMIT
                        Limit to N results ( for censys.io )
  -D, --debug           Debug informations
  -v, --verbose         Print raw JSON records
  -H, --html            Renders html elements in a browser

```

---

### Usage Examples

```
python gasmask.py -d example.com -i basic

python gasmask.py -d example.com -i dnsdump

python gasmask.py -d example.com -i whois,dns,revdns

python gasmask.py -d example.com -i basic,yahoo,github -o myresults/example_com_search_results

```

### censys.io usage examples 

```

python gasmask.py -i censys --Limit 10 nessus

python gasmask.py -i censys -I JBOSS --report location.country.raw --report_bucket 10

python gasmask.py -i censys --html-title "Padding Oracle" --Limit 10 --html

python gasmask.py -i censys --tags heartbleed --report location.country.raw

python gasmask.py -i censys -S NGINX --count

python gasmask.py -i censys -d example.com

python gasmask.py -i censys -t "Internal Server Error" -S Apache -m "HTTP 500" --Limit 15


```

### Read the API Keys usage example - e.g in censys.io  

```
python gasmask.py -i censys -r 

```

### Update the API Keys usage example - e.g in censys.io  

```
python gasmask.py -i censys -u 

```

---

### Credits

* [EmailHarvester](https://github.com/maldevel/EmailHarvester)
* [theHarvester](https://github.com/laramies/theHarvester)
* [Sublist3r](https://github.com/aboul3la/Sublist3r)
* [gelim](https://github.com/gelim/censys)

---
