---
title: 'Lync Server 2013: Einrichten des Speichers für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f299b01b95cddd461893b35518e3c2fe40c694
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Einrichten des Speichers für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-17_

Der Archivierungsspeicher für lync Server 2013 umfasst Folgendes:

  - **Daten**Speicherdaten Speicher ist erforderlich, um Chatinhalte zu speichern.   

  - **Datei**   Speicherdatei Speicher ist erforderlich, um Konferenzen (Besprechungs-) Inhaltsdaten Speicher und Dateispeicher zu speichern.

<div>

## <a name="setting-up-data-storage"></a>Einrichten des Datenspeichers

Voraussetzungen für das Einrichten des Datenspeichers für die Archivierung in lync Server 2013 hängen davon ab, wie Sie Archivierungsdaten speichern möchten:

  - Integrieren Sie lync Server 2013 Archivierung in Ihre Exchange-Bereitstellung, um Archivierungsdaten mithilfe des Exchange-Speichers zu speichern.

  - Richten Sie separate SQL Server-Datenbankserver zum Speichern von Archivierungsdaten ein.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Einrichten des Exchange-Speichers für Archivierungsdaten

Das Einrichten von Exchange für die Speicherung von Archivierungsdaten erfordert, dass Ihre Exchange-Bereitstellung Exchange 2013 ausführt. Darüber hinaus müssen Benutzerpostfächer auf dem Exchange 2013 Server verwaltet werden, und ihre Postfächer müssen in einem Compliance-Archiv abgelegt sein. Ausführliche Informationen zum Konfigurieren von Exchange 2013 finden Sie in der Exchange-Produktdokumentation.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Einrichten von SQL Server Datenbankservern für die Speicherung von Archivierungsdaten

Für die Archivierung in lync Server 2013 müssen die archivierten Daten von der SQL Server-Datenbanksoftware gespeichert werden, es sei denn, Sie integrieren Ihre Bereitstellung in Exchange.

Für SQL Server Archivierungsdatenbanken müssen Sie SQL Server auf dem Computer installieren, auf dem die Archivierungsdatenbank gehostet wird. Sie können dieselbe SQL-Instanz verwenden, die Sie für die Back-End-Datenbank eines Front-End-Pool verwenden. Um eine optimale Leistung zu erzielen, sollten Sie die Archivierungsdatenbank auf einem Computer bereitstellen, der vom zentralen Verwaltungsspeicher getrennt ist. Ausführliche Informationen zu abstimmen lync Server 2013 Komponenten finden Sie unter [unterstützte Server](lync-server-2013-supported-server-collocation.md) Zusammenstellungen in lync Server 2013 in der Unterstützungsdokumentation.

Auf jedem Datenbankserver muss eine unterstützte Version von SQL Server installiert sein. Ausführliche Informationen zu den unterstützten Versionen finden Sie unter [Technical Requirements for Archiving in lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in der Planungsdokumentation.

Sie müssen die SQL Server Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Administratorrechte und-Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen. Sie können die Datenbank auch zu einem späteren Zeitpunkt erstellen, z. B. als Teil des Installationsvorgangs. Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).

<div>


> [!NOTE]  
> Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und dass der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, die das Archivierungsdatenbank aufweist, damit der standardmäßige Archivierungs SQL Server-Wartungsauftrag unter der festgelegten Basis ausgeführt werden kann. Steuerung des SQL Server-Agent-Diensts.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Einrichten des Dateispeichers

Bei der Archivierung wird die lync Server 2013 Dateifreigabe verwendet, die Sie beim Einrichten Ihrer Front-End-Pool oder Standard Edition-Server angegeben haben. Die für die Archivierung verwendete Dateifreigabe kann nicht geändert werden. Ausführliche Informationen zu unterstützten Dateispeichersystemen finden Sie unter [File Storage Support in lync Server 2013](lync-server-2013-file-storage-support.md) in der Unterstützungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

