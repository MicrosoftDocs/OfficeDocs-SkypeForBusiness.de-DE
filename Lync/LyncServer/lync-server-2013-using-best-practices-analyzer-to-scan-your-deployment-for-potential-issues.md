---
title: Verwenden von Best Practices Analyzer zum Überprüfen Ihrer Bereitstellung auf potenzielle Probleme
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Verwenden von Best Practices Analyzer zum Durchsuchen Ihrer lync Server 2013-Bereitstellung nach potenziellen Problemen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Wenn Sie einen Best Practices Analyzer-Scan ausführen möchten, müssen Sie Folgendes angeben:

  - **Anmeldeinformationen**   Wenn Sie einen Scan durchführen möchten, müssen Sie sich bei einem Computer anmelden, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist. Darüber hinaus müssen Sie sich mit einem Benutzerkonto anmelden, das über die Benutzerrechte und Berechtigungen zum Ausführen der entsprechenden Scans verfügt, oder Sie müssen Anmeldeinformationen angeben, die über die entsprechenden Benutzerrechte und Berechtigungen verfügen, wenn Sie Best Practices Analyzer ausführen. Ausführliche Informationen finden Sie unter [Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Scanbereich um**   den Scanbereich anzugeben, wählen Sie die Kategorien und Server aus, die Sie überprüfen möchten. Sie können alle Kategorien, eine oder mehrere Kategorien oder einen oder mehrere Server innerhalb einer bestimmten Kategorie in ihrer lync Server-Umgebung auswählen.

  - **Art des Scans**   zurzeit ist der Integritäts Prüfungs Scan der einzige verfügbare Scantyp (standardmäßig aktiviert). Mit dem Integritäts Prüfungs Scan wird ein Bericht generiert, der Fehler, Warnungen und andere Informationen für alle im Bereich angegebenen Server enthält.

  - ****   Netzwerkgeschwindigkeit-Netzwerk Geschwindigkeitsoptionen umfassen schnelles LAN (100 Mbit/s oder mehr), LAN (10 Mbit/s), fast WAN (1,5 MBit/s) oder WAN (64 Kbit/s). Die geschätzte Zeit zum Durchführen des Scans basiert auf dieser Einstellung. Diese Einstellung wird auch zum Festlegen des Timeoutzeitraums verwendet. Während des Scans wartet der Best Practices Analyzer auf eine Antwort von einem Server für einen bestimmten Zeitraum. Wenn Sie innerhalb des angegebenen Timeoutzeitraums keine Antwort erhält, wechselt Sie zum nächsten Server in der Überprüfung. In langsameren Netzwerken ist dieser angegebene Timeoutzeitraum länger, um längere Netzwerk Latenzen zu berücksichtigen. Wir empfehlen, dass Sie den langsamsten Link in Ihrer Topologie für diesen Parameter auswählen, damit das Tool nicht zu schnell abläuft.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>So überprüfen Sie Ihre lync Server 2013-Bereitstellung

1.  Melden Sie sich bei einem Computer an, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist, und über andere erforderliche Benutzerrechte und Berechtigungen verfügt.

2.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.

3.  Klicken Sie auf der **Willkommens** Seite auf **Optionen für einen neuen Scan auswählen**.

4.  Überprüfen Sie auf der Seite **mit Active Directory verbinden** den in **Active Directory Server**angegebenen Namen, und führen Sie dann eine der folgenden Aktionen aus:
    
      - Wenn Sie einen Scan mit den Anmeldeinformationen ausführen möchten, die Sie für die Anmeldung am Computer verwendet haben, klicken Sie auf mit **dem Active Directory-Server verbinden**.
    
      - Wenn Sie andere Anmeldeinformationen angeben möchten, die Sie für Active Directory-Domänendienste, Edgeserver oder Exchange Server verwenden möchten, klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**, aktivieren Sie die einzelnen Kontrollkästchen, für die getrennte Anmeldeinformationen erforderlich sind, geben Sie die Anmeldeinformationen an. für jedes ausgewählte Kontrollkästchen aus, und klicken Sie dann auf **mit dem Active Directory-Server verbinden**.
    
    <div>
    

    > [!NOTE]
    > Vor Beginn des Scans führt Best Practices Analyzer eine Netzwerk-und Berechtigungsüberprüfung durch, um sicherzustellen, dass die angegebenen Kontoanmeldeinformationen gültig sind und dass Best Practices Analyzer eine Verbindung mit Active Directory-Domänendiensten herstellen kann. Wenn das Tool auf einem Arbeitsgruppenserver ausgeführt wird, überprüft das Tool auch, ob es eine Verbindung mit Edgeserver im Umkreisnetzwerk herstellen kann (das heißt, wenn Sie in der Überprüfung enthalten sind).

    
    </div>

5.  Wählen Sie auf der Seite **neue Best Practices-Überprüfung starten** die Optionen aus, die Sie in die Überprüfung einbeziehen möchten, geben Sie die Netzwerkgeschwindigkeit an, und klicken Sie dann auf über **Prüfung starten**.

6.  Klicken Sie auf der Seite **Scan abgeschlossen** auf **Bericht anzeigen dieser bewährten Methoden Überprüfung**.

7.  Führen Sie auf der Seite " **Best Practices-Bericht anzeigen** " eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Listen Berichte**, und klicken Sie dann entweder auf die Registerkarte **alle Probleme** oder auf die Registerkarte **Informationselemente** , um Berichte in einer nach Serverkomponente organisierten Liste anzuzeigen.
    
      - Klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **detaillierte Ansicht** oder auf die Registerkarte **Zusammenfassungsansicht** , um Berichte als hierarchische Liste anzuzeigen, die nach Arten von Ergebnissen sortiert ist.
    
      - Wenn Sie andere Berichte anzeigen möchten, klicken Sie auf **Weitere Berichte**.
    
    <div>
    

    > [!NOTE]
    > Details zu den Berichten zu Best Practices Analyzer und den von Ihnen identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer in lync Server 2013 erstellt wurden</A> , und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer identifiziert werden. in lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

