---
title: 'Lync Server 2013: Technische Anforderungen für IPv6'
TOCTitle: Technische Anforderungen für IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205278(v=OCS.15)
ms:contentKeyID: 49295411
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für IPv6 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie Lync Server 2013 für IPv6 konfigurieren möchten, sollten Sie die folgenden Anforderungen berücksichtigen:

  - Für die Verwendung von IPv6-Adressen zusammen mit Lync Server müssen Sie DNS-Einträge (Domain Name System) für Datensätze erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6 DNS verwendet Host (AAAA)-Einträge (vier "A"). Falls Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host (A)-Einträge für IPv4 als auch Host (AAAA)-Einträge für IPv6 zu konfigurieren und zu verwalten. Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die noch IPv4 verwenden.
    
    Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Falls der Client oder Server IPv6 nicht verwendet, wird nicht auf den Eintrag verwiesen. Umstellungstechnologien bestimmen anhand von Konfiguration und Richtlinien, welcher Eintrag verwendet werden soll.

  - Jede IPv6-Adresse weist einen Adressbereich auf. Für die IPv6-Adressierung können Sie drei Adressbereiche verwenden, nämlich globale IPv6-Adressen (vergleichbar mit den öffentlichen IPv4-Adressen), eindeutige lokale IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und verbindungslokale IPv6-Adressen (vergleichbar mit den automatisch zugewiesenen, privaten IP-Adressen in Windows Server für IPv4). Alle Server innerhalb eines Pools sollten IPv6-Adressen mit dem gleichen Adressbereich aufweisen.


> [!IMPORTANT]
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server- und Lync Server 2013-Ebene zuweisen, erwartungsgemäß funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas.



## Siehe auch

#### Weitere Ressourcen

[IP Version 6 Addressing Architecture](http://tools.ietf.org/html/rfc4291)  
[IPv6 Global Unicast Address Format](http://tools.ietf.org/html/rfc3587)  
[Unique Local IPv6 Unicast Addresses](http://tools.ietf.org/html/rfc4193)

