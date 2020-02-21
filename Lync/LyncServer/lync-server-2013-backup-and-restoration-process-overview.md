---
title: 'Lync Server 2013: Übersicht über den Sicherungs-und Wiederherstellungsprozess'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Sicherungs-und Wiederherstellungsprozess – Übersicht für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-26_

Dieser Abschnitt enthält eine Übersicht darüber, wie der Sicherungs-und Wiederherstellungsprozess für lync Server 2013 funktioniert. Sie können unabhängig vom Standort für alle Standard Edition-Server und Enterprise Edition-Server dasselbe Verfahren anwenden.

Im Allgemeinen funktioniert der Sicherungsvorgang wie folgt:

  - Sie erstellen auf einem eigenständigen Computer, der nicht Teil eines Pools ist, einen Sicherungsspeicherort als freigegebenen Ordner. Auf den Speicherort der Sicherung wird in  **$Backup** verwiesen.

  - Auf einer regulären, geplanten Basis sichern Sie alle lync Server Datenbanken und alle Dateispeicher, die unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md) beschrieben werden, indem Sie die Verfahren unter [sichern lync Server 2013](lync-server-2013-backing-up-lync-server.md) der zentrale Verwaltungsspeicher enthält alle Server Einstellungen und-Konfigurationen beschrieben.

  - Bei jedem Ausführen einer nachfolgenden Sicherung erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, auf den **$Backup** verweist.

Im Allgemeinen funktioniert der Wiederherstellungsprozess wie folgt:

  - Wenn ein Fehler oder Ausfall auftritt, stellen Sie die Daten an dem Speicherort wieder her, auf den von **$Backup** verwiesen wird, auf neue oder saubere Computer.
    
    <div>
    

    > [!IMPORTANT]  
    > Mit diesem Wiederherstellungsprozess werden Daten nicht auf einem Server im aktuellen Zustand wiederhergestellt. Der Prozess erfordert einen bereinigten oder neuen Server.

    
    </div>

  - Damit Ihre Benutzer-und Konferenz Informationen zum Fehlerfall wiederhergestellt werden können, können Sie eine Notfall Wiederherstellungs Topologie mit paarweise gepaarten Front-End-Pools implementieren, wie in [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.

  - Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfigurationen (Dynamic Host Configuration Protocol), Domänennamen, Computer-FQDNs (vollqualifizierte Domänennamen), Dateispeicherpfade usw. müssen zum Zeitpunkt der Wiederherstellung dieselben wie zum Zeitpunkt der Sicherung sein.

Wenn ein Server mit lync Server fehlschlägt, umfasst die Wiederherstellung die folgenden Schritte:

  - Installieren Sie das Betriebssystem auf einem neuen oder bereinigten Computer mit demselben FQDN wie der ausgefallene Computer.

  - Installieren Sie die Zertifikate neu.

  - Wenn der Server eine Datenbank gehostet hat, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.

  - Wenn der Server eine Datenbank gehostet hat, führen Sie im Allgemeinen den Topologie-Generator aus, um die Datenbank zu erstellen und zu installieren und Zugriffssteuerungslisten (ACLs) einzurichten.

  - Wenn der Server eine Serverrolle gehostet hat, führen Sie im allgemeinen Schritt 1 bis Schritt 4 des lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien zu installieren, die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Server eine Datenbank mit der Serverrolle gehostet hat, wird durch Ausführen von Schritt 2 des lync Server-Bereitstellungs-Assistenten die Datenbank neu erstellt.

    
    </div>

  - Wenn der Server eine Datenbank gehostet hat, stellen Sie die gesicherten Daten wieder her.

</div>

<span> </span>

</div>

</div>

</div>

