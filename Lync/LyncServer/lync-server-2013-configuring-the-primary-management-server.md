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
ms.openlocfilehash: a4fee1fa728c3c418c1f837a83248d95df7e7544
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532312"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Konfigurieren des primären Verwaltungsservers in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-19_

Um die neuen Funktionen für die Integritätsüberwachung in vollem Umfang nutzen zu können, müssen Administratoren zunächst einen Computer als primären Verwaltungs Server für Microsoft lync Server 2013 festlegen. auf diesem Computer müssen Sie System Center Operations Manager 2007 R2 oder System Center Operations Manager 2012 installieren. Darüber hinaus müssen Sie eine unterstützte Version von SQL Server installieren, die als Operations Manager-Back-End-Datenbank fungiert. Wenn Sie System Center Operations Manager 2012 verwenden, können Sie eine der folgenden Versionen von SQL Server als Back-End-Datenbank verwenden:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Wenn Sie System Center Operations Manager 2007 R2 verwenden, sollten Sie entweder SQL Server 2005 Service Pack 4 oder SQL Server 2008 Service Pack 3 installieren. Sie können auch SQL Server 2008 R2 als Back-End-Datenbank für System Center Operations Manager 2007 R2 verwenden. In Anhang 1 dieser Dokumentation finden Sie weitere Informationen zum Konfigurieren von SQL Server 2008 R2 für die Verwendung von System Center Operations Manager 2007 R2.

Bei der Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 müssen Sie alle Komponenten des Produkts installieren, einschließlich:

  - Betriebsdatenbank

  - Server

  - Konsole

  - Windows PowerShell-Cmdlets

  - Webkonsole

  - Reporting

  - Data Warehouse

Diese Komponenten und ihre Installation werden in diesem Dokument nicht ausführlich beschrieben. Ausführliche Informationen zu System Center Operations Manager 2007 R2 finden Sie in der Operations Manager 2007 R2-Dokumentation unter <https://go.microsoft.com/fwlink/p/?linkid=257526> und in der System Center Operations Manager 2012-Dokumentation unter <https://go.microsoft.com/fwlink/p/?linkid=257527> . Befolgen Sie diese Anweisungen, wenn Sie SQL Server 2005 oder SQL Server 2008 Service Pack 1 als Back-End-Datenbank verwenden möchten.

Wenn Sie System Center Operations Manager 2012 verwenden, können Sie SQL Server 2012 als Back-End-Datenbank verwenden. Ausführliche Informationen zu SQL Server 2012 finden Sie in der Online Dokumentation zu SQL Server 2012 unter [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) .

Beachten Sie, dass Sie pro lync Server-Bereitstellung nur einen einzigen primären Verwaltungs Server haben können. Auch wenn Sie entweder System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 verwenden können, können Sie die beiden Anwendungen nicht gleichzeitig ausführen – Sie müssen die eine oder die andere auswählen. Wenn Sie beispielsweise System Center Operations Manager 2012 ausführen, müssen auf allen System Center-Agents auch System Center Operations Manager 2012 ausgeführt werden. Es können nicht einige Agents mit System Center Operations Manager 2012 und anderen Agents ausgeführt werden, auf denen System Center Operations Manager 2007 R2 ausgeführt wird.

</div>

<span> </span>

</div>

</div>

</div>

