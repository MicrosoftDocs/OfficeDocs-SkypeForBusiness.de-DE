---
title: 'Lync Server 2013: Aktivieren von Office Web Apps Server und Lync Server 2013'
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
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-08-19_

Lync Server 2013 verwendet Office Web Apps Server für die Behandlung von PowerPoint-Präsentationen. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Übersicht über Webkonferenzen in lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Um diese neuen Funktionen verwenden zu können, müssen Administratoren Office Web Apps Server installieren und lync Server 2013 für die Kommunikation mit Office Web Apps Server konfigurieren. Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server. Diese Dokumentation bietet keine Informationen dazu, wie Sie Office Web Apps Server selbst installieren können. Informationen hierzu finden Sie auf <http://go.microsoft.com/fwlink/p/?linkid=257525>der Microsoft Office Web Apps-Bereitstellungswebsite unter. Dieser Leitfaden enthält alle erforderlichen Informationen für Office Web Apps Server. Beachten Sie, dass der Office Web Apps-Server auf einem eigenständigen Computer installiert sein sollte, auf dem lync Server, Microsoft SQL Server oder eine andere Serveranwendung nicht ausgeführt wird. (Auf diesem Computer darf keine Version von Microsoft Office installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4,5 und Windows PowerShell 3,0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Informationsdienste (IIS) werden ausführlich auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <http://go.microsoft.com/fwlink/p/?linkid=257525>erläutert.

<div>


> [!NOTE]  
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, der von lync Server 2013 unterstützt wird. Weitere Informationen finden Sie in der <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server-Dokumentation</A>.



</div>

In diesem Dokument werden die folgenden Themenbereiche behandelt:

  - [Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Überprüfen der Konfiguration von Office Web Apps Server in lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Konfigurieren von Clients von lync Server 2013 zur Verwendung mit Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

