---
title: 'Lync Server 2013: Vorbereiten der Infrastruktur und der Systeme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34de50135ff04c7db1b3eda2b65bdebb4ef10273
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Vorbereiten der Infrastruktur und der Systeme für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Für die Bereitstellung von lync Server 2013 ist die Verwendung des Topologie-Generators zum Definieren und Veröffentlichen des Topologie-Designs erforderlich. Um die für Ihre Topologie erforderlichen Komponenten zu identifizieren, erstellen und speichern Sie einen Topologie-Design mithilfe des Topologie-Generators. Vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator führen Sie folgende Aufgaben aus:

  - Erwerben und installieren Sie die Hardware für jede Komponente im Topologie-Design, die Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten ( IIS) und gegebenenfalls Reverse-Proxy Server), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (beispielsweise Dateiserver). Ausführliche Informationen zum Definieren einer Topologie, die die für Ihre Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Ausführliche Informationen zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt. Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Einrichten Active Directory-Domänendienste. Zum Veröffentlichen und Aktivieren der Topologie müssen die internen Server durch Computerkonten in AD DS repräsentiert werden. Dies wird erreicht, indem die Computer in die Active Directory-Domänendienste aufgenommen werden. Ausführliche Informationen zum Vorbereiten von AD DS finden Sie unter [Vorbereiten von Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Erstellen Sie eine Dateifreigabe. Standard Edition-Server können die Dateifreigabe für die erforderliche Datei hosten, während in einer Enterprise-Bereitstellung die Dateifreigabe nicht auf dem Front-End-Server gehostet werden kann. Die Berechtigungen und Gruppenmitgliedschaften, die zur Bereitstellung und Festlegung der Zugriffssteuerungsliste für den Ordner und die Freigabe erforderlich sind, müssen für den Topologie-Generator ordnungsgemäß festgelegt werden, damit er erfolgreich abgeschlossen werden kann. Sie sollten sicherstellen, dass die Person, auf der der Topologie-Generator ausgeführt wird, über die folgenden Berechtigungen und Gruppenmitgliedschaften verfügt:
    
      - Mitglied der lokalen Administratorgruppe
    
      - Mitglied der Domänenbenutzergruppe
    
      - Vollzugriff auf Freigabe und Ordner des Dateispeichers

  - Installieren Sie SQL Server für Enterprise Edition. Zur erfolgreichen SQL Server-Einrichtung muss der SQL Server-basierte Server online sein, und der Benutzer, der die Topologie veröffentlicht, muss auf der SQL Server-Instanz ein Mitglied der SQL Server-Gruppe "sysadmin" sein.

Nachdem Sie alle Vorbereitungsaufgaben wie in diesem Thema beschrieben abgeschlossen haben, aber vor der Veröffentlichung der Topologie, müssen Sie auch die anderen Vorbereitungsaufgaben ausführen, einschließlich der Installation der Windows-Betriebssysteme und anderer erforderlicher Software, einrichten IIS und Konfigurieren von DNS. Ausführliche Informationen zu diesen Aufgaben finden Sie unter [System Anforderungen für Server mit lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Konfigurieren von IIS für lync Server 2013](lync-server-2013-configure-iis.md)und [Vorbereiten der Infrastruktur und der Systeme für lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Darüber hinaus sollten Sie sich mit den Anforderungen für Clients und Clients vertraut machen. Ausführliche Informationen finden Sie unter [Deploying Clients and Devices in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hardware Setup für lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Software Setup für lync Server 2013](lync-server-2013-software-setup.md)

  - [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren von DNS-Einträgen in lync Server 2013 für eine Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installieren von lync Server 2013 Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

