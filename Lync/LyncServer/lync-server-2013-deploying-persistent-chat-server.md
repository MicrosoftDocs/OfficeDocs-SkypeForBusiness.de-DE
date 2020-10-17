---
title: 'Lync Server 2013: Bereitstellen des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76f3bb2a3ccc182f16e2e1416bdec00aefe3e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506092"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Bereitstellen des Servers für beständigen Chat in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-31_

Lync Server 2013 ist der Server für beständigen Chat Teil der lync Server 2013-Infrastruktur.

Zum Bereitstellen des Servers für beständigen Chat müssen Sie Folgendes tun:

  - Verwenden Sie den Topologie-Generator, um die Topologie und die Komponenten, die Sie bereitstellen möchten, zu definieren oder zu importieren und anschließend zu veröffentlichen.

  - Vorbereiten der Umgebung für die Bereitstellung von Komponenten für beständigen Chat Server.

  - Installieren und konfigurieren Sie die Server Komponenten für beständigen Chat für Ihre Bereitstellung.

Der Server für beständigen Chat ist mit lync Server 2013 Enterprise Edition als separater Pool verfügbar (nicht zusammen mit den Front-End-Servern der Enterprise Edition). Für den Server für beständigen Chat ist ein SQL Server Back-End-Server in Ihrem Enterprise Edition-Pool erforderlich, um den Chatroom-Inhalt und andere relevante Metadaten zu speichern. Es wird empfohlen, das **PersistentChatStore** auf einem dedizierten SQL Server Back-End-Server zu installieren, obwohl abstimmen lync Server 2013 Back-End-Server und **PersistentChatStore** in derselben SQL Server-Instanz unterstützt werden.

Der Server für beständigen Chat kann auch mit lync Server 2013 Standard Edition bereitgestellt werden. In diesem Fall ist die **PersistentChatService** -Front-End-Server auf dem Standard Edition-Computer zusammengefasst, und der **PersistentChatStore** -Back-End-Server kann auf der lokalen SQL Server Express-Instanz bereitgestellt werden.

Ausführliche Informationen zu unterstützten Colocation-Konfigurationen finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md)Zusammenstellungen in lync Server 2013.

<div>


> [!IMPORTANT]  
> Die hohe Verfügbarkeit für die Server Standard Edition für beständigen Chat wird nicht unterstützt &nbsp; . Leistung und Skalierung sind eingeschränkt. Darüber hinaus unterstützen wir nur neue Server für beständigen Chat &nbsp; Standard Edition-Server. Wir unterstützen das Upgrade lync Server 2010, Gruppen Chat Server nicht auf eine lync Server 2013 &nbsp; persistent Chat Server &nbsp; Standard Edition.



</div>

Wenn Ihre Organisation Compliance-Unterstützung benötigt, können Sie den Kompatibilitätsdienst für beständigen Chat Server auf dem Server für beständigen Chat Front-End-Server installieren. Für die Konformität ist eine separate Datenbank erforderlich.

Für jede Topologie ist mindestens ein Server mit installierter lync Server 2013 und ein Server mit SQL Server-Datenbanksoftware erforderlich.

Verwenden Sie den Topologie-Generator, um Ihren lync Server 2013-Bereitstellungen beständigen Chat Server hinzuzufügen. Sie können mithilfe des Topologie-Generators einen oder mehrere Server Pools für beständigen Chat hinzufügen. Befolgen Sie dieselben Bereitstellungsanweisungen für die Bereitstellung mehrerer Server Pools für beständigen Chat wie für jeden Pool. Ausführliche Informationen finden Sie unter [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zu verfügbaren Topologien und den technischen und Softwareanforderungen für die Installation von persistent Chat Server finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [How persistent Chat ServerWorks in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation sowie [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zum Erwerb von Zertifikaten, zum Erstellen der SQL Server Datenbank und zum Erstellen von Datei speichern finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

Eine einzelne Server Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen. Sie können einen Server Pool für beständigen Chat mit bis zu 4 aktiven Front-End-Servern mit einer Gesamtzahl von 80.000 gleichzeitigen Benutzern unterstützen.

Der Server für beständigen Chat wird auch auf einem virtuellen Server unterstützt. Der virtuelle Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, wenn er den Spezifikationen des physischen Servers entspricht.

<div>


> [!IMPORTANT]  
> Der Server für beständigen Chat muss auf einem NTFS-Dateisystem installiert sein, um die Sicherheit von Dateisystemen zu Verb erzwingen. FAT32 ist kein unterstütztes Dateisystem für den Server für beständigen Chat.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Funktionsweise von persistent Chat Server in lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Prüfliste für die Bereitstellung für persistent Chat Server in lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Technische Anforderungen für den Server für beständigen Chat in lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Einrichten von Systemen und Infrastruktur für den Server für beständigen Chat in lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Hinzufügen von persistent Chat Server zu Ihrer Bereitstellung in lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installieren des Servers für beständigen Chat in lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Hinzufügen eines Administrators für beständigen Chat in lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Konfigurieren des Servers für beständigen Chat in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Problembehandlung für die Server Konfiguration für beständigen Chat mit Windows PowerShell-Cmdlets in lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Failover und Ausfall des Servers für beständigen Chat in lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

