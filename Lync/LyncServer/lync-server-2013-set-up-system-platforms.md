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
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509782"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a>Einrichten von Systemplattformen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Bevor Sie mit der Bereitstellung des Servers für beständigen Chat beginnen, müssen Sie das erforderliche Betriebssystem auf Hardware installieren, die die Systemanforderungen auf Servern erfüllt:

Ausführliche Informationen zur unterstützten Hardware für Server, auf denen lync Server 2013, Datenbankserver und Dateiserver auszuführen sind, finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) in der Unterstützungsdokumentation. Ausführliche Informationen zu unterstützten Betriebssystemen und Datenbanksoftware finden Sie unter [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in der Unterstützungsdokumentation. Ausführliche Informationen zu den Windows Update-Anforderungen finden Sie unter [zusätzliche Server Unterstützung und Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in der Unterstützungsdokumentation.

Der Server für beständigen Chat Front-End-Server **PersistentChatService**kann auf einem oder mehreren eigenständigen Computern in einem lync Server 2013 Enterprise Edition-Pool bereitgestellt werden. Sie können nicht auf den lync Server Enterprise Edition-Front-End-Servern zusammengefasst werden. Der Server für beständigen Chat kann vom Bootstrapper bereitgestellt werden, genau wie bei anderen lync Server Rollen. Die **Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien**und den **beständigen Chat Webdienste für die chatroomverwaltung** sind auf den lync Server 2013-Front-End-Servern bereitgestellte Webkomponenten.

Eine einzelne Server Front-End-Server für beständigen Chat kann 20.000 aktive Benutzer unterstützen. Sie können einen Server Pool für beständigen Chat mit bis zu 4 aktiven Front-Ends mit einer Gesamtzahl von 80.000 gleichzeitigen Benutzern unterstützen. Auf dem Back-End-Server für beständigen Chat, **PersistentChatStore**, werden die Chatrooms und Kategorien gespeichert. Es wird empfohlen, das **PersistentChatStore** auf einem dedizierten SQL Server Back-End-Server im Enterprise Edition-Pool zu installieren. Obwohl wir abstimmen lync Server 2013 Back-End-Server und **PersistentChatStore** auf derselben SQL Server-Instanz unterstützen.

Wenn Ihre Organisation Compliance-Unterstützung benötigt, können Sie Sie mithilfe des Topologie-Generators installieren. Der Kompatibilitätsdienst für den Server für beständigen Chat wird auf demselben Computer wie der Server für beständigen Chat Front-End-Server installiert. Für die Konformität ist eine separate Datenbank erforderlich. Ausführliche Informationen zu den Kompatibilitätsanforderungen für den Server für beständigen Chat finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

Für jede Topologie ist mindestens ein Server mit installierter lync Server 2013 und ein Server mit SQL Server-Datenbanksoftware erforderlich. Der Topologie-Generator unterstützt mehrere Server Pools für beständigen Chat. Befolgen Sie die gleichen Bereitstellungsanweisungen für die Bereitstellung mehrerer Server Pools für beständigen Chat wie für jeden Pool, wenn Sie lync Server 2013 in der Bereitstellungsdokumentation [Bereitstellen](lync-server-2013-deploying-lync-server.md) .

Sie können auch den Server für beständigen Chat mit lync Server 2013 Standard Edition bereitstellen. In diesem Fall wird der **PersistentChatService** -Front-End-Server auf dem Standard Edition-Server zusammengestellt, und Sie können den **PersistentChatStore** -Back-End-Server auf der lokalen SQL Server Express Instanz bereitstellen.

<div>


> [!IMPORTANT]  
> Wir unterstützen keine persistent Chat Server &nbsp; Standard Edition für hohe Verfügbarkeit. Leistung und Skalierung sind eingeschränkt. Darüber hinaus werden nur neue Server für beständigen Chat &nbsp; Standard Edition-Server-Bereitstellungen unterstützt. Wir unterstützen kein Upgrade von lync Server 2010, Gruppen Chat Server auf eine lync Server 2013 &nbsp; persistent Chat Server &nbsp; Standard Edition.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md)  
[Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Planen von Servern für beständigen Chat in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

