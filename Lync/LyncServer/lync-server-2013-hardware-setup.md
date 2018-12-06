---
title: 'Lync Server 2013: Hardwaresetup'
TOCTitle: Hardwaresetup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425852(v=OCS.15)
ms:contentKeyID: 49293682
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hardwaresetup für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Zum Einrichten der Hardware und weiterer Infrastrukturkomponenten, die zur Implementierung Ihrer Topologie erforderlich sind, müssen Sie vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator die folgenden Aufgaben ausführen:

  - Installieren Sie die Hardware für jede Komponente im Topologieentwurf, die Sie mit dem Topologie-Generator erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (z. B. Lync Server 2013-Server, Datenbankserver, IIS-Server und Reverseproxyserver), Netzwerkadapter, Hardwaregeräten zum Lastenausgleich und Speichergeräten (z. B. Dateiserver). Überprüfen Sie, ob Sie die Empfehlungen für die Anzahl und die Geschwindigkeit von Netzwerkadaptern befolgt haben. Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, stellen Sie sicher, dass Sie vom Hersteller die richtigen Informationen erhalten haben, um die Hardwaregeräte für die Verwendung mit Lync Server 2013 zu konfigurieren. Wenn Sie einen Dateiserver oder einen anderen Server verwenden möchten, auf dem sich die für Lync Server erforderliche Dateifreigabe befindet, stellen Sie sicher, dass der Server verfügbar und für die Konfiguration der Dateifreigabe bereit ist. Ausführliche Informationen zum Definieren einer Topologie, welche die für Ihre Bereitstellung benötigten Komponenten angibt, finden Sie unter [Definieren und Konfigurieren der Topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur Ihren Anforderungen entspricht. Ausführliche Informationen finden Sie unter [Anforderungen an die Netzwerkinfrastruktur](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Nehmen Sie die Einrichtung von Active Directory-Domänendienste vor. Die Einrichtung der Active Directory-Domänendienste (AD DS) umfasst die AD DS-Vorbereitung und das Definieren aller Komponenten, die Sie in AD DS bereitstellen möchten. Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

  - Richten Sie die erforderlichen Berechtigungen zum Erstellen der Dateifreigabe ein. Die zur Verwendung von Dateifreigaben durch Lync Server 2013 erforderlichen Berechtigungen werden beim Veröffentlichen der Topologie automatisch vom Topologie-Generator konfiguriert. Das zum Veröffentlichen der Topologie verwendete Benutzerkonto muss jedoch über Vollzugriff (Lesen/Schreiben/Ändern) für die Dateifreigabe verfügen, damit Topologie-Generator die erforderlichen Berechtigungen konfigurieren kann. Um sicherzustellen, dass die Dateifreigabe bei der Veröffentlichung durch den Topologie-Generator ordnungsgemäß verwaltet werden kann, sollte der Benutzer oder die Domänengruppe, der der Benutzer angehört, ein Mitglied der lokalen Administratorgruppe auf dem Computer sein, auf dem sich die Dateifreigabe befindet. In einem Szenario mit mehreren Domänen sollte ein Benutzer oder eine Gruppe aus Domäne A Mitglied der lokalen Administratorgruppe auf dem Computer in Domäne B sein, auf dem die Dateifreigabe platziert wird.
    
    Ausführliche Informationen zum Verwenden von Dateifreigaben in einem verteilten Dateisystem (Distributed File System, DFS) finden Sie unter [Konfigurieren des Dateispeichers für Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    

    > [!WARNING]
    > Die Dateifreigabe für Lync Server 2013, Enterprise Edition, darf sich nicht auf dem Front-End-Server befinden.



  - Installieren Sie das Hardwaregerät zum Lastenausgleich für die Webdienste. Auch wenn Sie einen DNS-Lastenausgleich (Domain Name System) konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTP/HTTPS-Datenverkehr. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet. Wenngleich Sie weiterhin Hardwaregeräte zum Lastenausgleich für diese Pools benötigen, erfolgt ihre Einrichtung und Verwaltung hauptsächlich für HTTP/HTTPS-Datenverkehr - so wie es Administratoren von Hardwaregeräten zum Lastenausgleich gewohnt sind.

Nachdem Sie alle vorbereitenden Aufgaben durchgeführt haben, jedoch vor der Veröffentlichung der Topologie, müssen Sie zusätzlich die folgenden Aufgaben ausführen:

  - [Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Konfigurieren von IIS für Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

