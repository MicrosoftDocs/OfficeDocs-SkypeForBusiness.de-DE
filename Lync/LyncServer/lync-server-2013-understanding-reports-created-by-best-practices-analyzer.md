---
title: 'Lync Server 2013: Grundlegendes zu berichten, die von Best Practices Analyzer erstellt wurden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0903c3bafc4017d5455c188c66de3e1f2cf0b178
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Grundlegendes zu berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Best Practices Analyzer bietet mehrere Arten von Berichten, die zur Vereinfachung der Analyse und Lösung von Problemen organisiert sind. Best Practices Analyzer identifiziert Probleme wie Fehler, Warnungen und weitere Informationen.

<div>

## <a name="reports"></a>Berichte

Sie können auf die Ergebnisse eines Scans zugreifen, indem Sie die folgenden Berichte anzeigen:

  - **** Listen Berichte sind nach bestimmten Kriterien geordnet.    Sie können die Ergebnisse nach Kurs, Schweregrad oder Problem sortieren. Wenn Sie beispielsweise die Ergebnisse nach Kursen organisieren, werden Probleme im Zusammenhang mit Directors im Abschnitt Directors des Berichts berücksichtigt. Sie können alle Probleme oder nur die Informationselemente anzeigen. Sie können einen Listenbericht nach bestimmten Elementen wie Arbeitsspeicher durchsuchen. Sie können den Bericht auch drucken oder exportieren.

  - ****   Strukturberichte Strukturberichte sind nach den Regeln angeordnet, die zum Ausführen der Überprüfung und anderer Optionen, die Sie zum Zeitpunkt der Ausführung des Scans angegeben haben, verwendet werden. So werden beispielsweise Probleme im Zusammenhang mit den Testtopologie-Regeln im Abschnitt Testtopologie des Berichts berücksichtigt. Sie können die Details aller Probleme anzeigen oder nur eine Zusammenfassung der Probleme. Sie können einen Strukturbericht nach bestimmten Elementen wie Arbeitsspeicher durchsuchen. Sie können den Bericht auch drucken oder exportieren.

  - **Andere Berichts**   Elemente in anderen Berichten umfassen das Laufzeitprotokoll der Aufgaben, die in die Überprüfung einbezogen wurden. Sie können die Elemente in anderen Berichten nach bestimmten Elementen wie Arbeitsspeicher durchsuchen. Sie können den Bericht auch drucken oder exportieren.

</div>

<div>

## <a name="issues"></a>Fragen

Die von Best Practices Analyzer generierten Berichte zeigen spezifische Probleme an, die während der Überprüfung Ihrer Umgebung identifiziert werden, einschließlich der folgenden Arten von Problemen:

  - **Fehler**   kritische Probleme, bei denen Sie eine Änderung in Ihrer Umgebung erforderlich machen. Wenn beispielsweise lync Server 2013 Core Components nicht installiert ist, wird ein Fehler protokolliert.
    
    Probleme, die als Fehler klassifiziert sind, werden im Bericht mit einem roten X-Symbol gekennzeichnet. Fehler werden auf der Registerkarte **alle Probleme** der Ansicht **Listen Berichte** , auf der Registerkarte **detaillierte Ansicht** und auf der Registerkarte **Zusammenfassung** der Ansicht **Strukturberichte** angezeigt. Wenn Sie keinen bestimmten Fehler in einem Bericht sehen möchten, können Sie angeben, dass der Fehler nicht für eine einzelne Instanz oder für alle Instanzen dieses Fehlers im Bericht angezeigt werden soll. Der Fehler wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **andere Berichte** angezeigt, es sei denn, Sie ändern die Einstellung und geben an, dass der Fehler im Bericht angezeigt werden soll.

  - **Warnungs**   Probleme, die nicht mit der Implementierung einer bewährten Methode in Einklang stehen. Dies kann darauf hindeuten, dass eine Änderung in Ihrer Umgebung erforderlich ist. Das Problem kann ein bekanntes Problem mit einer bestimmten Einstellung sein, die nicht geändert werden muss. Dienste, die nicht auf einem Server gestartet werden, werden beispielsweise als Warnungen protokolliert.
    
    Probleme, die als Warnungen klassifiziert sind, werden im Bericht mit einem dreieckigen gelben Warnsymbol gekennzeichnet. Warnungen werden auf der Registerkarte **alle Probleme** in der **Ansicht Listen Berichte** sowie auf der Registerkarte **detaillierte Ansicht** und auf der Registerkarte **Zusammenfassung** der Ansicht **Strukturberichte** angezeigt. Wenn Sie keinen bestimmten Fehler in einem Bericht sehen möchten, können Sie angeben, dass der Fehler nicht für eine einzelne Instanz oder für alle Instanzen dieses Fehlers im Bericht angezeigt werden soll. Die Warnung wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **andere Berichte** angezeigt, es sei denn, Sie ändern die Einstellung und geben an, dass die Warnung im Bericht angezeigt werden soll.

  - **Informationen**   umfasst alle Probleme, die nicht als Fehler oder Warnungen klassifiziert sind. Beispielsweise wird die Anzahl der Serverobjekte von lync Server 2013 Standard Edition in den Active Directory-Domänendiensten als Informationsproblem eingestuft.
    
    Informationsprobleme werden auf der Registerkarte **alle Probleme** in der Ansicht **Listen Berichte** und auf der Registerkarte **detaillierte Ansicht** der Ansicht **Strukturberichte** angezeigt.

Der lync Server 2013, Best Practices Analyzer, nimmt keine Änderungen an Ihrer Umgebung vor, um Probleme zu beheben. Bei der Überprüfung werden nur potenzielle Probleme erkannt, und es werden Berichte bereitgestellt, die Informationen zum Beheben der einzelnen Probleme enthalten.

Wenn Sie auf ein Problem klicken, werden eine Erläuterung und einige Optionen für bestimmte Probleme angezeigt. Anschließend können Sie eine der folgenden Aktionen ausführen:

  - Hier finden Sie ausführlichere Informationen zu diesem Problem und Lösungsvorschläge.

  - Beenden der Anzeige von Problemen in Berichten:
    
      - Beenden der Anzeige von Problemen für die ausgewählte Instanz
    
      - Beenden Sie die Anzeige von Problemen für alle Instanzen dieses Problems.
    
    Um die Probleme anzuzeigen, die in Berichten nicht mehr angezeigt werden, wechseln Sie zur Registerkarte **Ausgeblendete Elemente** in der Ansicht **andere Berichte** . Von dort aus können Sie angeben, dass Probleme in Berichten erneut angezeigt werden sollen.

Details zum Beheben bestimmter Probleme finden Sie unter [analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

