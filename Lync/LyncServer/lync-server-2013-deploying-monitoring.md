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
ms.openlocfilehash: 73b9947cf77df8d0c3baedcb27d8e13cc728e52b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Bereitstellen der Überwachung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-17_

An der Microsoft lync Server 2013-Überwachungsinfrastruktur wurden wesentliche Änderungen vorgenommen, beginnend mit der Tatsache, dass die Monitoring Server Rolle veraltet ist. Anstatt separater Überwachungsserverrollen (für die Organisationen in der Regel dedizierte Computer einrichten mussten, die als Überwachungsserver dienten) werden Überwachungsdienste jetzt auf jedem Front-End-Server gemeinsam ausgeführt. Unter anderem sorgt diese Änderung für folgende Vorteile:

  - Verringern Sie die Anzahl der Serverrollen, die bei der Implementierung von lync Server 2013 erforderlich sind. In diesem Fall kann das Verringern der Überwachungsserverrolle auch Kosten sparen, da keine dedizierten Server für die Überwachung mehr erforderlich sind.

  - Verringern Sie die Komplexität von lync Server Einrichtung und Verwaltung. Da die Überwachungsdienste auf jedem Front-End-Server automatisch gemeinsam ausgeführt werden, müssen Sie die Überwachungsserverrolle nicht mehr installieren, konfigurieren und verwalten.

<div>


> [!NOTE]  
> Die Archivierungsserver Rolle wurde auch in lync Server 2013 veraltet. Wie bei den Überwachungsdiensten werden nun lync Server 2013 Archivierungsdienste auf jedem Front-End-Server zusammengefasst. Dies sollte beachtet werden, da Überwachung und Archivierung oft auf derselben SQL Server-Datenbankinstanz ausgeführt werden.



</div>

Wie Sie vielleicht erwarten, haben diese Änderungen erhebliche Auswirkungen auf die Installation und Verwaltung von Überwachungsdiensten. Da die Monitoring Server Rolle beispielsweise nicht mehr vorhanden ist, wurde der Monitoring Server Knoten aus dem lync Server Topologie-Generator entfernt. Das bedeutet wiederum, dass Sie den neuen Monitoring Server-Assistenten für den Topologie-Generator nicht mehr verwenden, um Ihrer Topologie einen neuen Monitoring Server hinzuzufügen. (Der Assistent ist nicht mehr vorhanden.) Stattdessen implementieren Sie in der Regel Überwachungsdienste in der Topologie, indem Sie die folgenden zwei Schritte ausführen:

1.  Aktivieren der Überwachung bei gleichzeitiger Einrichtung eines neuen lync Server Pools. (In lync Server 2013 ist die Überwachung auf Pool-zu-Pool-Basis aktiviert oder deaktiviert.) Beachten Sie, dass Sie die Überwachung für einen Pool aktivieren können, ohne Überwachungsdaten tatsächlich zu erfassen, ein Prozess, der in dieser Dokumentation im Abschnitt Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Qualität der Erfahrung erläutert wird.

2.  Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) an den neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Anhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Oft ist es zwar einfacher, die Überwachung gleichzeitig mit der Erstellung eines neuen Pool zu aktivieren, es ist jedoch auch möglich, bei deaktivierter Überwachung einen neuen Pool zu erstellen. In diesem Fall können Sie später den Topologie-Generator verwenden, um den Dienst zu aktivieren. Mithilfe des Topologie-Generators kann die Überwachung für einen Pool aktiviert bzw deaktiviert, oder ein Pool kann einem anderen Überwachungsspeicher zugeordnet werden. Beachten Sie, dass weiterhin mindestens ein Überwachungsspeicher erstellt werden muss, auch wenn keine Überwachungsserverrolle mehr vorhanden ist: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten dienen. Diese Back-End-Datenbanken können mithilfe von Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 erstellt werden.

<div>


> [!NOTE]  
> Wenn die Überwachung für einen Pool aktiviert wurde, können Sie den Prozess des Sammelns von Überwachungsdaten deaktivieren, ohne Ihre Topologie ändern zu müssen: lync Server-Verwaltungsshell bietet Ihnen die Möglichkeit, die Aufzeichnung von Kommunikationsdatensätzen (KDS) oder die Qualität zu deaktivieren (und später erneut zu aktivieren). QoE-Datenerfassung (Experience of Experience). Weitere Informationen finden Sie in diesem Dokument im Abschnitt "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE (Quality of Experience)-Einstellungen".



</div>

Eine weitere wichtige Verbesserung der Überwachung in lync Server 2013 ist die Tatsache, dass lync Server Überwachungsberichte jetzt IPv6 unterstützen: Berichte, die das Feld IP-Adresse verwenden, werden je nach der verwendeten SQL-Abfrage entweder IPv4-oder IPv6-Adressen angezeigt. und, 2) wo die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist oder nicht.

<div>


> [!NOTE]  
> Stellen Sie sicher, dass der Starttyp des SQL Server-Agent-Diensts automatisch ist und der SQL Server-Agentdienst für die SQL-Instanz ausgeführt wird, in der die Überwachungsdatenbanken gespeichert sind, sodass die Standard Überwachungs SQL Server Wartungsaufträge auf Ihrer geplanten Basis ausgeführt werden können. unter Kontrolle des SQL Server-Agent-Diensts.



</div>

In dieser Dokumentation werden Sie durch den Prozess der Installation und Konfiguration von Überwachungs-und Überwachungsberichten für lync Server 2013 geleitet. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

  - Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

  - Installieren Sie SQL Server Reporting Services und die lync Server-Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

  - Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen (KDS) und der Sammlung von QoE (Quality of Experience)-Daten. Die Aufzeichnung von Kommunikationsdatensätzen bietet Ihnen die Möglichkeit, die Verwendung von lync Server Funktionen wie VoIP-Telefon anrufen (Voice over IP) nachzuverfolgen. Instant Messaging (Sofortnachrichten); Dateiübertragungen; Audio/Video-Konferenzen (A/V); und Anwendungsfreigabesitzungen. QoE-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter).

  - Manuelles Löschen von KDS und QoE-Datensätzen aus der Überwachungsdatenbank.

</div>

<span> </span>

</div>

</div>

</div>

