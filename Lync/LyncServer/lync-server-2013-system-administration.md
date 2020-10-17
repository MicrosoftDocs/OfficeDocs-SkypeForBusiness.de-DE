---
title: 'Lync Server 2013: System Administration'
description: 'Lync Server 2013: System Administration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b56271d8d90f1d83072af0577692be1ea0b5bc7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562681"
---
# <a name="system-administration-in-lync-server-2013"></a>System Verwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Die System Administration umfasst die täglichen administrativen Aufgaben, sowohl geplant als auch bedarfsgesteuert, die erforderlich sind, damit ein IT-System reibungslos funktioniert. In der Regel werden Systemverwaltungsaufgaben in schriftlichen Verfahren behandelt. Mithilfe dieser Verfahren wird sichergestellt, dass alle Supportmitarbeiter dieselben Standardtools und-Methoden verwenden.

In einer lync-Umgebung umfassen die typischen Systemverwaltungsaufgaben das Sichern und Archivieren von Pools, das Überwachen von Protokollen, das Erstellen und Verwalten von Benutzern und das Aktualisieren von Antivirensoftware.

<div>

## <a name="system-troubleshooting"></a>System Problembehandlung

Eine Organisation muss bereit sein, mit unerwarteten Problemen fertig zu werden, und Sie sollte über ein Verfahren zum Verwalten von Problemen von dem Zeitpunkt an verfügen, an dem Sie bis zu Ihrer Lösung gemeldet werden. Informationen darüber, wie Supportmitarbeiter ein Problem diagnostiziert haben, sollten aufgezeichnet und in Zukunft verwendet werden, um zu vermeiden, dass die abgeschlossene Arbeit unnötig wiederholt wird.

</div>

<div>

## <a name="system-troubleshooting-process"></a>System Problembehandlungsprozess

Das folgende Diagramm zeigt den Systemproblem Behandlungsprozess und die Interaktionen mit anderen Betriebs Rollen.

**Flussdiagramm zur System Problembehandlung**

![Flussdiagramm zur System Problembehandlung](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Flussdiagramm zur System Problembehandlung")

  - **Klassifizieren und priorisieren**     Diese Aufgabe wird in der Regel vom Service Desk ausgeführt. Beispielsweise kann ein Problem als Softwareproblem oder Hardwareproblem gruppiert werden. Das Problem wird dann zur Untersuchung an das entsprechende Support Team weitergeleitet. Die Regeln für die Bestimmung der Priorität eines Problems sowie die Reaktionszeit und die Auflösungszeit sind in der Regel in der SLA definiert.

  - **Untersuchen und diagnostizieren**     Das entsprechende Support Team diagnostiziert das Problem und schlägt Änderungen vor, um das Problem zu beheben. Wenn die Lösung einfach ist und keine Änderungssteuerung erfordert, kann die Lösung sofort angewendet werden. Wenn die Lösung nicht einfach ist, sollte eine Änderungsanforderung ausgelöst werden, und die vorgeschlagene Arbeit sollte durch den Change Management-Prozess verwaltet werden, häufig unter einem "Fast-Track"-Verfahren. Alle vorgenommenen Änderungen sollten mit dem Konfigurationsverwaltungsprozess aufgezeichnet werden.

  - **Schließen und aufzeichnen**     Nach dem Testen der Lösung sollte das Problem geschlossen werden. Wenn aus dem Problem Lektionen gelernt werden müssen, sollte ein Eintrag in der Knowledge Base erstellt werden.

  - **Überprüfung und Trend Analyse**     Regelmäßige Überprüfungen der aktuellen Probleme sollten durchgeführt werden, um Problem Trends zu identifizieren. Wenn die Benutzer beispielsweise häufig Probleme mit langsamen Anmeldungen an Ihren lync-Websites auftreten, können Probleme mit der Netzwerkbandbreite verursacht werden. Die Problem Behebungszeiten und die Auswirkungen von Ausfällen auf die Systemverfügbarkeit sollten überprüft und mit der SLA verglichen werden. Die Person, die mit dem Kunden bei Dienstproblemen kontaktiert, wie beispielsweise ein Account Manager, sollte über wichtige Probleme informiert werden.

</div>

<div>

## <a name="issue-management-tools"></a>Problemverwaltungstools

Service Desk-Tools ermöglichen es Mitarbeitern, neue Probleme aufzuzeichnen, zu klassifizieren und zu priorisieren. Tools stellt dann die Workflowprozesse zur Verwaltung der Problem Dienstanforderung durch Untersuchung und Diagnose bereit, häufig von mehr als einem Support Team. Tools, die häufig Berichte über Lösungszeiten und Verlaufstrends bereitstellen, können auch eine Knowledge Base-Datenbank enthalten, die zum Durchsuchen früherer Probleme verwendet werden kann.

Die Microsoft Knowledge Base ist eine nützliche Aufzeichnung von Supportproblemen, die von Microsoft aufgetreten sind. Weitere Informationen finden Sie auf der Microsoft-Support-Website ( <https://go.microsoft.com/fwlink/?linkid=14898> ).

Bei Drittanbietersoftware ist in der Regel eine Anpassung erforderlich, die den Anforderungen der Organisation entspricht, beispielsweise die Organisation von Teams, Berichtsanforderungen und für die SLA erforderlichen Maßnahmen.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Zentralisierte vs. dezentrale Verwaltung

Rollen und Verantwortlichkeiten für die Ausführung von Systemverwaltungsaufgaben hängen davon ab, ob die Organisation einem zentralisierten Modell, einem dezentralisierten Modell oder einer Kombination aus beiden folgt.

  - **Zentrales Modell**     In einem zentralisierten Modell behalten eine oder mehrere administrative Gruppen die vollständige Kontrolle über die gesamte lync Server Umgebung bei. Dieses Verwaltungsmodell ähnelt einem Rechenzentrum, in dem alle Verwaltungsaufgaben von einer einzigen Informationstechnologiegruppe ausgeführt werden. Die Funktionen und Verantwortlichkeiten innerhalb des Teams sollten gemäß der Erfahrung und der Kenntnisse definiert werden.

  - **Dezentralisiertes Modell**     Dezentrale Organisationen befinden sich an mehreren geografischen Standorten und funktionieren lync Server Server und Administratoren Teams an unterschiedlichen Standorten. Beispielsweise kann es lokale Verwaltungsmitarbeiter und einen oder mehrere Server geben, auf denen lync Server 2013 für jedes Land/dieselbe Region laufen. Oder es kann ein Serverpool mit lync Server 2013 und ein Verwaltungsteam für Nordamerika und eins für Europa geben. Möglicherweise möchten Sie, dass Administratoren nur für Ihren eigenen geografischen Bereich zuständig sind und Berechtigungen zum Verwalten von Ressourcen in anderen Bereichen einschränken.

Mit lync Server können Sie auch bestimmte administrative Aufgaben mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) an bestimmte Personen oder Gruppen delegieren. Mit RBAC können Administratoren bestimmte Benutzerrechte und-Berechtigungen an andere Administratoren delegieren, um eine Teilmenge der möglichen administrativen Aufgaben auszuführen. Durch die Verwendung von RBAC hängt die Fähigkeit des Benutzers, bestimmte administrative Aufgaben auszuführen, von den dem Benutzer zugewiesenen RBAC-Rollen ab. RBAC enthält eine Liste der Cmdlets, die der Benutzer basierend auf den RBAC-Rollen ausführen kann, bei denen der Benutzer Mitglied ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

