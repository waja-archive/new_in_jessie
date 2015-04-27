---
author: Jan Wagner <waja@cyconet.org>
title: Was ist neu in Debian 8 Jessie?
---
## Was ist neu in Debian 8 Jessie?
### Jan Wagner <waja@cyconet.org>

---
= data-x='1000'
## Facts

* 4.841 neue Quellpakete
* ca. 1300 Quellpakete in Jessie entfernt
* > 21k Quellpakete
* zweites Release seit Sarge, was einen kürzeren Freeze als 6 Monate hatte

---
= data-x='1000'
## Versionen wichtiger Pakete

Kernel 3.16  
Xen 4.4 (xl + xm)  
glibc 2.19  
GCC 4.9 + 4.8  
Clang/LLVM 3.4 + 3.5  
Perl 5.20  
Python 2.7.9 + 3.4  
Ruby 2.1  
<!--
Tcl/Tk 8.6  
-->

---
= data-x='1000'
## Versionen wichtiger Pakete

Apache 2.4  
Nginx 1.6  
PHP 5.6  
PostgreSQL 9.4  
MariaDB 10.0  
MySQL 5.5 (Unterstützung bis 12.2016)  
<!--
Berkeley-DB 5.3  
-->
Postfix 2.11  
<!--
Exim 4.84  
Courier 0.73  
-->

---
= data-x='1000'
## Versionen wichtiger Pakete

OpenSSH 6.7  
OpenVPN 2.3  
StrongSwan 5.2  
BIND 9.9  
Unbound 1.4.22  
PowerDNS 3.4  
CUPS 1.7  
Samba 4.1  
Icinga 1.11  
Icinga2 2.1  

---
= data-x='1000'
## Versionen wichtiger Pakete

GNU Bash 4.3  
Zsh 5.0.7  
GNU Emacs 24.4  
Vim 7.4  
GNU Screen 4.2.1  
Tmux 1.9  

---
= data-x='1000'
## Versionen wichtiger Pakete

X.org 7.7  
GNOME 3.14  
KDE 4.11 (tlw. auch 4.12, 4.13, 4.14)  
XFCE 4.10  
LibreOffice 4.3  

---
= data-x='1000' data-scale="4"
## Neue Desktop Oberflächen

* Cinnamon 2.2
   * im Stil von GNOME 2
   * auf GNOME 3 aufbauend
   * [http://cinnamon.linuxmint.com/](http://cinnamon.linuxmint.com/)

* MATE 1.8
   * im Stil von GNOME 2
   * Weiterentwicklung von GNOME 2
   * [http://www.mate-desktop.org/](http://www.mate-desktop.org/)

---
= data-x='1000' data-scale="4"
## Neue Desktop Oberflächen

* RazorQt 0.5.2
  * schlank
	* QT-basiert
	* [http://razor-qt.org/](http://razor-qt.org/)
	* das Projekt ist zur Zeit dabei mit LXDE zu LXQt zu verschmelzen

---
= data-x='1000'
## Init-System

Neues Standard-Init-System ist Systemd.  

* schnelleres Booten
* Cgroups zur Ressourcenkontrolle von Diensten
* Möglichkeit, Services teilweise zu isolieren

Thanks god we have alternatives!

* System-V-Init (Paket `sysvinit-core`)
* Upstart
* OpenRC
* Runit (allerdings ohne offiziellen Support als Init-System)

---
= data-x='1000'
## Was man (noch) wissen sollte

* `crypttab` nicht komplett mit `systemd` unterstützt
* `openssh` nun default auf `PermitRootLogin without-password`
* `apache2` in Version 2.4 geänderter Syntax, geänderte Konfigurationsstruktur
* Debian GNU/kFreeBSD: `kfreebsd-*` (nicht mehr stabil genug, Pakete mit Stand Jessie-Release gibt’s unter `jessie-kfreebsd` auf allen Mirrors)
* wheezy-lts ist geplant
* Release Notes lesen (hilft)

---
= data-x='1000' data-rotate="90"
## APT

Mit APT 1.0 kam neu `/usr/bin/apt` als Alternative zu `apt-get` und `apt-cache` dazu.

* Gedacht als Benutzerschnittstelle: farbige Ausgabe, etc.
* Sollte nicht zum Skripten verwendet werden, API noch nicht stabil.
* Kann nicht alle Unterkommandos von `apt-get` und `apt-cache`.
* Hat dafür ein neues Unterkommando `apt list`, was in etwa `aptitude search` oder `apt-show-versions` entspricht.
* `apt-get` existiert weiterhin und sollte zum Skripten auch weiterhin verwendet werden.

---
= data-x='1000' data-rotate="-180"
## Neue Pakete (1/x)
### Paketmanagement

* `needrestart`, `whatmaps`: Interaktives oder automatisches Neustarten von Diensten, deren Bibliotheken aktualisiert wurden. (Ähnlich `checkrestart` aus dem Paket `debian-goodies`, aber als APT-Hook.)
* `debian-security-support`: Anzeige von Paketen, deren Unterstützung durch Sicherheitsaktualisierung vorzeitig ausläuft.
* `aptitude-robot`: Automatisierung und Verwaltung von Paket-Auswahlen
<!-- * `apt-transport-tor`: Wenn man nicht verraten will, dass man Debian und welche Pakete man benutzt. -->
* `apt-venv`: APT Virtual Environment, erlaubt das Installieren von `.deb`-Paketen ins Home-Verzeichnis
* `isenkram`: Automatisches Vorschlagen von Paketen zur Hardware-Unterstützung beim Einstecken von neuer Hardware (z.B. USB-Geräten).

---
= data-x='1000' data-rotate="-90"
## Neue Pakete (2/x)
### Konfigurationsmanagement

* `ansible` und `salt`

### Virtualisierung

* `bootstrap-vz`: Erstellen von Debian-Images für Nutzung bei Cloud-Anbietern/-Systemen (Amazon, Google, OpenStack, …)
* `vmdebootstrap`: Erstellen von Festplatten-Images für KVM, etc.
* OpenStack (diverse Pakete)

### Boot-Loader

* `grub-xen`: Abgespeckter Grub 2 für Xen-Systeme
* `gummiboot`: Einfacher UEFI-Bootloader aus dem Systemd-Umfeld

---
= data-x='1000' data-rotate="180"
## Neue Pakete (3/x)
### Dateisysteme

* `ceph` (Verteiltes Dateisystem)

### Backup

* `bareos` (Bacula-Fork)
* `clonezilla` (Bare-Metal-Backup und -Wiederherstellung)

### Sysadmin-Tools

* `lnav`: Ncurses-basierter Log-Dateien-Betrachter
* `glances`: Ähnlich wie `top`, zeigt aber viele weiteren Infos über das System an: Plattenplatzverbrauch, Netzwerk-Verkehr, Disk-I/O, etc.
* `sosreport`: Tool, das Endbenutzer aufrufen können um einem Techniker hilfreiche Informationen über ein System zu geben.

---
= data-x='1000' data-rotate="90"
## Neue Pakete (4/x)
### Spezielle Hardware-Unterstützung

* `bumblebee`: Unterstützung für Geräte mit NVIDIA-Optimus-Grafikkarten-System
* `sunxi-tools`: Programme zum Arbeiten mit Allwinner-ARM-Prozessoren.
* `f3`: Tool zum Verifizieren ob bei Flash-Medien die aufgedruckte Kapazität korrekt ist.

### Compiler und Interpreter

* Coffeescript (div. Pakete)

---
= data-x='1000' data-rotate="-90"
## Neue Pakete (5/x)
### Dokumenten-Renderer

* `mdpress`: Erstellen von Impress.js-basierten Präsentationen im Markdown-Format.

### Editoren

* Viele neue Plugins für Vim
* Viele neuen True-Type-Schriftarten

### VCS

* `metamonger`: Speichert Dateisystem-Metadaten von Dateien in Git-Repositories.

---
= data-x='1000' data-rotate="180"
## Neue Pakete (6/x)
### Paketierung

* `debdry` Halbautomatische Paketierung durch Verhinderung von Wiederholungen (DRY = Don’t Repeat Yourself)
* `dput-ng`: Reimplementation von dput mit u.a. ausführlicheren Paket-Tests vor dem Hochladen.

### Qualitätssicherung für Pakete

* `adequate`: Überprüft installierte Pakete auf typische Fehler. (Wie `lintian`, nur für installierte Pakete.)
* `duck`: Debian URL Checker; überprüft, ob URLs und E-Mail-Adressen in der Paketierung noch gültig sind. Siehe auch [http://duck.debian.net/](http://duck.debian.net/)
* `how-can-i-help`: Zeigt an, welche der installierten Pakete ggf. Hilfe benötigen.
<!-- * `tmperamental`: Per `LD_PRELOAD` geladene Bibliothek, die anzeigt, wenn ein Programm unerlaubterweise nach `/tmp/` schreibt, z.B. wenn sie die Umgebungsvariable `$TMPDIR` ignoriert. -->

---
= data-x='1000' data-rotate="90"
## Neue Pakete (7/x)
### Server-Software, CGI-Skripte, etc.

* `nghttp2`: HTTP 2.0 Referenz-Implementation
* `cgit`: Schnelles, in C geschriebenes Web-Frontend für Git-Repositories (ein Ersatz für `gitweb`)
* `pinto`: Programm zum Betreiben eines eigenen Perl-Modul-Archivs im Stile des *CPAN*.
* `calypso`: CalDAV-/CardDAV-Server mit Git-Backend zum Speichern von Kalendereinträgen und Kontaktdaten.
* `elog`: Elektronisches Online-Logbuch zum Protokollieren von Wartungen, Vorfällen, etc. an Geräten oder Systemen.
* `owncloud`: Cloud-Speicher für Dateien, Musik, Kontakte, Kalender und vieles mehr
* `nodejs`: Ereignisgesteuerte E/A für JavaScript V8

---
= data-x='1000' data-rotate="180"
## Neue Pakete (8/x)
### Webbrowser

* `qupzilla`: Leichtgewichtiger Webbrowser basierend auf der Qt-Variante von WebKit.

### E-Mail

* `alot`: Text-Modus-Mailprogramm, das `notmuch` als Backend verwendet.
* `automx`: Server-seitiges Programm zum automatischen Konfigurieren von E-Mail-Programmen anhand der E-Mail-Adresse.

### Kompression

* `pxz` und `pixz`: Parallele Kompression mit XZ/LZMA (verschiedene Implementationen)
* `lbzip2`: Schnelle, multi-thread Bzip2-Implementation.

---
= data-x='1000' data-rotate="-90"
## Neue Pakete (9/x)
### DNS/DNSSEC/DHCP

* `dhcpy6d`: DHCPv6-Server, der IPv6-Adressen basierend auf MAC-Adressen vergeben kann.
* `dns-root-data`: DNS-Root-Zonen-Informationen (`root.hints`) einschliesslich der öffentlichen Root-DNSSEC-Vertrauensanker (`root.key, root.ds`)
* `dnssec-trigger`: Dienst, der (via Unbound) dafür sorgt, dass wenn möglich immer DNSSEC-Validierung aktiv ist, einschliesslich eines Systray-Applets, welches anzeigt, ob DNSSEC-Validierung momentan funktioniert.
* `knot`: Authorativer DNS-Server entwickelt von den CZ.NIC Labs, der Entwicklungsabteilung der `.cz` Registierungsstelle.

---
= data-x='1000' data-rotate="90"
## Neue Pakete (10/x)
### Monitoring-Software

* `monitoring-plugins` wegen Problemen mit Nagios Enterprises umbenannt aus `nagios-plugins`
* `icinga2` komplett von Grund auf neu erstelle Monitoring-Lösung

---
= data-x='1000' data-rotate="180"
## Neue Pakete (11/x)
### Interessantes für die Kommandozeile

* `undistract-me`: Benachrichtigt via `libnotify`-Popups den Benutzer, wenn langlaufende Kommandos auf der Kommandozeile fertig geworden sind. Funktioniert zur Zeit nur mit der `bash`.
* `rename`: Moderner Ersatz für und langfristig Nachfolger des bisher im Paket `perl` mitgelieferten Programmes `prename`.
* `asciinema`: Mitschneiden und Online-Stellen von Kommandozeilen-Sessions
<!-- * `powerline`: Framework für Kommandozeilen-Prompts und andere Statuszeilen.-->
* `cleo`: Automatisches Starten von vordefinierten Kommandozeilenbefehlen, bei denen es so aussieht, als ob man den Befehl tippt. Für Präsentationen gedacht.
* `silversearcher-ag`: Reimplementation in C des in Perl geschriebenen `ack` (Paket `ack-grep`), einem "`grep` für Menschen".
* `vit`: Ncurses-basiertes Text-Modus-Frontend für Taskwarrior

---
= data-x='1000' data-rotate="270"
## Neue Pakete (12/x)
### Chat/IM/Microblogging

* `dianara` und `pumpa`: Client-Programme für das `pump.io`-Netzwerk von Micro-Blogs.
* `hexchat`: Nachfolger von X-Chat
* `irssi-plugin-otr`: Off-The-Record-Verschlüsselungs-Plugin für `Irssi`.
* `kanla`: Schlanker Monitoring-Daemon mit Alarmierung via Jabber/XMPP.

---
= data-x='1000' data-rotate="-90"
## Neue Pakete (13/x)
### Video

* `mpv`: Video-Player basierend auf MPlayer/MPlayer2, aber mit aufgefeilterer Benutzeroberfläche/-schnittstelle.
* `minitube` und `smtube`: YouTube Video-Browser und -Player.
* `mediathekview`: Dursuchen und Anschauen von Fernsehprogrammen diverser deutschsprachiger Fernsehsender inkl. SRF, ORF, ARD und ZDF.
* `youtube-dl`: Kommandozeilen-Programm zum Herunterladen von Videos von hunderten von Video-Portalen.
* `handbrake`: DVD-Ripper und Video-Format-Konverter

---
= data-x='1000' data-rotate="-180"
## Neue Pakete (14/x)
### X11

* `winswitch`: Programm zum Starten und Verwalten von Remote-Anwendungen und -Sessions. Kann sowohl ganze Desktop-Sessions (via NX, VNC, RDP), wie auch einzelne Anwendungen (via Xpra, NX und SSH) remote anzeigen.

### Geografische Anwendungen

* Marble (diverse Pakete): Grafisches Programm zum Anzeigen von digitalen Landkarten diverser Anbieter.
* `openstreetmap-client`: GNOME-Programm zu Anzeigen von digitalen Landkarten von OpenStreetMap.

---
= data-x='1000'
## Nicht (mehr) enthaltene Pakete

* `pacemaker`: Ressourcenverwaltung für Hochverfügbarkeits-Cluster
* `roundcube`: Optisch anpassbare, AJAX-basierte Webmail-Lösung für IMAP-Server
* `docker.io`: Linux container runtime
* `pnp4nagios`: monitoring addon to create graphs from performance data
* `snort`: Flexibles Netzwerk-IDS (Intrusion Detection System)
* `openswan`: Daemon für das Internet-Key-Exchange-Protokoll

---
= data-x='1000'
## Slides

* [http://irgendeine.url](http://irgendeine.url)
* Lizenz: [CC-SA-3.0-DE](https://creativecommons.org/licenses/by-sa/3.0/de/)
* Mail: Jan Wagner <waja@cyconet.org>  


## Cedits (wo ich mich hemmungslos bedient habe)

* [Vortrag auf der Jessie Release Party Zürich](http://noone.org/talks/whats-new-in-debian/jessie-release-party-zurich.html) von Axel Beckert
* [Jessie-Vortrag an den Grazer Linuxtagen](http://michael-prokop.at/slides/glt15_debian_jessie_lightning_talk.pdf) von Michael Prokop
