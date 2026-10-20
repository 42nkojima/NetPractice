*This project has been created as part of the 42 curriculum by nkojima.*

# NetPractice

## Description

NetPractice is a practical introduction to computer networking.
The goal is to repair 10 small simulated networks so that every host can reach
the destinations listed as goals for that level.
Each level shows a network diagram that does not work yet.
You fix it by editing the unshaded fields: IP addresses, subnet masks, and
routing table entries (destinations and next hops) on hosts, routers, and the
Internet.

The levels get progressively harder:

- **Levels 1–5**: hosts on the same network, switches, a first router, and
  default gateways.
- **Levels 6–10**: routing tables across several routers and the Internet,
  return paths, and splitting address blocks into subnets that do not
  overlap.

The networks are simulated in a training interface that runs in the web
browser. No real network equipment is configured.

## Instructions

### Running the training interface

1. Download `net_practice.1.9.tgz` from the project page and extract it:

   ```sh
   tar xzf net_practice.1.9.tgz
   ```

2. Start the local web server:

   ```sh
   cd net_practice
   ./run.sh
   ```

   The script finds a free port, starts `python3 -m http.server`, and opens
   the browser.
   If it fails, start the server manually and open the URL yourself:

   ```sh
   python3 -m http.server 49242
   # then open http://localhost:49242
   ```

3. Enter your 42 login in the field on the home page.
   The configuration of each level is generated from this login.

4. For a randomly generated configuration, as used during the defense, use
   the **evaluation** tab instead.

### Solving a level and exporting the configuration

1. Edit the unshaded fields until the network works.
2. Click **Check again** to test the configuration.
   The logs at the bottom of the page explain what is still wrong, for example
   a missing gateway or an invalid address.
3. When the level is solved, click **Get my config** *before* moving on.
   This downloads `levelN.json` for the current level.

### Submission requirements

- The 10 exported configuration files (one per level), from `level1.json`
  to `level10.json`, must be placed at the **root** of this repository.
- They must be exported with your own login entered in the interface.
- During the defense, three random levels must be solved within a limited
  time, with no external tools (a simple calculator such as `bc` is the
  limit).

## Resources

### Networking concepts studied

- **TCP/IP addressing**: IPv4 addresses, the network part and the host part,
  network and broadcast addresses, and the usable host range.
- **Subnet masks and CIDR notation**: converting between `/n` and dotted
  masks, block sizes, and splitting a block into subnets that do not
  overlap.
- **Default gateway**: how a host sends traffic for other networks to its
  router.
- **Routers and switches**: a switch connects devices inside one network,
  and a router connects separate networks and forwards packets between them.
- **Routing tables**: destination network, next hop, and the `default` route
  (`0.0.0.0/0`).
  Routes must exist in both directions so that replies can come back.
- **Public and private address ranges** (RFC 1918), and why private addresses
  are not routed on the Internet.
- **OSI model**: where switches (layer 2, data link) and routers (layer 3,
  network) work.

### References

- [NetPractice guide (tsunanko)](https://tsunanko.github.io/netpractice-guide/):
  networking basics, level walkthroughs, and defense preparation.
- [RFC 791: Internet Protocol](https://www.rfc-editor.org/rfc/rfc791)
- [RFC 4632: Classless Inter-domain Routing (CIDR)](https://www.rfc-editor.org/rfc/rfc4632)
- [RFC 1918: Address Allocation for Private Internets](https://www.rfc-editor.org/rfc/rfc1918)
- [Cloudflare Learning: What is the OSI model?](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)

### Use of AI

AI (Claude) was used for:

- Planning the study schedule from the subject and choosing which concepts
  to focus on for levels 6–10.
- Drafting this README and the `.gitignore`.

All levels were solved by hand, without AI.
Every answer was checked in the training interface and can be explained
during the defense.
