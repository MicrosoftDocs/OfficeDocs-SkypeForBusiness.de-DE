---
title: 'Lync Server 2013: DNS-Infrastrukturunterstützung'
TOCTitle: DNS-Infrastrukturunterstützung (Domain Name System)
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425850(v=OCS.15)
ms:contentKeyID: 49293677
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Infrastrukturunterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-08_

Lync Server 2013 erfordert DNS (Domain Name System) und setzt es folgendermaßen ein:

  - Zum Erkennen interner Server oder Pools für die Kommunikation zwischen Servern.

  - Damit Clients den Front-End-Pool oder den Standard Edition-Server erkennen können, der für verschiedene SIP-Transaktionen verwendet wird.

  - Zum Zuordnen der einfachen URLs für Konferenzen zu den Servern, auf denen diese Konferenzen gehostet werden.

  - Damit externe Server und Clients für Sofortnachrichten oder für Konferenzen eine Verbindung mit Edgeservern oder dem HTTP-Reverseproxy herstellen können.

  - Damit nicht angemeldete UC-Geräte (Unified Communications) den Front-End-Pool oder den Standard Edition-Server ermitteln können, auf dem der Geräteaktualisierungswebdienst ausgeführt wird, sowie Updates abrufen und Protokolle senden können.

  - Damit mobile Clients automatisch Webdienstressourcen ermitteln können, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.

  - Zum DNS-Lastenausgleich.


> [!NOTE]
> Lync Server 2013 unterstützt keine internationalisierten Domänennamen (IDNs).




> [!IMPORTANT]
> Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen. Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname. Der Topologie-Generator verwendet FQDNs und keine Kurznamen. Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist. <STRONG>Verwenden Sie nur Standardzeichen</STRONG> (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync&nbsp;Server, Edgeserver und Pools. Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.


