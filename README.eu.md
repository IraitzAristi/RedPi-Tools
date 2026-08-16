[English](README.md) · [Castellano](README.es.md) · **Euskara**

# RedPi Tools

**RedPi** proiekturako neurrira egindako Python-eko segurtasun-auditoriako
tresna-multzoa — enpresa-sare simulatu bat (LAN / DMZ / WAN), sare-segurtasuna
ikasteko eta erakusteko erabilia. Tresnak menu bidez erabiltzen dira eta bi
multzotan banatzen dira: defentsiboak eta ofentsiboak.

> ⚠️ **Erabilera baimendua / hezkuntzarako soilik.** Tresna hauek norberaren
> laborategi isolatu baterako idatzi ziren, lanbide-heziketako zibersegurtasun
> proiektu baten barruan. Erabili soilik zure jabetzako sistemen aurka edo
> probatzeko idatzizko baimen esplizitua duzun sistemen aurka. Kontrolatzen ez
> dituzun sistemen aurka exekutatzea legez kanpokoa izan daiteke.

[RedPi proiektuaren](https://iraitzaristi.github.io) parte · writeup-a eta
dokumentazio osoa han daude.

## Tresnak

**Defentsiboak** (`defentsa/`)
- `mysql_kudeaketa.py` — MySQL datu-basea kudeatzeko interfazea.
- `pasahitz_analizatzailea.py` — gordetako pasahitzen sendotasun-analizatzailea.
- `pasahitz_generadorea.py` — pasahitz sendoen sortzailea (irteera SHA-256 hash-arekin).

**Ofentsiboak** (`erasoa/`)
- `sareko_eskanerra.py` — sare, ataka eta zerbitzuen eskanerra.
- `web_analisia.py` — web-bideen fuzzer-a.
- `sniffer.py` — HTTP/FTP trafikoaren sniffer-a.
- `arp_spoofer.py` — ARP spoofer-a (MITM).
- `xmlrpc.py` — WordPress-en XML-RPC-aren aurkako kredentzialen indar gordina.

`menu_nagusia.py` da bi menuak lotzen dituen sarrera-puntua.

## Baldintzak

- Python 3
- `nmap` sisteman instalatuta (eskanerrak erabiltzen du)
- Python paketeak:

```bash
pip install -r requirements.txt
```

Tresna ofentsibo batzuek (sniffer-a, ARP spoofer-a, eskanerra) pakete gordinak
harrapatzen edo sortzen dituzte eta root pribilegioekin (`sudo`) exekutatu behar dira.

## Erabilera

```bash
python3 menu_nagusia.py
```

## Konfigurazioa

Tresnak RedPi laborategirako konfiguratu ziren, beraz script batzuek **kodean
finkatutako laborategiko balioak** dituzte (helburuko IPak, `172.16.1.10`
adibidez, eta `technova_db` proba datu-basearen kredentzialak). Ingurune simulatu
eta isolatu bateko balio baztergarriak dira — egokitu IPak, helburuak eta
kredentzialak script bakoitzaren hasieran zure baimendutako ingurunerako.

## Oharrak

- Interfazea eta kodearen iruzkinak **euskaraz** daude.
- `reverse_shellPHP.txt` proiektuaren kasu praktikoan erabilitako PHP reverse
  shell payload estandar bat da; osotasunagatik sartua.

## Lizentzia

MIT — ikusi `LICENSE`.
