**English** · [Castellano](README.es.md) · [Euskara](README.eu.md)

# RedPi Tools

Custom Python security-audit toolkit built for the **RedPi** project — a
simulated enterprise network (LAN / DMZ / WAN) used to learn and demonstrate
network security. The toolkit is menu-driven and split into defensive and
offensive tools.

> ⚠️ **Authorized / educational use only.** These tools were written for a
> self-built, isolated lab as part of a vocational cybersecurity project. Use
> them only against systems you own or have explicit written permission to test.
> Running them against systems you don't control may be illegal.

Part of the [RedPi project](https://iraitzaristi.github.io) · full write-up and
documentation there.

## Tools

**Defensive** (`defentsa/`)
- `mysql_kudeaketa.py` — MySQL database management interface.
- `pasahitz_analizatzailea.py` — password-strength analyzer for stored credentials.
- `pasahitz_generadorea.py` — strong password generator (hashes output with SHA-256).

**Offensive** (`erasoa/`)
- `sareko_eskanerra.py` — network/port/service scanner.
- `web_analisia.py` — web path fuzzer.
- `sniffer.py` — HTTP/FTP traffic sniffer.
- `arp_spoofer.py` — ARP spoofer (MITM).
- `xmlrpc.py` — WordPress XML-RPC credential brute-forcer.

`menu_nagusia.py` is the entry point that ties the two menus together.

## Requirements

- Python 3
- `nmap` installed on the system (used by the scanner)
- Python packages:

```bash
pip install -r requirements.txt
```

Some offensive tools (sniffer, ARP spoofer, scanner) capture or craft raw
packets and need to be run with root privileges (`sudo`).

## Usage

```bash
python3 menu_nagusia.py
```

## Configuration

The tools were configured for the RedPi lab, so some scripts contain **hard-coded
lab values** (target IPs like `172.16.1.10`, and demo database credentials for
the `technova_db` test database). These are throwaway values from an isolated
simulated environment — adjust the IPs, targets and credentials at the top of each
script for your own authorized environment.

## Notes

- The interface and code comments are written in **Basque** (Euskara).
- `reverse_shellPHP.txt` is a standard PHP reverse-shell payload used in the
  project's practical case; included for completeness.

## License

MIT — see `LICENSE`.
