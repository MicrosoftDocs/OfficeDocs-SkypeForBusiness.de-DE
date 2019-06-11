---
title: 'Lync Server 2013: Vorbereiten der Infrastruktur und Systeme'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e724dd3b6105be3f4601c523dbbf558c91ca9f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Vorbereiten der Infrastruktur und Systeme für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Bereitstellung von lync Server 2013 erfordert die Verwendung des Topologie-Generators zum Definieren und Veröffentlichen des Topologie-Designs. Um die für Ihre Topologie erforderlichen Komponenten zu identifizieren, verwenden Sie den Topologie-Generator zum Erstellen und Speichern eines Topologie-Designs. Bevor Sie Ihre Topologie im Topologie-Generator veröffentlichen, gehen Sie wie folgt vor:

  - Erwerben und installieren Sie die Hardware für jede Komponente im Topologie-Design, das Sie mithilfe des Topologie-Generators erstellt und gespeichert haben, einschließlich aller erforderlichen Computer (Server mit lync Server 2013, Datenbankservern, Servern mit Internet Informationsdiensten ( IIS) und ggf. Reverse Proxy Server), Netzwerkadapter, Hardwarelastenausgleichs und Speichergeräte (wie Dateiserver). Details zum Definieren einer Topologie, die die für die Bereitstellung erforderlichen Komponenten angibt, finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Details zu den Hardwareanforderungen für Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.

  - Stellen Sie sicher, dass die Netzwerkinfrastruktur die Anforderungen erfüllt. Ausführliche Informationen finden Sie unter Anforderungen an die [Netzwerkinfrastruktur für lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in der Planungsdokumentation.

  - Einrichten von Active Directory-Domänendiensten Um die Topologie zu veröffentlichen und zu aktivieren, müssen Sie die internen Server durch Computerkonten in AD DS darstellen. Dies erfolgt durch beitreten der Computer zu AD DS. Details zum Vorbereiten von AD DS finden Sie unter [Vorbereiten der Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Erstellen Sie eine Dateifreigabe. Standard Edition-Server können die Dateifreigabe für die erforderliche Datei hosten, während die Dateifreigabe in einer Unternehmensbereitstellung nicht auf dem Front-End-Server gehostet werden kann. Die Berechtigungen und Gruppenmitgliedschaften, die für die Bereitstellung und Festlegung der Zugriffssteuerungsliste (ACL) für den Ordner und die Freigabe erforderlich sind, müssen für die erfolgreiche Ausführung des Topologie-Generators ordnungsgemäß festgelegt werden. Stellen Sie sicher, dass die Person, auf der der Topology Builder ausgeführt wird, über die folgenden Berechtigungen und Gruppenmitgliedschaften verfügt:
    
      - Mitglied von lokalen Administratoren
    
      - Mitglied von Domänenbenutzern
    
      - Vollzugriff auf Freigabe und Ordner im Dateispeicher

  - Für Enterprise Edition installieren und konfigurieren Sie SQL Server. Damit das SQL Server-Setup erfolgreich ausgeführt werden kann, muss der auf SQL Server basierende Server online sein, und die Person, die die Topologie veröffentlicht, ist ein lokaler Administrator auf dem SQL Server und muss ein Mitglied der SQL Server sysadmin-Gruppe auf der SQL Server-Instanz sein.

Nachdem Sie alle Vorbereitungsaufgaben abgeschlossen haben, wie in diesem Thema beschrieben, aber vor dem Veröffentlichen der Topologie, müssen Sie auch die anderen Vorbereitungsaufgaben ausführen, einschließlich der Installation der Windows-Betriebssysteme und anderer erforderlicher Software, einrichten IIS und Konfigurieren von DNS. Details zu diesen Aufgaben finden Sie unter [System Anforderungen für Server mit lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Konfigurieren von IIS für lync Server 2013](lync-server-2013-configure-iis.md)und [Vorbereiten der Infrastruktur und Systeme für lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Darüber hinaus sollten Sie sich mit den Anforderungen der Clients und Clients vertraut machen. Ausführliche Informationen finden Sie unter [Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hardwaresetup für Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Softwaresetup für Lync Server 2013](lync-server-2013-software-setup.md)

  - [Vorbereiten der Active Directory-Domänendienste für Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Konfigurieren von SQL Server für Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Konfigurieren der DNS-Einträge in Lync Server 2013 für einen Front-End-Pool oder Standard Edition-Server](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

