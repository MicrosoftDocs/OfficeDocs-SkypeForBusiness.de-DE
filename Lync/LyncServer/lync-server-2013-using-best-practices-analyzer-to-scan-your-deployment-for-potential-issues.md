---
title: Verwenden von Best Practices Analyzer zum Überprüfen der Bereitstellung auf mögliche Probleme
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c3c2c5b49ae59c93ac6f78a2ae354061d7bf0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Verwenden von Best Practices Analyzer zum Überprüfen Ihrer lync Server 2013-Bereitstellung auf mögliche Probleme

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Zum Ausführen einer Best Practices Analyzer-Überprüfung müssen Sie Folgendes angeben:

  - **Anmeldeinformationen**   zum Ausführen eines Scans müssen Sie sich bei einem Computer anmelden, auf dem Best Practices Analyzer installiert ist, indem Sie ein Konto verwenden, das Mitglied der lokalen Gruppe Administratoren ist. Außerdem müssen Sie sich mit einem Benutzerkonto anmelden, das über die erforderlichen Benutzerrechte und Berechtigungen verfügt, um die geeigneten Überprüfungen auszuführen, oder Sie müssen beim Ausführen von Best Practices Analyzer Anmeldeinformationen angeben, die über die erforderlichen Benutzerrechte und Berechtigungen verfügen. Ausführliche Informationen finden Sie unter [Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Umfang**   der Überprüfung um den Umfang der Überprüfung anzugeben, wählen Sie die Kategorien und Server aus, die Sie überprüfen möchten. Sie können alle Kategorien, eine oder mehrere Kategorien oder einen oder mehrere Server in einer bestimmten Kategorie in ihrer lync Server Umgebung auswählen.

  - **Typ der**   Überprüfung derzeit ist der Integritäts Prüfungs Scan der einzige verfügbare Scantyp (standardmäßig ausgewählt). Die Integritätsprüfung generiert einen Bericht mit Fehlern, Warnungen und weiteren Informationen für alle Server, die sich im angegebenen Bereich befinden.

  - **Netzwerkgeschwindigkeit**   Netzwerk Geschwindigkeitsoptionen umfassen schnelles LAN (100 Mbit/s oder mehr), LAN (10 Mbit/s), schnelles WAN (1,5 MBit/s) oder WAN (64 Kbit/s). Die geschätzte Dauer der Überprüfung basiert auf dieser Einstellung. Zudem wird diese Einstellung auch zum Festlegen des Timeouts verwendet. Während der Überprüfung wartet der Best Practices Analyzer eine angegebene Zeitdauer auf eine Serverantwort. Erfolgt innerhalb des angegebenen Timeout-Zeitraums keine Antwort, wird zum nächsten Server in der Überprüfung gewechselt. In langsameren Netzwerken ist dieser Timeout-Zeitraum länger, um längere Netzwerklatenzen zu berücksichtigen. Wir empfehlen die Auswahl der langsamsten Verbindung in Ihrer Topologie für diesen Parameter, damit das Tool nicht zu schnell einen Timeout ausgibt.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>So führen Sie eine Überprüfung Ihrer Lync Server 2013-Bereitstellung durch

1.  Melden Sie sich an einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied der lokalen Administratorengruppe ist und über weitere erforderliche Benutzerrechte und -berechtigungen verfügt.

2.  Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **Best Practices Analyzer**.

3.  Klicken Sie auf der **Willkommensseite** auf **Optionen für neue Überprüfung auswählen**.

4.  Überprüfen Sie auf der Seite **Mit Active Directory verbinden** den in **Active Directory-Server** angegebenen Namen, und führen Sie dann eine der folgenden Aktionen aus:
    
      - Zum Ausführen einer Überprüfung mit den Anmeldeinformationen, die Sie zur Anmeldung an Computer verwendet haben, klicken Sie auf **Mit Active Directory-Server verbinden**.
    
      - Zum Angeben verschiedener Anmeldeinformationen, die Sie für Active Directory Domain Services, Edgeserver oder Exchange Server verwenden möchten, klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**, aktivieren Sie alle Kontrollkästchen, für die separate Anmeldeinformationen erforderlich sind, geben Sie die Anmeldeinformationen für jedes aktivierte Kontrollkästchen an, und klicken Sie dann auf **Mit Active Directory-Server verbinden**.
    
    <div>
    

    > [!NOTE]
    > Vor dem Beginn der Überprüfung führt Best Practices Analyzer eine Netzwerk- und Berechtigungsprüfung durch, um sicherzustellen, dass die angegebenen Kontoanmeldeinformationen gültig sind und Best Practices Analyzer eine Verbindung mit Active Directory Domain Services herstellen kann. Wird das Tool auf einem Arbeitsgruppenserver ausgeführt, überprüft es auch, ob eine Verbindung mit Edgeservern im Umkreisnetzwerk möglich ist (falls diese in die Überprüfung eingeschlossen sind).

    
    </div>

5.  Wählen Sie auf der Seite **Neue Bewährte Methoden-Überprüfung starten** die Optionen, die die Überprüfung umfassen soll, geben Sie die Netzwerkgeschwindigkeit an, und klicken Sie dann auf **Überprüfung starten**.

6.  Klicken Sie auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen**.

7.  Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:
    
      - Wenn Sie Berichte in einer Liste anzeigen möchten, die nach Serverkomponenten angeordnet ist, klicken Sie auf **Berichte auflisten**, und klicken Sie dann entweder auf die Registerkarte **Alle Probleme** oder auf **Informationselemente**.
    
      - Wenn Sie Berichte als hierarchische Liste anzeigen möchten, die nach Ergebnistypen angeordnet ist, klicken Sie auf **Strukturberichte**, und klicken Sie dann entweder auf die Registerkarte **Detaillierte Ansicht** oder auf **Zusammenfassungsansicht**.
    
      - Wenn Sie sonstige Berichte anzeigen möchten, klicken Sie auf **Sonstige Berichte**.
    
    <div>
    

    > [!NOTE]
    > Ausführliche Informationen zu den Best Practices Analyzer-Berichten und den identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">anzeigen und arbeiten mit Berichten, die von Best Practices Analyzer erstellt wurden, in lync Server 2013</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analysieren und Beheben von Problemen, die von Best Practices Analyzer in lync Server 2013 identifiziert</A>wurden.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

