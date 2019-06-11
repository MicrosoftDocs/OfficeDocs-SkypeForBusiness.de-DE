---
title: 'Lync Server 2013: Überprüfen von Ereignisprotokollen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Überprüfen von Ereignisprotokollen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-06_

Sie können die [Windows-Ereignisanzeige](http://go.microsoft.com/fwlink/p/?linkid=314067) verwenden, um Ereignisprotokolle anzuzeigen und Informationen zu Dienstfehlern, Replikationsfehlern in AD DS sowie Warnungen zu Systemressourcen wie virtuellem Arbeitsspeicher und Speicherplatz zu erhalten. Die Ereignisanzeige ist im Lieferumfang von Windows Server 2008 und 2012 enthalten.

Klicken Sie im lync Server 2013-Protokollierungstool beim Beenden der Debugsitzung auf **Protokolldateien analysieren** , um die Protokolldateien mithilfe des Snooper-Tools anzuzeigen.

Die Ereignisanzeige verwaltet Protokolle zu Anwendungs-, Sicherheits-und Systemereignissen auf dem Computer. Sowohl lync Server 2013 als auch Windows melden Warnungen und Fehlerbedingungen für die Ereignisprotokolle. Überprüfen Sie daher die Ereignisprotokolle täglich.

Verwenden Sie die Ereignisanzeige für folgende Zwecke:

  - Anzeigen und Verwalten von Ereignisprotokollen

  - Abrufen von Informationen zu Hardware-, Software-und Systemproblemen, die aufgelöst werden müssen.

  - Erkennen von Trends, die eine zukünftige Aktion erfordern

Ein Server, auf dem lync Server unter einem Windows Server-Betriebssystem ausgeführt wird, zeichnet Ereignisse in vier Typen von Protokollen auf:

  - **Anwendungsprotokolle**   das Anwendungsprotokoll enthält Ereignisse, die von Anwendungen oder Programmen protokolliert werden. Entwickler legen fest, welche Ereignisse protokolliert werden sollen. Beispielsweise kann ein Datenbankprogramm einen Datei Fehler im Anwendungsprotokoll aufzeichnen. Die meisten Ereignisse im Zusammenhang mit lync Server 2013 werden im Anwendungsprotokoll angezeigt.

  - **Sicherheitsprotokolle**   das Sicherheitsprotokoll zeichnet Ereignisse wie gültige und ungültige Anmeldeversuche zusätzlich zu Ereignissen auf, die sich auf die Ressourcennutzung beziehen, wie das Erstellen, öffnen oder Löschen von Dateien oder anderen Objekten. Wenn beispielsweise die Anmeldeüberwachung aktiviert ist, werden Versuche zur Anmeldung am System im Sicherheitsprotokoll aufgezeichnet.

  - **Systemprotokolle**   das Systemprotokoll enthält Ereignisse, die von Windows-Systemkomponenten protokolliert werden. Beispielsweise wird der Fehler eines Treibers oder einer anderen Systemkomponente zum Laden während des Starts im Systemprotokoll aufgezeichnet. Die von Systemkomponenten protokollierten Ereignistypen sind vom Server vorgegeben.

  - **Lync Server 2013**   das Protokollierungstool zeichnet wichtige Ereignisse auf, die sich auf Authentifizierung, Verbindungen und Benutzeraktionen beziehen. Nachdem Sie die Diagnoseprotokollierung aktiviert haben, können Sie die Protokolleinträge in der Ereignisanzeige anzeigen.

<div>


> [!NOTE]  
> Es wird nicht empfohlen, die maximalen Protokollierungseinstellungen zu verwenden, es sei denn, Sie werden von den Microsoft-Kundendienst angewiesen. Die maximale Protokollierung führt zu erheblichen Ressourcen und kann viele "falsch positive" geben, das heißt, Fehler, die nur bei maximaler Protokollierung protokolliert werden, aber wirklich erwartet werden und keine Besorgnis erregend sind. Wir empfehlen außerdem, die Diagnoseprotokollierung nicht dauerhaft zu aktivieren. Verwenden Sie es nur bei der Problembehandlung.



</div>

In jedem Ereignisanzeigeprotokoll zeichnet lync Server 2013 Informations-, Warnungs-und Fehlerereignisse auf. Überwachen Sie diese Protokolle genau, um die Typen von Transaktionen zu verfolgen, die auf den lync Server 2013-Servern durchgeführt werden. Sie sollten die Protokolle in regelmäßigen Abständen archivieren oder das automatische Rollover verwenden, um nicht genügend Speicherplatz zu schaffen. Da Protokolldateien eine begrenzte Menge an Speicherplatz belegen können, erhöhen Sie die Protokollgröße (beispielsweise auf 50 MB), und legen Sie Sie auf Overwrite fest, damit der lync Server 2013-Server weiterhin neue Ereignisse schreiben kann.

Sie können die Ereignisprotokollverwaltung auch mithilfe der folgenden Tools und Technologien automatisieren:

  - System Center Operations Manager überwacht den Zustand und die Verwendung von lync Server 2013-Servern. Das lync Server 2013 Management Pack für Operations Manager erweitert Operations Manager durch die Bereitstellung spezieller Überwachung für Server, auf denen lync Server 2013 ausgeführt wird.

  - Das lync Server 2013-Management Pack für Operations Manager überwacht die Standard-und Enterprise-Edition von lync Server 2013. Diese Version enthält auch das QoE-Management Pack (Quality of Experience), das zuvor ein separates Management Pack war.

Überwachte Typen sind Ereignisprotokolleinträge, Leistungsindikatoren und statusbehaftete Überwachung von QoE. Diese Version des Management Packs überwacht nur lync Server 2013 und 2010 und kann nicht zum Überwachen von Office Communications Server 2007 verwendet werden.

Das Management Pack bietet die folgenden Features:

  - Benachrichtigungen, die darauf hindeuten, dass der Dienst Auswirkungen auf Ereignisse hat

  - Warnungen, die die Konfiguration angeben, und andere Probleme, die sich nicht auf Dienste auswirken

  - Statusüberwachung der lync Server-Dienste

  - Produkt wissen: Ursache und Lösung identifizierter Probleme

Weitere Informationen zum lync Server 2013 Management Pack finden Sie unter über [Wachen von lync Server 2013 mit System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Ereignis Kamm**   mit dem Event Comb-Tool werden bestimmte Ereignisse aus den Ereignisprotokollen von mehreren Computern an einem zentralen Speicherort erfasst. Damit können Sie nur die Ereignis-IDs oder Ereignisquellen melden, die Sie angeben. Weitere Informationen zum Event Comb finden Sie auf der Website [Kontosperrung und Verwaltungs Tools](http://go.microsoft.com/fwlink/?linkid=35607) .

**Ereignisauslöser**   in Windows Server 2012 Sie können "eine Aufgabe an dieses Ereignis anfügen" in der Windows-Ereignisanzeige, in der ein Administrator entweder ein Programm ausführen, eine e-Mail-Nachricht senden oder eine auf dem Bildschirm angezeigte Nachricht anzeigen kann. Weitere Informationen zu diesem Feature finden Sie unter Windows Server 2008 R2-Thema [Ausführen einer Aufgabe als Antwort auf ein bestimmtes Ereignis](http://technet.microsoft.com/en-us/library/cc748900.aspx). Sie können auch Befehlszeilentools wie "EventTrigger. exe" verwenden, um Ereignisprotokolle zu erstellen und zu Abfragen und Programme mit bestimmten protokollierten Ereignissen zu verknüpfen. Mit Eventtriggers. exe können Sie Ereignisauslöser erstellen, die Programme ausführen, wenn bestimmte Ereignisse auftreten.

<div>

## <a name="see-also"></a>Siehe auch


[Windows-Ereignisanzeige](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

