---
title: 'Lync Server 2013: Anzeigen von Berichten aus Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79732661152ba0929b62ae64f46b0cbfdb95217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Anzeigen von Berichten von Best Practices Analyzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn Sie Best Practices Analyzer zum Überprüfen Ihrer Umgebung verwenden, geben Sie einen Namen für die Überprüfung an. Nachdem Best Practices Analyzer eine Überprüfung abgeschlossen hat, speichert Sie die Überprüfungsergebnisse in Berichten und speichert Sie unter dem Namen der Überprüfung. Nach Abschluss der Überprüfung können Sie die für diesen Scan generierten Berichte anzeigen, indem Sie direkt auf der Seite **Scannen abgeschlossen** auf **Bericht anzeigen dieser bewährten Methoden prüfen** klicken. Sie können die Berichte auch zu einem späteren Zeitpunkt über diesen Scan oder vorherige Scans anzeigen. Sie können Berichte auf dem lokalen Computer anzeigen, auf dem die Überprüfung ausgeführt wurde, die Überprüfungsergebnisse von einem anderen Computer importieren oder die Scanergebnisse exportieren, um die Berichte auf einem anderen Computer anzuzeigen, auf dem Best Practices Analyzer installiert ist.

Die Scan Ergebnisse werden in den folgenden Berichtstypen angezeigt:

  - Listen Berichte

  - Strukturberichte

  - Andere Berichte

Diese Berichte umfassen Fehler, Warnungen und weitere Informationen. Ausführliche Informationen zu jedem dieser Arten von Berichten und Problemen finden Sie unter [Grundlegendes zu berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Gehen Sie wie folgt vor, um die zuvor von Best Practices Analyzer generierten Scanergebnisse anzuzeigen.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>So zeigen Sie Berichte aus einer vorherigen Überprüfung an

1.  Melden Sie sich bei einem Computer an, auf dem Best Practices Analyzer installiert ist, und verwenden Sie ein Konto, das Mitglied des lokalen Benutzerkontos ist.
    
    > [!NOTE]  
    > Sie können die Ergebnisse eines Scans mit einem Konto anzeigen, das Mitglied der lokalen Gruppe Administratoren ist, aber Sie können nur dann einen Scan ausführen, wenn Sie über die entsprechenden Benutzerrechte und Berechtigungen verfügen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</A>.

2.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.

3.  Klicken Sie auf der **Willkommens** Seite auf **die anzuzeigenden Scanergebnisse auswählen**.

4.  Führen Sie auf der Seite **Wählen Sie eine bewährte Vorgehensweise für die Anzeige aus** , eine der folgenden Aktionen aus:
    
      - Wenn Sie Berichte aus der Liste der lokal gespeicherten Scanergebnisse anzeigen möchten, klicken Sie auf den Namen des Scans, und klicken Sie dann auf **Bericht dieser Überprüfung anzeigen**.
        
        > [!NOTE]  
        > Der Best Practices Analyzer erstellt die Liste der lokalen Dateien aus dem &lt;Ordner&gt;\\System Drive Dokumente\\&lt;und&gt;Einstellungen Benutzer-Data\Microsoft\RtcBPA.
    
      - Wenn Sie Berichte zu den Ergebnissen eines Scans anzeigen möchten, die an einem anderen Speicherort gespeichert sind, klicken Sie auf **Scan importieren**, suchen Sie die Datei, die die Überprüfungsergebnisse enthält, und klicken Sie dann auf **Öffnen**.
        
        > [!NOTE]  
        > Wenn die Version von Best Practices Analyzer auf diesem Computer nicht mit der Version übereinstimmt, die zum Sammeln der Daten in der importierten Datei verwendet wurde, analysiert das Tool auf Ihrem Computer die Datei möglicherweise erneut, nachdem Sie importiert wurde.

5.  Führen Sie auf der Seite " **Best Practices-Bericht anzeigen** " eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Listen Berichte**, und klicken Sie dann entweder auf die Registerkarte **alle Probleme** oder auf die Registerkarte **Informationselemente** , um Berichte in einer nach Serverkomponente organisierten Liste anzuzeigen.
    
      - Klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **detaillierte Ansicht** oder auf die Registerkarte **Zusammenfassungsansicht** , um Berichte als hierarchische Liste anzuzeigen, die nach Arten von Ergebnissen sortiert ist.
    
      - Wenn Sie andere Berichte anzeigen möchten, klicken Sie auf **Weitere Berichte**.
    
    > [!NOTE]  
    > Details zu den Berichten zu Best Practices Analyzer und den von Ihnen identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden</A> , und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>werden.

</div>

</div>

</div>

</div>

</div>

