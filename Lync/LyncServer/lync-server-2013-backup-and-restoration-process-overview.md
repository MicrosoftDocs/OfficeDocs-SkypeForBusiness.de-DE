---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b01230e84c9278d5540c21d41d9af1342479e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Übersicht über den Sicherungs-und Wiederherstellungsprozess für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Dieser Abschnitt enthält eine Übersicht über die Funktionsweise des Sicherungs-und Wiederherstellungsprozesses für lync Server 2013. Sie verwenden das gleiche Verfahren für alle Standard Edition-Server und Enterprise Edition-Server unabhängig von deren Standort.

Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:

  - Sie erstellen einen Sicherungsspeicherort als freigegebenen Ordner auf einem eigenständigen Computer, der nicht zu einem Pool gehört. Auf den Speicherort der Sicherung wird in **$Backup**verwiesen.

  - Regelmäßig, planmäßig, sichern Sie alle lync Server-Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md) beschrieben werden, indem Sie die unter [Sichern von lync Server 2013 beschriebenen Verfahren ausführen. ](lync-server-2013-backing-up-lync-server.md)Der zentrale Verwaltungsspeicher umfasst alle Servereinstellungen und-Konfigurationen.

  - Jedes Mal, wenn Sie eine nachfolgende Sicherung ausführen, erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, in dem Verweise **$Backup** .

Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:

  - Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den **$Backup** auf neue oder bereinigte Computer verweisen.
    
    <div>
    

    > [!IMPORTANT]  
    > Durch diesen Wiederherstellungsprozess werden keine Daten auf einem vorhandenen Serverzustand wiederhergestellt. Dieser Vorgang erfordert also, dass der Server sauber oder neu ist.

    
    </div>

  - Damit Ihre Benutzer-und Konferenz Informationen bis zum Zeitpunkt des Fehlers wiederherstellbar sind, können Sie eine Disaster Recovery-Topologie mit gekoppelten Front-End-Pools implementieren, wie in [Planen für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.

  - Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfiguration (Dynamic Host Configuration Protocol), Domänennamen, vollqualifizierte Computer Domänennamen (FQDNs), Dateispeicher Pfade usw. müssen zum Zeitpunkt der Wiederherstellung identisch sein, die Sie zum Zeitpunkt des Sichern Sie.

Wenn ein Server mit lync Server ausfällt, umfasst die Wiederherstellung die folgenden Schritte:

  - Installieren Sie das Betriebssystem auf einem neuen oder sauberen Computer mit demselben FQDN wie der fehlerhafte Computer.

  - Installieren Sie Zertifikate erneut.

  - Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.

  - Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren sowie Zugriffssteuerungslisten (ACLs) einzurichten.

  - Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird mit Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.

    
    </div>

  - Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.

</div>

<span> </span>

</div>

</div>

</div>

