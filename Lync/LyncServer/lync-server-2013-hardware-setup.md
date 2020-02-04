---
title: 'Lync Server 2013: Hardwaresetup'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Hardwaresetup für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Das Einrichten der Hardware und anderer Komponenten, die für die Infrastruktur erforderlich sind, die Sie zum Implementieren Ihrer Topologie benötigen, erfordert, dass Sie vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator die folgenden Schritte ausführen:

  - Installieren Sie die Hardware für jede Komponente im Topologie-Design, das Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten (IIS) und Reverse Proxy Server, je nach Bedarf), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver). Vergewissern Sie sich, dass Sie die Empfehlungen für die Anzahl und Geschwindigkeit von Netzwerkadaptern befolgt haben. Wenn Sie Hardwarelastenausgleichs verwenden werden, stellen Sie sicher, dass Sie über die richtigen Informationen des Anbieters verfügen, um Sie für die Verwendung mit lync Server 2013 zu konfigurieren. Wenn Sie einen Dateiserver oder einen anderen Server verwenden werden, um die von lync Server erforderliche Dateifreigabe aufzunehmen, stellen Sie sicher, dass der Server verfügbar und für die Konfiguration der Dateifreigabe bereit ist. Details zum Definieren einer Topologie, die die für die Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Details zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt. Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Einrichten von Active Directory-Domänendiensten Das Einrichten von AD DS umfasst das Vorbereiten von AD DS und das Definieren aller Komponenten, die in AD DS bereitgestellt werden sollen. Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.

  - Richten Sie die erforderlichen Berechtigungen zum Erstellen der Dateifreigabe ein. Die Berechtigungen für die Verwendung von Dateifreigaben durch lync Server 2013 werden automatisch vom Topologie-Generator konfiguriert, wenn Sie Ihre Topologie veröffentlichen. Das für die Veröffentlichung der Topologie verwendete Benutzerkonto muss jedoch über die vollständige Steuerung (Lesen/Schreiben/ändern) auf der Dateifreigabe verfügen, damit der Topologie-Generator die erforderlichen Berechtigungen konfigurieren kann. Um sicherzustellen, dass die Dateifreigabe während des Veröffentlichungsprozesses der Topologie-Builder ordnungsgemäß verwaltet werden kann, sollte der Benutzer oder die Domänengruppe, in der der Benutzer Mitglied ist, Mitglied der lokalen Gruppe Administratoren auf dem Computer sein, auf dem sich die Dateifreigabe befindet. In einem Szenario mit mehreren Domänen sollte die Domäne eines Benutzers oder einer Gruppe ein Mitglied der lokalen Gruppe Administratoren auf dem Computer in Domäne B sein, in dem sich die Dateifreigabe befindet.
    
    Ausführliche Informationen zum Aktualisieren von Dateifreigaben in einem DFS (Distributed File System) finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > Die Dateifreigabe für lync Server 2013, Enterprise Edition, kann nicht auf dem Front-End-Server gefunden werden.

    
    </div>

  - Installieren Sie das Hardware-Lastenausgleichsmodul für Webdienste, und richten Sie es ein. Wenn der DNS-Lastenausgleich (Domain Name System) bereitgestellt wird, müssen Sie weiterhin Hardwarelastenausgleichs für diese Pools verwenden, jedoch nur für HTTP/HTTPS-Datenverkehr. Das Hardware-Lastenausgleichsmodul wird für HTTPS-Datenverkehr von Clients über Ports 443 und 80 verwendet. Obwohl Sie weiterhin Hardwarelastenausgleichs für diese Pools benötigen, werden deren Einrichtung und Verwaltung in erster Linie für den HTTP/HTTPS-Datenverkehr verwendet, den die Administratoren der Hardwarelastenausgleichs gewohnt sind.

Nachdem Sie alle Vorbereitungsaufgaben wie in diesem Thema beschrieben, aber vor dem Veröffentlichen der Topologie abgeschlossen haben, müssen Sie auch Folgendes tun:

  - [Installieren von Betriebssystemen und erforderlicher Software auf Servern für Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Konfigurieren von IIS für Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

