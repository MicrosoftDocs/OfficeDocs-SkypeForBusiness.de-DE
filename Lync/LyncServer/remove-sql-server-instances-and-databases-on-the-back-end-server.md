---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11439dd9fd339c3620b3e6288526459f45a2a542
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Sie entfernen die Microsoft SQL Server-Datenbanken und-Instanzen, nachdem Sie die Server mit lync Server 2010 entfernt haben, die von diesen abhängig sind, oder nachdem Sie die Server mit lync Server 2010 neu konfiguriert haben, um eine andere Datenbank zu verwenden. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server mit lync Server 2010 so neu konfigurieren, dass die Datenbanken veraltet oder nicht verfügbar sind.

Um die Datenbanken oder Instanzen für den Archivierungsserver oder den Überwachungsserver zu entfernen, müssen Sie zuerst die Serverrolle entfernen. Um die Instanzen oder Datenbanken für den Front-End-Pool zu entfernen, müssen Sie die abhängige Serverrolle zunächst entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen zusammengefassten Datenbanken oder separaten Instanzen für Server unterschieden. Die Verfahren sind von der Daten Bank Zusammenstellung nicht betroffen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

