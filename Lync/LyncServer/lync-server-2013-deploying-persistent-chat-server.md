---
title: 'Lync Server 2013: Bereitstellen des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Bereitstellen des Servers für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-31_

Lync Server 2013, beständiger Chat Server ist Teil der lync Server 2013-Infrastruktur.

Für die Bereitstellung des beständigen Chat Servers müssen Sie Folgendes ausführen:

  - Verwenden Sie den Topologie-Generator, um Ihre Topologie und die Komponenten, die Sie bereitstellen möchten, zu definieren, zu importieren und anschließend zu veröffentlichen.

  - Bereiten Sie Ihre Umgebung für die Bereitstellung beständiger Chat Server Komponenten vor.

  - Installieren und konfigurieren Sie Komponenten für beständigen Chat Server für Ihre Bereitstellung.

Der Server für beständigen Chat steht in lync Server 2013 Enterprise Edition als separater Pool zur Verfügung (nicht mit den Enterprise Edition-Front-End-Servern). Der Server für beständigen Chat erfordert einen SQL Server-Back-End-Server in Ihrem Enterprise Edition-Pool, um den Chatroom-Inhalt und andere relevante Metadaten zu speichern. Wir empfehlen, dass Sie die **PersistentChatStore** auf einem dedizierten SQL Server-Back-End-Server installieren, obwohl abstimmen lync Server 2013-Back-End-Server und **PersistentChatStore** auf derselben SQL Server-Instanz unterstützt werden.

Der Server für beständigen Chat kann auch mit lync Server 2013 Standard Edition bereitgestellt werden. In diesem Fall befindet sich der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Computer, und der **PersistentChatStore** -Back-End-Server kann auf der lokalen SQL Server Express-Instanz bereitgestellt werden.

Ausführliche Informationen zu unterstützten Colocation-Konfigurationen finden Sie unter unterstützte Server setzungen [in lync Server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Wir unterstützen keine höhere Verfügbarkeit für die Standard&nbsp;Edition für beständigen Chat Server. Leistung und Skalierung sind limitiert. Darüber hinaus unterstützen wir nur den neuen Server&nbsp;für beständigen Chat Server Standard Edition. Wir unterstützen nicht das Upgrade von lync Server 2010, Gruppen-Chat Server auf eine&nbsp;lync Server 2013&nbsp;persistent Chat Server Standard Edition.



</div>

Wenn Ihre Organisation Compliance-Unterstützung erfordert, können Sie den beständigen Chat Server-Kompatibilitätsdienst auf dem Front-End-Server für beständigen Chat Server installieren. Für die Compliance ist eine separate Datenbank erforderlich.

Für jede Topologie ist mindestens ein Server mit lync Server 2013 und ein Server mit installierter SQL Server-Datenbanksoftware erforderlich.

Verwenden Sie den Topologie-Generator, um ihrer lync Server 2013-Bereitstellung beständigen Chat Server hinzuzufügen. Mithilfe des Topologie-Generators können Sie einen oder mehrere beständige Chat Server Pools hinzufügen. Befolgen Sie dieselben Bereitstellungsanweisungen für die Bereitstellung mehrerer beständiger Chat Server Pools, wie Sie dies für jeden Pool tun würden. Ausführliche Informationen finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Details zu verfügbaren Topologien sowie zu den technischen und Softwareanforderungen für die Installation von persistent Chat Server finden Sie unter Planen des beständigen [Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [Funktionsweise des beständigen Chat Servers in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation sowie [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung.

Details zum Abrufen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Datei speichern finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Ein einzelner beständiger Chat Server-Front-End-Server kann 20.000-aktive Benutzer unterstützen. Sie können einen Server Pool für beständigen Chat mit bis zu vier aktiven Front-End-Servern mit insgesamt 80.000 gleichzeitigen Benutzern unterstützen.

Der Server für beständigen Chat wird auch auf einem virtuellen Server unterstützt. Der virtuelle Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, wenn er den Spezifikationen des physikalischen Servers entspricht.

<div>


> [!IMPORTANT]  
> Der Server für beständigen Chat muss auf einem NTFS-Dateisystem installiert sein, um die Dateisystemsicherheit zu erzwingen. FAT32 ist kein unterstütztes Dateisystem für beständigen Chat Server.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Funktionsweise des beständigen Chat Servers in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Prüfliste zur Bereitstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Technische Anforderungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Einrichten der Systeme und Infrastruktur für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Hinzufügen eines Administrators für beständigen Chat in Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Konfigurieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Problembehandlung bei der Konfiguration des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Ausführen eines Failovers bzw. Failbacks für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

