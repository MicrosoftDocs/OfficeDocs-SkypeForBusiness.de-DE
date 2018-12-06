---
title: Durchsuchen einer Bereitstellung auf potenzielle Probleme mithilfe von Best Practices Analyzer
TOCTitle: Durchsuchen einer Bereitstellung auf potenzielle Probleme mithilfe von Best Practices Analyzer
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg591343(v=OCS.15)
ms:contentKeyID: 49293116
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Durchsuchen einer Bereitstellung auf potenzielle Probleme mithilfe von Best Practices Analyzer

 

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Zum Ausführen einer Best Practices Analyzer-Überprüfung müssen Sie Folgendes angeben:

  - **Anmeldeinformationen**   Zum Ausführen einer Überprüfung, müssen Sie sich mit einem Konto, das Mitglied der lokalen Gruppe "Administratoren" ist, an einem Computer anmelden, auf dem Best Practices Analyzer installiert ist. Außerdem müssen Sie sich mit einem Benutzerkonto anmelden, das über die erforderlichen Benutzerrechte und Berechtigungen verfügt, um die geeigneten Überprüfungen auszuführen, oder Sie müssen beim Ausführen von Best Practices Analyzer Anmeldeinformationen angeben, die über die erforderlichen Benutzerrechte und Berechtigungen verfügen. Ausführliche Informationen finden Sie unter [Voraussetzungen hinsichtlich Gruppenmitgliedschaften und Benutzerberechtigungen für Best Practices Analyzer](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Überprüfungsbereich**   Zum Festlegen des zu Überprüfungsbereichs wählen Sie die zu überprüfenden Kategorien und Server aus. Sie können alle, eine oder mehrere Kategorien sowie einen oder mehrere Server in einer bestimmten Kategorie in Ihrer Lync Server-Umgebung auswählen.

  - **Überprüfungsart**   Derzeit ist als einzige Überprüfungsart die Integritätsprüfung verfügbar (standardmäßig ausgewählt). Die Integritätsprüfung generiert einen Bericht mit Fehlern, Warnungen und weiteren Informationen für alle Server, die sich im angegebenen Bereich befinden.

  - **Netzwerkgeschwindigkeit**   Optionen für die Netzwerkgeschwindigkeit umfassen schnelles LAN (100 Mbit/s oder mehr), LAN (10 MBit/s), schnelles WAN (1,5 Mbit/s) oder WAN (64 Kbit/s). Die geschätzte Dauer der Überprüfung basiert auf dieser Einstellung. Zudem wird diese Einstellung auch zum Festlegen des Timeouts verwendet. Während der Überprüfung wartet der Best Practices Analyzer eine angegebene Zeitdauer auf eine Serverantwort. Erfolgt innerhalb des angegebenen Timeout-Zeitraums keine Antwort, wird zum nächsten Server in der Überprüfung gewechselt. In langsameren Netzwerken ist dieser Timeout-Zeitraum länger, um längere Netzwerklatenzen zu berücksichtigen. Wir empfehlen die Auswahl der langsamsten Verbindung in Ihrer Topologie für diesen Parameter, damit das Tool nicht zu schnell einen Timeout ausgibt.

## So führen Sie eine Überprüfung Ihrer Lync Server 2013-Bereitstellung durch

1.  Melden Sie sich an einem Computer an, auf dem Best Practices Analyzer installiert ist. Verwenden Sie dabei ein Konto, das Mitglied der lokalen Administratorengruppe ist und über weitere erforderliche Benutzerrechte und -berechtigungen verfügt.

2.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft Lync Server 2013** und dann auf **Best Practices Analyzer**.

3.  Klicken Sie auf der **Willkommensseite** auf **Optionen für neue Überprüfung auswählen**.

4.  Überprüfen Sie auf der Seite **Mit Active Directory verbinden** den in **Active Directory-Server** angegebenen Namen, und führen Sie dann eine der folgenden Aktionen aus:
    
      - Zum Ausführen einer Überprüfung mit den Anmeldeinformationen, die Sie zur Anmeldung an Computer verwendet haben, klicken Sie auf **Mit Active Directory-Server verbinden**.
    
      - Zum Angeben verschiedener Anmeldeinformationen, die Sie für Active Directory Domain Services, Edgeserver oder Exchange Server verwenden möchten, klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**, aktivieren Sie alle Kontrollkästchen, für die separate Anmeldeinformationen erforderlich sind, geben Sie die Anmeldeinformationen für jedes aktivierte Kontrollkästchen an, und klicken Sie dann auf **Mit Active Directory-Server verbinden**.
    

    > [!NOTE]
    > Vor dem Beginn der Überprüfung führt Best Practices Analyzer eine Netzwerk- und Berechtigungsprüfung durch, um sicherzustellen, dass die angegebenen Kontoanmeldeinformationen gültig sind und Best Practices Analyzer eine Verbindung mit Active Directory Domain Services herstellen kann. Wird das Tool auf einem Arbeitsgruppenserver ausgeführt, überprüft es auch, ob eine Verbindung mit Edgeservern im Umkreisnetzwerk möglich ist (falls diese in die Überprüfung eingeschlossen sind).



5.  Wählen Sie auf der Seite **Neue Bewährte Methoden-Überprüfung starten** die Optionen, die die Überprüfung umfassen soll, geben Sie die Netzwerkgeschwindigkeit an, und klicken Sie dann auf **Überprüfung starten**.

6.  Klicken Sie auf der Seite **Überprüfung abgeschlossen** auf **Bericht für diese Bewährte Methoden-Überprüfung anzeigen**.

7.  Führen Sie auf der Seite **Bewährte Methoden-Bericht anzeigen** einen der folgenden Schritte aus:
    
      - Zum Anzeigen von Berichten in einer nach Serverkomponente geordneten Liste klicken Sie auf **Listenberichte** und anschließend entweder auf die Registerkarte **Alle Probleme** oder **Informationselemente**.
    
      - Zum Anzeigen von Berichten als nach Ergebnistypen geordnete hierarchische Liste klicken Sie auf **Strukturberichte** und anschließend entweder auf die Registerkarte **Detaillierte Ansicht** oder **Zusammenfassungsansicht**.
    
      - Klicken Sie zum Anzeigen anderer Berichte auf **Andere Berichte**.
    

    > [!NOTE]
    > Nähere Informationen zu Best Practices Analyzer-Berichten und den darin identifizierten Problemen finden Sie unter <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Anzeigen und Verwenden von Berichten, die von Best Practices Analyzer erstellt wurden</A> und <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analysieren und Beheben von Problemen, die von Best Practices Analyzer erkannt wurden</A>.


