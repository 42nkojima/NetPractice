*This project has been created as part of the 42 curriculum by nkojima.*

# NetPractice

## Description

NetPractice is an introduction to computer networking through 10 levels of
simulated networks that do not work yet.
Each level is solved by setting IP addresses, subnet masks, and routing
tables so that every goal of the level is reached.

## Instructions

Extract the archive from the project page and start the training interface:

```sh
tar xzf net_practice.*.tgz
cd net_practice && ./run.sh
```

If `run.sh` fails, run `python3 -m http.server 49242` and open
`http://localhost:49242`.

1. Enter your 42 login on the home page.
   The **evaluation** tab generates random levels instead.
2. Edit the unshaded fields and click **Check again**.
   The logs at the bottom show what is still wrong.
3. Once a level is solved, click **Get my config** to download `levelN.json`.

**Submission:** the 10 exported files (`level1.json` to `level10.json`, one
per level, exported with your own login) must be placed at the repository
root.

## Resources

Concepts studied: TCP/IP addressing, subnet masks and CIDR, default gateways,
routers and switches, routing tables, private address ranges, and the OSI
layers (switches work at layer 2, routers at layer 3).

- [NetPractice guide (tsunanko)](https://tsunanko.github.io/netpractice-guide/)
- [RFC 4632: Classless Inter-domain Routing (CIDR)](https://www.rfc-editor.org/rfc/rfc4632)
- [RFC 1918: Address Allocation for Private Internets](https://www.rfc-editor.org/rfc/rfc1918)
- [Cloudflare Learning: What is the OSI model?](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)

**Use of AI:** Claude was used to plan the study schedule and to draft this
README and the `.gitignore`.
All levels were solved by hand, without AI.
