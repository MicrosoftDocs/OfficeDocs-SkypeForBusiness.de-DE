---
title: 'Lync Server 2013: Aktivieren von Office-webapps Server und lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89ec4337bd4bc728f9737ecb75bb29075831bc09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528542"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Konfigurieren der Integration mit Office-webapps Server und lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-08-19_

Lync Server 2013 verwendet Office-webapps-Server zur Behandlung von PowerPoint-Präsentationen. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Overview of Webconferencing in lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Um diese neuen Funktionen nutzen zu können, müssen Administratoren Office-webapps Server installieren und lync Server 2013 für die Kommunikation mit Office-webapps-Server konfigurieren. Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Verwendung mit Office-webapps Server. In dieser Dokumentation werden keine Informationen zum Installieren von Office-webapps Server selbst bereitgestellt. Informationen hierzu finden Sie auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <https://go.microsoft.com/fwlink/p/?linkid=257525> . Dieser Leitfaden enthält alle erforderlichen Informationen für Office-webapps Server; Beachten Sie, dass Office webapps Server auf einem eigenständigen Computer installiert werden sollte, auf dem lync Server, Microsoft SQL Server oder eine andere Server Anwendung nicht aktiv ist. (Auf diesem Computer darf keine Version von Microsoft Office installiert sein.) Auf jedem Computer, auf dem Office-webapps-Server ausgeführt wird, muss auch ein bestimmter Softwaresatz installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3,0); Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Information Services (IIS) werden ausführlich in der Microsoft Office Web Apps-Bereitstellungswebsite unter beschrieben <https://go.microsoft.com/fwlink/p/?linkid=257525> .

<div>


> [!NOTE]  
> Die neueste Iteration von Office-webapps Server wird Office Online Server benannt, der von lync Server 2013 unterstützt wird. Weitere Informationen finden Sie in der <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Dokumentation zum Office Online Server</A>.



</div>

In diesem Dokument werden die folgenden Themenbereiche behandelt:

  - [Konfigurieren lync Server 2013 für die Verwendung mit Office-webapps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Veröffentlichen von Office-webapps-Servern in lync Server 2013 mithilfe eines Reverse-Proxyservers](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Überprüfen der Konfiguration von Office-webapps Server in lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Konfigurieren von Clients von lync Server 2013 für die Verwendung mit Office-webapps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

