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
ms.openlocfilehash: 1ffa6108760955de643b7ffa4afe841464ae140f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535592"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Anzeigen von Berichten aus Best Practices Analyzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Wenn Sie Best Practices Analyzer zur Überprüfung Ihrer Umgebung verwenden, geben Sie einen Namen für die Überprüfung an. Nach Abschluss der Überprüfung speichert Best Practices Analyzer die Überprüfungsergebnisse in Berichten und speichert diese Berichte unter dem Namen der Überprüfung. Sobald die Überprüfung abgeschlossen ist, können Sie die erstellten Berichte anzeigen, indem Sie direkt auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen** klicken. Sie können die Berichte für diese oder frühere Überprüfungen auch zu einem späteren Zeitpunkt anzeigen. Sie können die Berichte auf dem lokalen Computer anzeigen, auf dem die Überprüfung erfolgt ist, die Überprüfungsergebnisse von einem anderen Computer importieren oder die Überprüfungsergebnisse exportieren, um sie auf einem Computer anzuzeigen, auf dem Best Practices Analyzer installiert ist.

Die Überprüfungsergebnisse werden in den folgenden Arten von Berichten dargestellt:

  - Listenberichte

  - Strukturberichte

  - Sonstige Berichte

Diese Berichte umfassen Fehler, Warnungen und andere Informationen. Ausführliche Informationen zu diesen Arten von Berichten und Problemen finden Sie unter [Understanding Reports by Best Practices Analyzer created in lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Verwenden Sie das folgende Verfahren, um die Überprüfungsergebnisse anzuzeigen, die zuvor mit Best Practices Analyzer erstellt wurden.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>So zeigen Sie Berichte aus einer früheren Überprüfung an

1.  Melden Sie sich auf einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied des Kontos für lokale Benutzer ist.
    
    > [!NOTE]  
    > Sie können zwar die Ergebnisse einer Überprüfung anzeigen, wenn Sie ein Konto verwenden, das Mitglied der lokalen Administratorengruppe ist; Sie können jedoch nur eine Überprüfung ausführen, wenn Sie über die erforderlichen Benutzerrechte und Berechtigungen verfügen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013</A>.

2.  Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.

3.  Klicken Sie im Willkommensbildschirm**** auf **Anzuzeigende Überprüfungsergebnisse auswählen**.

4.  Führen Sie auf der Seite **Bewährte Methoden-Überprüfung zum Anzeigen auswählen** einen der folgenden Schritte aus:
    
      - Wenn Sie Berichte aus der Liste der lokal gespeicherten Überprüfungsergebnisse anzeigen möchten, klicken Sie auf den Namen der Überprüfung, und klicken Sie dann auf **Bericht für diese Überprüfung anzeigen**.
        
        > [!NOTE]  
        > Der Best Practices Analyzer erstellt die Liste der lokalen Dateien aus dem &lt; Ordner &gt; \\ System Drive Dokumente und Einstellungen \\ &lt; Benutzer &gt; Data\Microsoft\RtcBPA.
    
      - Wenn Sie Berichte zu Ergebnissen einer Überprüfung anzeigen möchten, die sich an einem anderen Speicherort befinden, klicken Sie auf **Überprüfung importieren**, suchen Sie nach der Datei, in der die Überprüfungsergebnisse enthalten sind, und klicken Sie dann auf **Öffnen**.
        
        > [!NOTE]  
        > Wenn die Version von Best Practices Analyzer auf diesem Computer nicht mit der Version übereinstimmt, die verwendet wurde, um die Daten in der importierten Datei zu erfassen, wird die Datei von dem Tool auf Ihrem Computer möglicherweise nach dem Import erneut analysiert.

5.  Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:
    
      - Wenn Sie Berichte in einer Liste anzeigen möchten, die nach Serverkomponenten angeordnet ist, klicken Sie auf **Berichte auflisten**, und klicken Sie dann entweder auf die Registerkarte **Alle Probleme** oder auf **Informationselemente**.
    
      - Wenn Sie Berichte als hierarchische Liste anzeigen möchten, die nach Ergebnistypen angeordnet ist, klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **Detaillierte Ansicht** oder auf **Zusammenfassungsansicht**.
    
      - Wenn Sie sonstige Berichte anzeigen möchten, klicken Sie auf **Sonstige Berichte**.
    
    > [!NOTE]  
    > Ausführliche Informationen zu den Best Practices Analyzer-Berichten und den identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer erstellt wurden, in lync Server 2013</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>wurden.

</div>

</div>

</div>

</div>

</div>

