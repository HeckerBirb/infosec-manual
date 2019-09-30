# How to contribute
Please follow the following guidelines when contributing articles to the manual (if the specific article does not yet exist, feel free to create it).

## Naming conventions
Article names must use the following naming convention: 
```
[popular_low_port, ][popular_high_port, ]service_protocol_or_concept
```
For example:
* 22, SSH
* 80, 443, HTTP/HTTPS
* Linux Privesc

Note: the low and high ports can be specified as port ranges, e.g. "4444-5555, My Service".


## Network services (i.e. service behind a port)
Please include the following sections in your contibutions:
* Title of very few words describing the vulnerability/misconfiguration (e.g. "Misconfigured sudo permissions" or "SQL Injections").
* Short description of what to check and why.
* Example command(s) in clear, readable format (cryptic commands may be suspected harmful and rejected).
* (If it makes sense) mitigation guidelines describing how to prevent or fix the vulnerability/misconfiguration.

For ease of contribution and consistency, please use the provided template at the bottom of this page.

## What to do if...
### ...more than one common port exists
* If an article for the service exists already, but not all ports are listed (e.g. RPC), please use that article.
* If neither the service name nor the relevant ports are present in the directory name, please create a new article following the naming convention.


## Template for new contributions
For new articles:
````
# < Title of article, following the naming convention above >
## < Short title of vulnerability or misconfiguration >
< Short introduction here >

### Example commands
```
$ command1
$ command2
```

### Sample output
```
$ command1
< output >

$ command2
< output >
```

### Suggested mitigations
[ BLANK IF NONE | < suggestions > ]
````

For existing articles, use the above but leave out the header-1 title.
