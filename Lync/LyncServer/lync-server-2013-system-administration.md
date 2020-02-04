---
title: 'Lync Server 2013: System Verwaltung'
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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>System Verwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-18_

Die System Administration umfasst die täglichen administrativen Aufgaben, sowohl geplant als auch on-Demand, die erforderlich sind, um ein IT-System reibungslos funktionieren zu lassen. In der Regel werden Systemverwaltungsaufgaben durch schriftliche Verfahren abgedeckt. Mithilfe dieser Verfahren können Sie sicherstellen, dass alle Supportmitarbeiter dieselben Standardtools und-Methoden verwenden.

In einer lync-Umgebung umfassen typische Systemverwaltungsaufgaben das Sichern und Archivieren von Pools, das Überwachen von Protokollen, das Erstellen und Verwalten von Benutzern und das Aktualisieren der Antivirensoftware.

<div>

## <a name="system-troubleshooting"></a>System Problembehandlung

Eine Organisation muss bereit sein, mit unerwarteten Problemen umzugehen, und es sollte ein Verfahren zum Verwalten von Problemen ab dem Zeitpunkt vorhanden sein, zu dem Sie bis zu Ihrer Lösung gemeldet werden. Informationen dazu, wie das Supportpersonal ein Problem diagnostiziert hat, sollten aufgezeichnet und in Zukunft verwendet werden, um eine unnötige Wiederholung der abgeschlossenen Arbeit zu vermeiden.

</div>

<div>

## <a name="system-troubleshooting-process"></a>System Problembehandlungsprozess

Das folgende Diagramm zeigt den Systemproblem Behandlungsprozess und die Interaktionen mit anderen Vorgangs Rollen.

**System Problembehandlung-Flussdiagramm**

![Flussdiagramm für die Systemproblembehandlung](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Flussdiagramm für die Systemproblembehandlung")

  - **Klassifizieren und priorisieren**   diese Aufgabe wird in der Regel vom Service Desk ausgeführt. Beispielsweise kann ein Problem als Softwareproblem oder Hardwareproblem gruppiert werden. Das Problem wird dann zur Untersuchung an das geeignete Support Team weitergeleitet. Die Regeln für die Bestimmung der Priorität eines Problems sowie die Zeit für die Antwort und die Zeit zum beheben werden in der Regel in der SLA definiert.

  - **Untersuchen und diagnostizieren**   des entsprechenden Support Teams, das das Problem diagnostiziert, und schlägt Änderungen vor, um das Problem zu beheben. Wenn die Lösung einfach ist und keine Änderungssteuerung erforderlich ist, kann die Lösung sofort angewendet werden. Wenn es sich nicht um eine einfache Lösung handelt, sollte ein Änderungsantrag gestellt und die vorgeschlagene Arbeit vom Change Management-Prozess verwaltet werden, häufig unter einem "Fast-Tracking"-Verfahren. Alle vorgenommenen Änderungen sollten mithilfe des Konfigurationsverwaltungsprozesses aufgezeichnet werden.

  - **Schließen und aufzeichnen**   nachdem Sie die Lösung getestet haben, sollte das Problem geschlossen werden. Wenn es Lektionen gibt, die aus dem Problem zu lernen sind, sollte ein Eintrag in der Knowledge Base erstellt werden.

  - **Überprüfungs-und Trend Analyse**   regelmäßige Reviews zu aktuellen Problemen sollten durchgeführt werden, um Problem Trends zu erkennen. Wenn die Benutzer beispielsweise häufig Probleme mit langsamen Anmeldungen an Ihren lync-Websites haben, kann dies zu Problemen mit der Netzwerkbandbreite führen. Die Problem Behebungszeiten und die Auswirkungen etwaiger Ausfälle auf die Systemverfügbarkeit sollten überprüft und mit der SLA verglichen werden. Die Person, die mit dem Kunden bei Dienstproblemen unterhält, beispielsweise ein Kontomanager, sollte über wichtige Probleme informiert werden.

</div>

<div>

## <a name="issue-management-tools"></a>Problemverwaltungstools

Mit Service Desk-Tools können Mitarbeiter neue Probleme aufzeichnen, klassifizieren und priorisieren. Die Tools stellen dann die Workflowprozesse bereit, um die Problem Dienstanforderung durch Untersuchung und Diagnose zu verwalten, häufig von mehr als einem Support Team. Tools, die häufig Berichte zu auflösungszeiten und Verlaufstrends bereitstellen, können auch eine Knowledge Base-Datenbank enthalten, die zum Durchsuchen vergangener Probleme verwendet werden kann.

Die Microsoft Knowledge Base ist eine nützliche Aufzeichnung von Supportproblemen, die von Microsoft aufgetreten sind. Weitere Informationen finden Sie auf der Microsoft-Support Website<http://go.microsoft.com/fwlink/?linkid=14898>().

Für Software von Drittanbietern ist in der Regel eine Anpassung an die Anforderungen der Organisation erforderlich, wie etwa die Organisation von Teams, die Berichterstattungsanforderungen und die erforderlichen Maßnahmen für die SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Zentralisierte vs. dezentrale Verwaltung

Rollen und Zuständigkeiten für die Durchführung von Systemverwaltungsaufgaben hängen davon ab, ob die Organisation einem zentralisierten Modell, einem dezentralisierten Modell oder einer Kombination aus beiden folgt.

  - **Zentrales Modell**   in einem zentralisierten Modell verwalten eine oder mehrere administrative Gruppen die vollständige Kontrolle über die gesamte lync Server-Umgebung. Dieses Verwaltungsmodell ähnelt einem Rechenzentrum, in dem alle Verwaltungsaufgaben von einer einzigen Informationstechnologiegruppe ausgeführt werden. Rollen und Zuständigkeiten innerhalb des Teams sollten nach Erfahrung und Fachwissen definiert werden.

  - **Dezentrale Modelle**   dezentralisierte Organisationen befinden sich an verschiedenen geografischen Standorten und verfügen über funktionierende lync Server-Server und Administratoren Teams an verschiedenen Speicherorten. So können beispielsweise lokale Verwaltungsmitarbeiter und mindestens ein Server, auf dem lync Server 2013 ausgeführt wird, für jedes Land/jede Region vorhanden sein. Möglicherweise gibt es einen Serverpool, auf dem lync Server 2013 und ein Verwaltungsteam für Nordamerika und eines für Europa ausgeführt werden. Manchmal möchten Sie möglicherweise, dass Administratoren nur für Ihren eigenen geografischen Bereich verantwortlich sind und Berechtigungen zum Verwalten von Ressourcen in anderen Bereichen einschränken.

Mit lync Server können Sie auch bestimmte administrative Aufgaben mithilfe der rollenbasierten Zugriffssteuerung an bestimmte Personen oder Gruppen delegieren. Mit RBAC können Administratoren bestimmte Benutzerrechte und Berechtigungen an andere Administratoren delegieren, um eine Teilmenge der möglichen administrativen Aufgaben auszuführen. Durch die Verwendung von RBAC hängt die Fähigkeit des Benutzers, bestimmte administrative Aufgaben auszuführen, von den Rollen ab, die dem Benutzer zugewiesen sind. RBAC bietet eine Liste der Cmdlets, die der Benutzer basierend auf den RBAC-Rollen ausführen kann, in denen der Benutzer Mitglied ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

