---
title: 'Lync Server 2013: Einrichten von Systemplattformen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Einrichten von Systemplattformen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bevor Sie die Bereitstellung des beständigen Chat Servers starten, müssen Sie das erforderliche Betriebssystem auf Hardware installieren, die den Systemanforderungen auf Servern entspricht:

Details zur unterstützten Hardware für Server mit lync Server 2013, Datenbankservern und Dateiservern finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Dokumentation zur Unterstützung. Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware finden Sie unter Unterstützung für [Server Software und-Infrastruktur in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Dokumentation zur Unterstützung. Details zu den Windows Update-Anforderungen finden Sie unter [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in der Dokumentation zur Unterstützung.

Der beständige Chat Server-Front-End-Server, **PersistentChatService**, kann auf einem oder mehreren eigenständigen Computern in einem lync Server 2013 Enterprise Edition-Pool bereitgestellt werden. Sie können nicht auf den lync Server Enterprise Edition-Front-End-Servern zusammengestellt werden. Der Server für beständigen Chat kann vom Bootstrapper bereitgestellt werden, genau wie andere lync-Serverrollen. Die **beständigen Chat-Webdienste für Datei Upload/-Download**und **beständige Chat-Webdienste für die chatroomverwaltung** sind Webkomponenten, die auf den lync Server 2013-Front-End-Servern bereitgestellt werden.

Ein einzelner beständiger Chat Server-Front-End-Server kann 20.000-aktive Benutzer unterstützen. Sie können einen Server Pool für beständigen Chat mit bis zu vier aktiven Front-Ends haben, der insgesamt 80.000 gleichzeitige Benutzer unterstützt. Der beständige Chat-Back-End-Server, **PersistentChatStore**, speichert die Chatrooms und Kategorien. Wir empfehlen, die **PersistentChatStore** auf einem dedizierten SQL Server-Back-End-Server in Ihrem Enterprise Edition-Pool zu installieren. Obwohl wir abstimmen lync Server 2013-Back-End-Server und- **PersistentChatStore** auf derselben SQL Server-Instanz unterstützen.

Wenn Ihre Organisation Compliance-Unterstützung erfordert, können Sie Sie mithilfe des Topologie-Generators installieren. Der beständige Chat Server-Kompatibilitätsdienst ist auf demselben Computer wie der Front-End-Server des beständigen Chat Servers installiert. Für die Compliance ist eine separate Datenbank erforderlich. Ausführliche Informationen zu den Konformitätsanforderungen für den Server für beständigen Chat finden Sie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

Für jede Topologie ist mindestens ein Server mit lync Server 2013 und ein Server mit installierter SQL Server-Datenbanksoftware erforderlich. Der Topologie-Generator unterstützt mehrere beständige Chat Server Pools. Befolgen Sie die gleichen Bereitstellungsanweisungen für die Bereitstellung mehrerer beständiger Chat Server Pools wie für jeden Pool, wenn Sie [lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation bereitstellen möchten.

Sie können den Server für beständigen Chat auch mit lync Server 2013 Standard Edition bereitstellen. In diesem Fall befindet sich der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Server, und Sie können den **PersistentChatStore** -Back-End-Server auf der lokalen SQL Server Express-Instanz bereitstellen.

<div>


> [!IMPORTANT]  
> Wir unterstützen keine persistent Chat Server&nbsp;Standard Edition für eine höhere Verfügbarkeit. Leistung und Skalierung sind limitiert. Darüber hinaus unterstützen wir nur neue Server Bereitstellungen für beständigen Chat Server&nbsp;-Standard Editionen. Wir unterstützen kein Upgrade von lync Server 2010, Gruppen-Chat Server auf eine lync Server 2013&nbsp;persistent Chat Server&nbsp;Standard Edition.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Unterstützte Hardware für Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Serversoftware- und Infrastrukturunterstützung in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

