# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
# DNS Enumeration
# DNS Recon


| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```
# OUTPUT:
# SITE:
<img width="1919" height="958" alt="Screenshot 2025-09-08 083345" src="https://github.com/user-attachments/assets/b9f4b8d7-ea25-4436-8b63-e90ac50b4e63" />

# INURL:

<img width="1914" height="952" alt="Screenshot 2025-09-08 084325" src="https://github.com/user-attachments/assets/b7696373-8bae-4d15-be10-cf40d92db1a7" />

# INTITLE:

<img width="1915" height="915" alt="Screenshot 2025-09-08 084353" src="https://github.com/user-attachments/assets/8ec03edf-9563-4929-a82b-f3c300d8c7d8" />

# FILETYPE:

<img width="1918" height="972" alt="Screenshot 2025-09-08 084432" src="https://github.com/user-attachments/assets/878af451-9ae1-4d2a-8d09-73ae4f48ebbe" />

# INTEXT:

<img width="1916" height="976" alt="Screenshot 2025-09-08 084758" src="https://github.com/user-attachments/assets/f49fc76a-b171-4adb-8e21-431da64dd037" />

# LINK:

<img width="1903" height="955" alt="Screenshot 2025-09-08 084829" src="https://github.com/user-attachments/assets/c8c4a7b7-5e6d-4c93-87a3-0d5697718ea1" />

# CACHE:

<img width="1918" height="970" alt="Screenshot 2025-09-08 084904" src="https://github.com/user-attachments/assets/f04414be-0c55-47c4-bf92-67ce0dbccb5c" />

# EXT:

<img width="1919" height="932" alt="Screenshot 2025-09-08 084941" src="https://github.com/user-attachments/assets/9819ac0c-3649-492c-8769-4e64d7180514" />

# DNS Enumeration

<img width="586" height="661" alt="Screenshot 2025-09-13 083325" src="https://github.com/user-attachments/assets/8f7b8010-0975-43d1-a18e-5996a21f0f97" />

## DNS Recon

<img width="382" height="371" alt="Screenshot 2025-09-13 083449" src="https://github.com/user-attachments/assets/364d4931-b682-4e14-8de6-64cd86566469" />

# dns recon

provides the ability to perform: Check all NS records for zone transfers Enumerate general DNS records for a given domain (MX, SOA, NS, A, AAAA, SPF , TXT) Perform common SRV Record Enumeration Top level domain expansion

<img width="586" height="661" alt="Screenshot 2025-09-13 083325" src="https://github.com/user-attachments/assets/f7ee5e82-ef1f-4e09-a1a5-a283d64ac2ea" />
<img width="712" height="449" alt="Screenshot 2025-09-13 083501" src="https://github.com/user-attachments/assets/812a9901-dd81-4791-98dd-14bf1ca43ca4" />



## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:
<img width="688" height="701" alt="Screenshot 2025-09-13 083601" src="https://github.com/user-attachments/assets/76b06bd8-903b-4bc3-b15e-a73716aea34d" />



## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
  
<img width="863" height="529" alt="Screenshot 2025-09-13 083723" src="https://github.com/user-attachments/assets/47ac6c6b-7d74-4362-9242-5e9044e615c7" />

<img width="668" height="351" alt="Screenshot 2025-09-13 083900" src="https://github.com/user-attachments/assets/0e452c37-90f9-4140-be0b-a33d069fd1e2" />

# telnet for smtp enumeration
<img width="446" height="115" alt="Screenshot 2025-09-13 083951" src="https://github.com/user-attachments/assets/9ec853f6-7359-4b8e-8011-f24694b28be8" />

## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:


<img width="756" height="103" alt="Screenshot 2025-09-13 091016" src="https://github.com/user-attachments/assets/57cca69b-3b67-4bb1-8bfb-a2ad42e3e825" />

## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
