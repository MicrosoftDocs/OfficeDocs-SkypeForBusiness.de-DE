---
title: 'Lync Server 2013: Hardware-Setup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528342"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Hardware Setup für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Zum Einrichten der Hardware und anderer Komponenten, die für die Infrastruktur erforderlich sind, die Sie zur Implementierung Ihrer Topologie benötigen, müssen Sie vor dem Veröffentlichen der Topologie im Topologie-Generator folgende Schritte ausführen:

  - Installieren Sie die Hardware für jede Komponente im Topologie-Design, die Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server, auf denen lync Server 2013, Datenbankserver, Server mit Internet Information Services (IIS) und Reverse-Proxyservern, je nach Bedarf), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver) verwendet werden. Überprüfen Sie, ob Sie die Empfehlungen für die Anzahl und die Geschwindigkeit von Netzwerkadaptern befolgt haben. Wenn Sie Hardwaregeräte zum Lastenausgleich verwenden, stellen Sie sicher, dass Sie über die richtigen Informationen vom Anbieter verfügen, um Sie für die Verwendung mit lync Server 2013 zu konfigurieren. Wenn Sie einen Dateiserver oder einen anderen Server verwenden, um die für lync Server erforderliche Dateifreigabe zu beherbergen, stellen Sie sicher, dass der Server verfügbar und für die Konfiguration der Dateifreigabe bereit ist. Ausführliche Informationen zum Definieren einer Topologie, die die für Ihre Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt. Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Einrichten Active Directory-Domänendienste. Die Einrichtung der Active Directory-Domänendienste (AD DS) umfasst die AD DS-Vorbereitung und das Definieren aller Komponenten, die Sie in AD DS bereitstellen möchten. Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

  - Richten Sie die erforderlichen Berechtigungen zum Erstellen der Dateifreigabe ein. Berechtigungen für die Verwendung von Dateifreigaben durch lync Server 2013 werden beim Veröffentlichen Ihrer Topologie automatisch vom Topologie-Generator konfiguriert. Das zum Veröffentlichen der Topologie verwendete Benutzerkonto muss jedoch über Vollzugriff auf die Dateifreigabe verfügen (Lesen/Schreiben/ändern), damit der Topologie-Generator die erforderlichen Berechtigungen konfigurieren kann. Um sicherzustellen, dass die Dateifreigabe während des Veröffentlichungsprozesses des Topologie-Generators ordnungsgemäß verwaltet werden kann, sollte der Benutzer oder die Domänengruppe, zu der der Benutzer gehört, Mitglied der lokalen Gruppe Administratoren auf dem Computer sein, auf dem sich die Dateifreigabe befindet. In einem Szenario mit mehreren Domänen sollte ein Benutzer oder eine Gruppe aus Domäne A Mitglied der lokalen Administratorgruppe auf dem Computer in Domäne B sein, auf dem die Dateifreigabe platziert wird.
    
    Ausführliche Informationen zum Aktualisieren mithilfe von Dateifreigaben in einem verteilten Datei System (DFS) finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > Die Dateifreigabe für lync Server 2013 Enterprise Edition kann sich nicht auf dem Front-End-Server befinden.

    
    </div>

  - Installieren und Einrichten des Hardwaregerät zum Lastenausgleich für Webdienste. Auch wenn Sie einen DNS-Lastenausgleich (Domain Name System) konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTP/HTTPS-Datenverkehr. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet. Wenngleich Sie weiterhin Hardwaregeräte zum Lastenausgleich für diese Pools benötigen, erfolgt ihre Einrichtung und Verwaltung hauptsächlich für HTTP/HTTPS-Datenverkehr – so wie es Administratoren von Hardwaregeräten zum Lastenausgleich gewohnt sind.

Nachdem Sie alle vorbereitenden Aufgaben durchgeführt haben, jedoch vor der Veröffentlichung der Topologie, müssen Sie zusätzlich die folgenden Aufgaben ausführen:

  - [Installieren von Betriebssystemen und erforderlicher Software auf Servern für lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Konfigurieren von IIS für lync Server 2013](lync-server-2013-configure-iis.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren von DNS-Einträgen in lync Server 2013 für eine Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

