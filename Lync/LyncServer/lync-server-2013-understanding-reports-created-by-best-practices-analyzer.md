---
title: 'Lync Server 2013: Grundlegendes zu berichten, die von Best Practices Analyzer erstellt wurden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56556d209e073be49a6c0eb2aa30461a06930238
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Grundlegendes zu berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

Best Practices Analyzer bietet verschiedene Berichttypen zur Vereinfachung der Analyse und der Lösung von Problemen. Best Practices Analyzer identifiziert Probleme wie z. B. Fehler, Warnungen und andere Informationen.

<div>

## <a name="reports"></a>Berichte

Sie können auf die Ergebnisse einer Überprüfung zugreifen, indem Sie jeden der folgenden Berichte anzeigen:

  - **Listen Berichte Listen**Berichte werden nach bestimmten Kriterien sortiert.    Sie können die Ergebnisse nach Klasse, Schweregrad oder Problem anordnen. Wenn Sie die Ergebnisse beispielsweise nach Klasse anordnen, befinden sich Probleme im Zusammenhang mit Directors im Directors-Abschnitt des Berichts. Sie können alle Probleme oder nur die Informationselemente anzeigen. Sie können einen Listenbericht nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

  - **Strukturberichte**   Strukturberichte werden nach den Regeln organisiert, die zum Ausführen der Überprüfung und anderen Optionen verwendet werden, die Sie zum Zeitpunkt der Überprüfung angegeben haben. Probleme im Zusammenhang mit Testtopologieregeln befinden sich z. B. im Testtopologie-Abschnitt des Berichts. Sie können Details zu allen Problemen oder nur eine Zusammenfassung der Probleme anzeigen. Sie können einen Strukturbericht nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

  - **Andere Berichts**   Elemente in anderen Berichten enthalten das Laufzeitprotokoll der Aufgaben, die in der Überprüfung enthalten waren. Sie können die Elemente in anderen Berichten nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

</div>

<div>

## <a name="issues"></a>Probleme

Die vom Best Practices Analyzer generierten Berichte geben bestimmte Probleme an, die während der Überprüfung Ihrer Umgebung identifiziert wurden, einschließlich folgender Problemtypen:

  - **Fehler**   : wichtige Probleme, bei denen Sie eine Änderung in Ihrer Umgebung vornehmen müssen. Wenn beispielsweise lync Server 2013 Kernkomponenten nicht installiert sind, wird ein Fehler protokolliert.

    Als Fehler klassifizierte Probleme sind im Bericht mit einem roten X-Symbol gekennzeichnet. Fehler werden auf der Registerkarte **Alle Probleme** in der Ansicht **Listenberichte** und auf den Registerkarten **Detaillierte Ansicht** und **Zusammenfassungsansicht** der Ansicht **Strukturberichte** angezeigt. Wenn Sie in einem Bericht einen bestimmten Fehler nicht anzeigen möchten, können Sie festlegen, dass der Fehler für eine Instanz oder alle Instanzen dieses Fehlers im Bericht nicht angezeigt wird. Der Fehler wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte** angezeigt, außer Sie ändern die Einstellung und legen fest, dass der Fehler im Bericht angezeigt wird.

  - **Warnungen**   Probleme, die nicht mit der Implementierung einer bewährten Methode konsistent sind. Dies kann u. U. die Notwendigkeit einer Änderung in Ihrer Umgebung anzeigen. Bei dem Problem könnte es sich um ein bekanntes Problem mit einer bestimmten Einstellung handeln, die Sie nicht ändern müssen. Auf einem Server nicht gestartete Dienste werden z. B. als Warnungen protokolliert.

    Als Warnungen klassifizierte Probleme sind im Bericht mit einem dreieckigen gelben Warnsymbol gekennzeichnet. Warnungen werden auf der Registerkarte **Alle Probleme** der Ansicht **Listenberichte** sowie auf den Registerkarten **Detaillierte Ansicht** und **Zusammenfassungsansicht** der Ansicht **Strukturberichte** angezeigt. Wenn Sie in einem Bericht einen bestimmten Fehler nicht anzeigen möchten, können Sie festlegen, dass der Fehler für eine Instanz oder alle Instanzen dieses Fehlers im Bericht nicht angezeigt wird. Die Warnung wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte** angezeigt, außer Sie ändern die Einstellung und legen fest, dass die Warnung im Bericht angezeigt wird.

  - **Informationen**   umfassen alle Probleme, die nicht als Fehler oder Warnungen klassifiziert sind. Beispielsweise wird die Anzahl der lync Server 2013 Standard Edition-Server-Objekte in Active Directory-Domänendienste als Informationsproblem klassifiziert.

    Informationsprobleme werden auf der Registerkarte **Alle Probleme** der Ansicht **Listenberichte** und der Registerkarte **Detaillierte Ansicht** der Ansicht **Strukturberichte** angezeigt.

Das lync Server 2013, Best Practices Analyzer macht keine Änderungen an Ihrer Umgebung, um Probleme zu beheben. Durch die Überprüfung werden lediglich potenzielle Probleme ermittelt und Berichte bereitgestellt, die Informationen zu Lösungen für alle ermittelten Probleme enthalten.

Wenn Sie auf ein Problem klicken, werden eine Erklärung sowie einige Optionen für bestimmte Probleme angezeigt. Anschließend können Sie eine der folgenden Aktionen ausführen:

  - Ausführlichere Informationen zum Problem sowie zu Lösungen dafür suchen.

  - Das Anzeigen von Problemen in Berichten beenden:

      - Das Anzeigen von Problemen für die ausgewählte Instanz beenden.

      - Das Anzeigen von Problemen für alle Instanzen des Problems beenden.

    Zum Anzeigen der Probleme, die in Berichten nicht mehr angezeigt werden, öffnen Sie die Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte**. Dort können Sie festlegen, dass Probleme wieder in Berichten angezeigt werden.

Ausführliche Informationen zum Beheben bestimmter Probleme finden Sie unter [analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert wurden](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>
