---
title: Konfigurieren lync Server für die Verwendung mit System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff72248e691d3e5358fda79a98d318cfc3a382eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Konfigurieren lync Server 2013 für die Verwendung mit System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Um Ihre Microsoft lync Server 2013-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:

  - Identifizieren und konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver. Das Konfigurieren des Verwaltungsservers umfasst die Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 sowie das Einrichten einer Back-End-Datenbank mithilfe von SQL Server. Die aktuelle Version von SQL Server, die Sie verwenden müssen, hängt von der von Ihnen verwendeten Version von System Center Operations Manager ab. Ausführliche Informationen finden Sie unter [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifizieren und konfigurieren Sie die lync Server Computer, die Sie überwachen möchten. Um einen lync Server Computer mithilfe von System Center Operations Manager zu überwachen, müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert.

  - Identifizieren und konfigurieren Sie die Computer, die als lync Server Watcher- *Knoten*fungieren sollen. Watcher-Knoten sind Computer, die regelmäßig lync Server synthetischen Transaktionen ausgeführt werden, bei denen es sich um Windows PowerShell-Cmdlets handelt, die sicherstellen, dass wichtige lync Server-Komponenten, beispielsweise die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austauschen von Chatnachrichten, funktioniert wie erwartet.

Die Themen in diesem Abschnitt enthalten Anweisungen zum Ausführen aller dieser Aufgaben

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren des primären Verwaltungsservers in lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installieren der lync Server 2013 Management Packs](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Konfigurieren der lync Server Computer, die in lync Server 2013 überwacht werden](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installieren und Konfigurieren von Watcher-Knoten in lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

