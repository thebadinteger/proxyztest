<h1 align="center">proxyz</h1>  
<p align="center">
  <img src="https://img.shields.io/badge/Go-1.24%2B-blue?style=flat&logo=go&logoColor=white" alt="Go"/>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-green" alt="Go"/>
  <img src="https://img.shields.io/github/license/thebadinteger/proxyz" alt="License"/>
</p>  
<h3 align="center">Multithreaded proxy checker and scraper</h3>  

<div align="center"><img src="https://raw.githubusercontent.com/thebadinteger/proxyztest/refs/heads/main/proxyzblue.png" alt="Preview" width="128"></div>

## Features:  
- Multithreaded 
- Protocol support: `HTTP, HTTPS, SOCKS4, SOCKS5` 
- Authorization support 
- User-Agent configuration 
- Geolocation filtering 
- Anti-duplicate 

## Installation:  
```shell
git clone https://github.com/thebadinteger/proxyz.git
cd proxyz
go build
```  
Or download the latest binary from the **[Releases page](https://github.com/thebadinteger/proxyz/releases/latest)**.

## Configuration:  
- `config.json`  
Scrape sources config format:  
```
  "sources": {
    "protocol": [
    "source",
    "source",
    "source"
    ]
  }
```
User-agents config format:  
```
  "useragents": [
    "user-agent",
    "user-agent",
    "user-agent"
  ]
```

## Usage:  
```shell
./proxyz -s -c -p [protocol] -i [input] -o [output] -t [threads] -w [timeout] -a -l [IP/URL] -g [geolocation]
```
```
[-s, --scrape] Scrape proxies - arguments: -p, -o (required) -c (optional)
[-c, --check] Check proxies - arguments: -i, -p, -o (required) -t, -w, -a, -l, -g (optional)
[-p, --protocol] Proxy protocols - all/http,https,socks4,socks5 (default: all)
[-i, --input] Path to input file
[-o, --output] Path to output file
[-t, --threads] Number of check threads (default: 256)
[-w, --timeout] Check timeout in ms (default: 7200)
[-a, --apart] Add protocol to check output
[-l, --lab] Target (URL or IP) for proxy checking (default: http://api.ipify.org)
[-g, --geo] Proxy geolocation(s), 2-letter country code 'RU,US,GB' or with "-" to exclude '-CN,-JP'
[-d, --debug] Log everything
```  

**Input format:**  
```
ip:port
login:password@ip:port
protocol://ip:port
protocol://login:password@ip:port
```  
**Output format:**  
Default:  
```
ip:port
login:password@ip:port
```  
With protocol (-a):  
```
protocol://ip:port
protocol://login:password@ip:port
```  

### Credits:  
Made by badinteger `[GPL v3.0 License]`
