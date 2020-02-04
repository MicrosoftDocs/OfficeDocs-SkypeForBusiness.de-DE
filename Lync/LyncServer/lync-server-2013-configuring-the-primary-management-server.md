---
title: 'Lync Server 2013: Konfigurieren des primären Verwaltungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Konfigurieren des primären Verwaltungsservers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-19_

Um die neuen Integritäts Überwachungsfunktionen in Microsoft lync Server 2013 vollständig nutzen zu können, müssen Administratoren zunächst einen Computer als primären Verwaltungs Server festlegen. auf diesem Computer müssen Sie System Center Operations Manager 2007 R2 oder System Center Operations Manager 2012 installieren. Darüber hinaus müssen Sie eine unterstützte Version von SQL Server installieren, um als Ihre Operations Manager-Back-End-Datenbank zu funktionieren. Wenn Sie System Center Operations Manager 2012 verwenden, können Sie eine der folgenden Versionen von SQL Server als Back-End-Datenbank verwenden:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Wenn Sie System Center Operations Manager 2007 R2 verwenden, empfiehlt es sich, entweder SQL Server 2005 Service Pack 4 oder SQL Server 2008 Service Pack 3 zu installieren. Sie können auch SQL Server 2008 R2 als Back-End-Datenbank für System Center Operations Manager 2007 R2 verwenden. Weitere Informationen zum Konfigurieren von SQL Server 2008 R2 für die Zusammenarbeit mit System Center Operations Manager 2007 R2 finden Sie in Anhang 1 dieser Dokumentation.

Wenn Sie System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 installieren, müssen Sie alle Komponenten dieses Produkts installieren, einschließlich:

  - Betriebsdatenbank

  - Server

  - Konsole

  - Windows PowerShell-Cmdlets

  - Webkonsole

  - Berichterstellung

  - Data Warehouse

Diese Komponenten und deren Installation werden in diesem Dokument nicht ausführlich erläutert. Ausführliche Informationen zu System Center Operations Manager 2007 R2 finden Sie in der Dokumentation zu Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 unter und in <http://go.microsoft.com/fwlink/p/?linkid=257527>der System Center Operations Manager 2012-Dokumentation unter. Befolgen Sie diese Anweisungen, wenn Sie SQL Server 2005 oder SQL Server 2008 Service Pack 1 als Back-End-Datenbank verwenden möchten.

Wenn Sie System Center Operations Manager 2012 verwenden, können Sie SQL Server 2012 als Back-End-Datenbank verwenden. Ausführliche Informationen zu SQL Server 2012 finden Sie unter Online Dokumentation für SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)unter.

Beachten Sie, dass pro lync Server-Bereitstellung nur ein einzelner primärer Verwaltungs Server verfügbar sein kann. Auch wenn Sie System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 verwenden können, können Sie die beiden Anwendungen nicht gleichzeitig ausführen – Sie müssen die eine oder andere auswählen. Wenn Sie beispielsweise System Center Operations Manager 2012 ausführen, müssen alle Ihre System Center-Agents auch System Center Operations Manager 2012 ausführen. Sie können nicht über einige Agents verfügen, auf denen System Center Operations Manager 2012 und andere Agents mit System Center Operations Manager 2007 R2 ausgeführt werden.

</div>

<span> </span>

</div>

</div>

</div>

