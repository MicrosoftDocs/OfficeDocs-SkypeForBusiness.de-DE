---
title: 'Lync Server 2013: Überprüfen von Ereignisprotokollen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15fb690dc213dbe22377b988f82dd59d6eb8a03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Überprüfen von Ereignisprotokollen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-06_

Sie können die [Windows-Ereignisanzeige](http://go.microsoft.com/fwlink/p/?linkid=314067) verwenden, um Ereignisprotokolle anzuzeigen und Informationen zu Dienstfehlern, Replikationsfehlern im AD DS und Warnungen zu Systemressourcen wie virtuellem Arbeitsspeicher und Speicherplatz zu erhalten. Die Ereignisanzeige ist in Windows Server 2008 und 2012 enthalten.

Wenn Sie im lync Server 2013 Protokollierungstool die Debugsitzung beenden, klicken Sie auf **Protokolldateien analysieren** , um die Protokolldateien mithilfe des Tools Snooper anzuzeigen.

Die Ereignisanzeige verwaltet Protokolle zu Anwendungs-, Sicherheits-und Systemereignissen auf dem Computer. Sowohl lync Server 2013 als auch Windows melden Warnungen und Fehlerbedingungen für die Ereignisprotokolle. Überprüfen Sie daher die Ereignisprotokolle täglich.

Verwenden Sie die Ereignisanzeige für Folgendes:

  - Anzeigen und Verwalten von Ereignisprotokollen.

  - Erhalten Sie Informationen zu Hardware-, Software-und Systemproblemen, die behoben werden müssen.

  - Identifizieren Sie Trends, die zukünftige Aktionen erfordern.

Ein Server, auf dem lync Server auf einem Windows Server-Betriebssystem läuft, zeichnet Ereignisse in vier Protokolltypen auf:

  - **Anwendungsprotokolle**   das Anwendungsprotokoll enthält Ereignisse, die von Anwendungen oder Programmen protokolliert werden. Entwickler legen fest, welche Ereignisse protokolliert werden. Ein Datenbankprogramm könnte z. B. einen Dateifehler im Anwendungsprotokoll aufzeichnen. Die meisten lync Server 2013 bezogenen Ereignisse werden im Anwendungsprotokoll angezeigt.

  - **Sicherheitsprotokolle**   das Sicherheitsprotokoll zeichnet Ereignisse wie gültige und ungültige Anmeldeversuche zusätzlich zu Ereignissen im Zusammenhang mit der Ressourcenverwendung wie erstellen, öffnen oder Löschen von Dateien oder anderen Objekten auf. Wenn Anmeldeüberwachung aktiviert ist, werden z. B. Anmeldeversuche am System im Sicherheitsprotokoll aufgezeichnet.

  - **Systemprotokolle**   das Systemprotokoll enthält Ereignisse, die von Windows-System Komponenten protokolliert werden. Der Ladefehler eines Treibers oder einer anderen Systemkomponente während des Startvorgangs wird z. B. im Systemprotokoll aufgezeichnet. Die von Systemkomponenten protokollierten Ereignistypen werden von Server im Vorfeld festgelegt.

  - **Lync Server 2013**   das Protokollierungstool zeichnet wichtige Ereignisse im Zusammenhang mit Authentifizierung, Verbindungen und Benutzeraktionen auf. Nachdem Sie die Diagnoseprotokollierung aktiviert haben, können Sie die Protokolleinträge in der Ereignisanzeige anzeigen.

<div>


> [!NOTE]  
> Es wird nicht empfohlen, die maximalen Protokollierungseinstellungen zu verwenden, es sei denn, Sie werden vom Microsoft-Kundendienst dazu aufgefordert. Die maximale Protokollierung entwässert erhebliche Ressourcen und kann viele "falsch positive Ergebnisse" verursachen, also Fehler, die nur bei der maximalen Protokollierung protokolliert werden, aber wirklich erwartet werden und keine Anlass zur Besorgnis geben. Außerdem wird empfohlen, die Diagnoseprotokollierung nicht dauerhaft zu aktivieren. Verwenden Sie sie nur zur Problembehandlung.



</div>

In den einzelnen Protokollen der Ereignisanzeige erfasst lync Server 2013 Informationen, Warnungen und Fehlerereignisse. Überwachen Sie diese Protokolle eng, um die Transaktionstypen nachzuverfolgen, die auf den lync Server 2013 Servern ausgeführt werden. Sie sollten die Protokolle in regelmäßigen Abständen archivieren oder die automatische Rolloverfunktion verwenden, damit stets ausreichend Speicherplatz vorhanden ist. Da Protokolldateien eine begrenzte Menge an Speicherplatz belegen können, müssen Sie die Protokollgröße vergrößern (beispielsweise auf 50 MB) und diese auf Overwrite festlegen, damit der lync Server 2013 Server weiterhin neue Ereignisse schreiben kann.

Sie können die Ereignisprotokollverwaltung auch mithilfe der folgenden Tools und Technologien automatisieren:

  - System Center Operations Manager überwacht die Integrität und die Verwendung von lync Server 2013 Servern. Lync Server 2013 Management Pack für Operations Manager erweitert Operations Manager durch die Bereitstellung spezieller Überwachung für Server, auf denen lync Server 2013 ausgeführt wird.

  - Das lync Server 2013 Management Pack für Operations Manager überwacht Standard-und Enterprise Edition von lync Server 2013. In dieser Version ist auch das QoE-Management Pack (Quality of Experience) integriert, das zuvor ein separates Management Pack war.

Überwachte Typen sind Ereignisprotokolleinträge, Leistungsindikatoren und Stateful-Überwachung von QoE. Diese Version des Management Packs überwacht nur lync Server 2013 und 2010 und kann nicht zum Überwachen von Office Communications Server 2007 verwendet werden.

Das Management Pack bietet die folgenden Features:

  - Warnungen, die den Dienst beeinflussen, der Ereignisse angibt

  - Warnungen, die die Konfiguration und andere Probleme mit nicht-Dienst Auswirkungen betreffen

  - Statusüberwachung von lync Server Diensten

  - Produkt wissen: Ursache und Lösung identifizierter Probleme

Weitere Informationen zu lync Server 2013 Management Pack finden Sie unter [Monitoring lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Ereignis Kamm**   mit dem Tool "Ereignis Kamm" werden bestimmte Ereignisse aus den Ereignisprotokollen mehrerer Computer an einem zentralen Speicherort erfasst. Sie können nur die Ereignis-IDs oder Ereignisquellen melden, die es angibt. Weitere Informationen zum Ereignis Kamm finden Sie auf der Website für [Kontosperrung und Verwaltungs Tools](http://go.microsoft.com/fwlink/?linkid=35607) .

**Ereignisauslöser**   in Windows Server 2012 können Sie "eine Aufgabe an dieses Ereignis anfügen" in der Windows-Ereignisanzeige, bei der ein Administrator entweder ein Programm ausführen, eine e-Mail-Nachricht senden oder eine Bildschirm Nachricht anzeigen kann. Weitere Informationen zu diesem Feature finden Sie im Windows Server 2008 R2 Thema [Ausführen einer Aufgabe als Reaktion auf ein bestimmtes Ereignis](http://technet.microsoft.com/library/cc748900.aspx). Sie können auch Befehlszeilentools wie "EventTrigger. exe" zum Erstellen und Abfragen von Ereignisprotokollen und zum Zuordnen von Programmen zu bestimmten protokollierten Ereignissen verwenden. Mit Eventtriggers. exe können Sie Ereignisauslöser erstellen, die Programme ausführen, wenn bestimmte Ereignisse eintreten.

<div>

## <a name="see-also"></a>Siehe auch


[Windows-Ereignisanzeige](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

