---
title: 'Lync Server 2013: Einrichten von Speicher für die Archivierung'
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
ms.openlocfilehash: a5a380ce6c863c54739e74488bfa3b3979664e78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Einrichten von Speicher für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-17_

Der Archivierungsspeicher für lync Server 2013 umfasst Folgendes:

  - **** Zum Speichern von Chat Inhalten sind Datenspeicher erforderlich.   

  - **Dateispeicher**   Dateispeicher ist erforderlich, um Konferenzdaten Speicher und Dateispeicher zu speichern.

<div>

## <a name="setting-up-data-storage"></a>Einrichten von Datenspeicher

Die Anforderungen für das Einrichten von Datenspeicher für die Archivierung in lync Server 2013 hängen davon ab, wie Archivierungsdaten gespeichert werden sollen:

  - Integrieren Sie die lync Server 2013-Archivierung in Ihre Exchange-Bereitstellung, um Archivierungsdaten mithilfe des Exchange-Speichers zu speichern.

  - Einrichten separater SQL Server-Datenbankserver zum Speichern von Archivierungsdaten

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Einrichten des Exchange-Speichers zum Archivieren von Daten

Das Einrichten von Exchange für die Speicherung von Archivierungsdaten setzt voraus, dass Ihre Exchange-Bereitstellung Exchange 2013 ausführt. Darüber hinaus müssen sich Benutzerpostfächer auf dem Exchange 2013-Server befinden, und ihre Postfächer müssen in-situ-Speicher platziert werden. Weitere Informationen zum Konfigurieren von Exchange 2013 finden Sie in der Exchange-Produktdokumentation.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Einrichten von SQL Server-Datenbankservern zum Speichern von Archivierungsdaten

Die Archivierung in lync Server 2013 erfordert, dass die archivierten Daten von der SQL Server-Datenbanksoftware gespeichert werden, es sei denn, Sie integrieren Ihre Bereitstellung in Exchange.

Für SQL Server-Archivierungsdatenbanken müssen Sie SQL Server auf dem Computer installieren, auf dem die Archivierungsdatenbank gehostet wird. Sie können dieselbe SQL-Instanz verwenden, die Sie für die Back-End-Datenbank eines Front-End-Pools verwenden. Um eine optimale Leistung zu erzielen, sollten Sie die Archivierungsdatenbank auf einem Computer bereitstellen, der vom zentralen Verwaltungsspeicher getrennt ist. Ausführliche Informationen zu den abstimmen-Komponenten von lync Server 2013 finden Sie unter [unterstützte Server Zusammenstellung in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Dokumentation zur Unterstützung.

Auf jedem Datenbankserver muss eine unterstützte Version von SQL Server ausgeführt werden. Details zu den unterstützten Versionen finden Sie unter [Technische Voraussetzungen für die Archivierung in lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in der Planungsdokumentation.

Sie müssen die SQL Server-Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren können. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, auch als Teil des Installationsvorgangs. Ausführliche Informationen zu SQL Server finden Sie im SQL Server TechCenter unter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).

<div>


> [!NOTE]  
> Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, die die Archivierungsdatenbank enthält, damit der standardmäßige Archivierungs-SQL Server-Wartungsauftrag auf der Grundlage der geplanten Basis ausgeführt werden kann. Steuerung des SQL Server-Agent-Diensts.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Einrichten von Dateispeicher

Bei der Archivierung wird die von Ihnen festgelegte lync Server 2013-Dateifreigabe verwendet, wenn Sie Ihren Front-End-Pool oder Standard Edition-Server einrichten. Sie können die für die Archivierung verwendete Dateifreigabe nicht ändern. Ausführliche Informationen zu unterstützten Dateispeichersystemen finden Sie unter unter [Stützung von Dateispeicher in lync Server 2013](lync-server-2013-file-storage-support.md) in der Dokumentation zur Unterstützung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

