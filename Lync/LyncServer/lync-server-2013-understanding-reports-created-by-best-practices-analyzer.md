---
title: Grundlegendes zu den von Best Practices Analyzer erstellten Berichten
TOCTitle: Grundlegendes zu den von Best Practices Analyzer erstellten Berichten
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg591344(v=OCS.15)
ms:contentKeyID: 49293248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grundlegendes zu den von Best Practices Analyzer erstellten Berichten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Best Practices Analyzer bietet verschiedene Berichttypen zur Vereinfachung der Analyse und der Lösung von Problemen. Best Practices Analyzer identifiziert Probleme wie z. B. Fehler, Warnungen und andere Informationen.

## Berichte

Sie können auf die Ergebnisse einer Überprüfung zugreifen, indem Sie jeden der folgenden Berichte anzeigen:

  - **Listenberichte**   Listenberichte sind nach bestimmten Kriterien angeordnet. Sie können die Ergebnisse nach Klasse, Schweregrad oder Problem anordnen. Wenn Sie die Ergebnisse beispielsweise nach Klasse anordnen, befinden sich Probleme im Zusammenhang mit Directors im Directors-Abschnitt des Berichts. Sie können alle Probleme oder nur die Informationselemente anzeigen. Sie können einen Listenbericht nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

  - **Strukturberichte**   Strukturberichte werden nach den Regeln angeordnet, die zum Durchführen der Überprüfung verwendet werden, sowie nach weiteren Optionen, die Sie zum Zeitpunk der Durchführung der Überprüfung angegeben haben. Probleme im Zusammenhang mit Testtopologieregeln befinden sich z. B. im Testtopologie-Abschnitt des Berichts. Sie können Details zu allen Problemen oder nur eine Zusammenfassung der Probleme anzeigen. Sie können einen Strukturbericht nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

  - **Andere Berichte**   Elemente in anderen Berichten umfassen das Laufzeitprotokoll zu Aufgaben, die in die Überprüfung eingeschlossen waren. Sie können die Elemente in anderen Berichten nach bestimmten Elementen wie z. B. Arbeitsspeicher durchsuchen. Sie können den Bericht auch ausdrucken oder exportieren.

## Probleme

Die vom Best Practices Analyzer generierten Berichte geben bestimmte Probleme an, die während der Überprüfung Ihrer Umgebung identifiziert wurden, einschließlich folgender Problemtypen:

  - **Fehler**   Schwerwiegende Probleme, die eine Änderung in Ihrer Umgebung erfordern. Sind beispielsweise Hauptkomponenten von Lync Server 2013 nicht installiert, wird ein Fehler protokolliert
    
    Als Fehler klassifizierte Probleme sind im Bericht mit einem roten X-Symbol gekennzeichnet. Fehler werden auf der Registerkarte **Alle Probleme** in der Ansicht **Listenberichte** und auf den Registerkarten **Detaillierte Ansicht** und **Zusammenfassungsansicht** der Ansicht **Strukturberichte** angezeigt. Wenn Sie in einem Bericht einen bestimmten Fehler nicht anzeigen möchten, können Sie festlegen, dass der Fehler für eine Instanz oder alle Instanzen dieses Fehlers im Bericht nicht angezeigt wird. Der Fehler wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte** angezeigt, außer Sie ändern die Einstellung und legen fest, dass der Fehler im Bericht angezeigt wird.

  - **Warnungen**   Probleme, die nicht mit der Implementierung einer bewährten Methode konsistent sind. Dies kann u. U. die Notwendigkeit einer Änderung in Ihrer Umgebung anzeigen. Bei dem Problem könnte es sich um ein bekanntes Problem mit einer bestimmten Einstellung handeln, die Sie nicht ändern müssen. Auf einem Server nicht gestartete Dienste werden z. B. als Warnungen protokolliert.
    
    Als Warnungen klassifizierte Probleme sind im Bericht mit einem dreieckigen gelben Warnsymbol gekennzeichnet. Warnungen werden auf der Registerkarte **Alle Probleme** der Ansicht **Listenberichte** sowie auf den Registerkarten **Detaillierte Ansicht** und **Zusammenfassungsansicht** der Ansicht **Strukturberichte** angezeigt. Wenn Sie in einem Bericht einen bestimmten Fehler nicht anzeigen möchten, können Sie festlegen, dass der Fehler für eine Instanz oder alle Instanzen dieses Fehlers im Bericht nicht angezeigt wird. Die Warnung wird dann nur auf der Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte** angezeigt, außer Sie ändern die Einstellung und legen fest, dass die Warnung im Bericht angezeigt wird.

  - **Informationen**   Enthält alle Probleme, die nicht als Fehler oder Warnungen klassifiziert sind. Die Anzahl von Lync Server 2013-Standard Edition-Serverobjekten in Active Directory-Domänendienste wird beispielsweise als Informationsproblem klassifiziert.
    
    Informationsprobleme werden auf der Registerkarte **Alle Probleme** der Ansicht **Listenberichte** und der Registerkarte **Detaillierte Ansicht** der Ansicht **Strukturberichte** angezeigt.

Der Best Practices Analyzer in Lync Server 2013 nimmt keine Änderungen an Ihrer Umgebung vor, um Probleme zu lösen. Durch die Überprüfung werden lediglich potenzielle Probleme ermittelt und Berichte bereitgestellt, die Informationen zu Lösungen für alle ermittelten Probleme enthalten.

Wenn Sie auf ein Problem klicken, werden eine Erklärung sowie einige Optionen für bestimmte Probleme angezeigt. Anschließend können Sie eine der folgenden Aktionen ausführen:

  - Ausführlichere Informationen zum Problem sowie zu Lösungen dafür suchen.

  - Das Anzeigen von Problemen in Berichten beenden:
    
      - Das Anzeigen von Problemen für die ausgewählte Instanz beenden.
    
      - Das Anzeigen von Problemen für alle Instanzen des Problems beenden.
    
    Zum Anzeigen der Probleme, die in Berichten nicht mehr angezeigt werden, öffnen Sie die Registerkarte **Ausgeblendete Elemente** der Ansicht **Andere Berichte**. Dort können Sie festlegen, dass Probleme wieder in Berichten angezeigt werden.

Nähere Informationen zum Lösen bestimmter Probleme finden Sie unter [Analysieren und Beheben von Problemen, die von Best Practices Analyzer erkannt wurden](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

