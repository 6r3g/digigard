---
{"dg-publish":true,"dg-permalink":"writeup/rootme10k/applicativesaretheway","permalink":"/writeup/rootme10k/applicativesaretheway/","dgPassFrontmatter":true}
---

# rootme10k

## Applicatives are the way

Requêtes dns :
```shell
tshark -nr applicatives_are_the_way.pcapng -T fields -e dns.qry.name -Y 'dns.qry.name contains ".bwlryq"' | uniq | cut -d. -f 1 | tee | base64 -d
I lostMyPassw0rd...ButImSureThAtItIsNtS0FaR#    
```

Requêtes ICMP et bon mot de passe :
```shell
tshark -nr applicatives_are_the_way.pcapng -Y "icmp.type == 8" -T fields -e data.text > passwords.txt && fcrackzip -u -v -D -p ./passwords.txt flag.zip
found file 'flag.txt', (size cp/uc     50/    36, flags 9, chk 9548)

PASSWORD FOUND!!!!: pw == VKQ*{8cD]ZpfZn
```

Unzip et flag
```bash
unzip -P "VKQ*{8cD]ZpfZn" flag.zip && cat flag.txt
Archive:  flag.zip
  inflating: flag.txt
RM{W1r3Sh4rk_R3@lly_Is_Y0uR_Th1ng:)}#                      
```

xxx
