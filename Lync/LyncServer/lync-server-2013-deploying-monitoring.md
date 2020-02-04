---
title: 'Lync Server 2013: Bereitstellen der Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Bereitstellen der Überwachung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-12-17_

Wichtige Änderungen wurden an der Überwachungsinfrastruktur von Microsoft lync Server 2013 vorgenommen, beginnend mit der Tatsache, dass die Überwachungs Server Rolle veraltet ist. Anstelle von separaten Überwachungsserver Rollen (die in der Regel erforderlich sind, dass Organisationen dedizierte Computer einrichten, um als Überwachungsserver zu fungieren) sind die Überwachungsdienste nun auf jedem Front-End-Server angeordnet. Diese Änderung unterstützt u. a.:

  - Verringern Sie die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind. In diesem Fall hilft die Dekrementierung der Monitoring Server-Serverrolle auch, die Kosten zu senken, da keine dedizierten Server für die Überwachung erforderlich sind.

  - Verringern Sie die Komplexität von lync Server-Setup und-Verwaltung. Durch automatisches abstimmen der Überwachungsdienste auf jedem Front-End-Server müssen Sie die Monitoring Server-Rolle nicht mehr installieren, konfigurieren und verwalten.

<div>


> [!NOTE]  
> Die Rolle des Archivierungsservers wurde in lync Server 2013 ebenfalls als veraltet markiert. Wie die Überwachungsdienste sind die lync Server 2013-Archivierungsdienste nun auf jedem Front-End-Server angeordnet. Dies ist wichtig, da die Überwachung und Archivierung häufig dieselbe SQL Server-Datenbankinstanz verwenden.



</div>

Wie Sie vielleicht erwarten, haben diese Änderungen einen großen Einfluss darauf, wie Überwachungsdienste installiert und verwaltet werden. Wenn beispielsweise die Monitoring Server-Rolle nicht mehr vorhanden ist, wurde der Monitoring Server-Knoten aus dem lync Server Topology Builder entfernt; Das bedeutet wiederum, dass Sie den neuen Monitoring Server-Assistenten von Topology Builder nicht mehr verwenden, um Ihrer Topologie einen neuen Monitoring Server hinzuzufügen. (Dieser Assistent ist nicht mehr vorhanden.) Stattdessen implementieren Sie in der Regel Überwachungsdienste in Ihrer Topologie, indem Sie die beiden folgenden Schritte ausführen:

1.  Aktivieren der Überwachung zur gleichen Zeit beim Einrichten eines neuen lync Server-Pools. (In lync Server 2013 ist die Überwachung in Pool-by-Pool-Basis aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne tatsächlich Überwachungsdaten zu sammeln, was im Abschnitt Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Qualität der Benutzerfreundlichkeit dieser Dokumentation erläutert wird.

2.  Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) zum neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Abhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Zwar ist es oft einfacher, die Überwachung zur gleichen Zeit zu aktivieren, in der Sie einen neuen Pool erstellen, aber es ist auch möglich, einen neuen Pool mit deaktivierter Überwachung zu erstellen. In diesem Fall können Sie später mithilfe des Topologie-Generators den Dienst aktivieren: Topologie-Generator bietet eine Möglichkeit zum Aktivieren oder Deaktivieren der Überwachung für einen Pool oder zum Zuordnen eines Pools zu einem anderen Überwachungsspeicher. Beachten Sie, dass Sie zwar nicht mehr über eine Überwachungs Server Rolle verfügen, aber dennoch mindestens einen Überwachungsspeicher erstellen müssen: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten verwendet werden. Diese Back-End-Datenbankenkönnen entweder mit Microsoft SQL Server 2008 R2 oder mit Microsoft SQL Server 2012 erstellt werden.

<div>


> [!NOTE]  
> Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess des Sammelns von Überwachungsdaten deaktivieren, ohne Ihre Topologie ändern zu müssen: die lync Server-Verwaltungsshell bietet eine Möglichkeit, die Anrufdetailaufzeichnung (CDR) oder die Qualität zu deaktivieren (und später erneut zu aktivieren). Experience (QoE)-Datensammlung. Weitere Informationen finden Sie in diesem Dokument im Abschnitt „Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen)“ und „QoE (Quality of Experience)-Einstellungen“.



</div>

Eine weitere wichtige Verbesserung der Überwachung in lync Server 2013 ist die Tatsache, dass die lync Server-Überwachungsberichte nun IPv6 unterstützen: Berichte, die das Feld IP-Adresse verwenden, werden je nach: 1) der verwendeten SQL-Abfrage entweder IPv4-oder IPv6-Adressen angezeigt. und 2) Wenn die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.

<div>


> [!NOTE]  
> Vergewissern Sie sich, dass der Starttyp des SQL Server-Agent-Diensts „Automatisch“ ist und der SQL Server-Agent-Dienst für die SQL-Instanz mit den Überwachungsdatenbanken ausgeführt wird, damit die SQL Server-Wartungsaufträge für die Standardüberwachung plangemäß unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt werden können.



</div>

Diese Dokumentation führt Sie durch den Vorgang zum Installieren und Konfigurieren von Überwachungs-und Überwachungsberichten für lync Server 2013. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

  - Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

  - Installieren Sie SQL Server Reporting Services und die lync Server-Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

  - Konfigurieren Sie die Datensammlung zur Anrufdetailaufzeichnung (CDR) und zur Quality of Experience (QoE). Die Aufzeichnung von Anrufdetails bietet eine Möglichkeit, die Nutzung von lync-Server Funktionen wie VoIP-Telefon anrufen (Voice over IP) nachvollziehen zu können. Instant Messaging (im) Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. QoE-Metriken dienen zur Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei der Paketverzögerung (Jitter).

  - Manuelles Löschen von KDS und/oder QoE-Datensätzen aus der Überwachungsdatenbank.

</div>

<span> </span>

</div>

</div>

</div>

