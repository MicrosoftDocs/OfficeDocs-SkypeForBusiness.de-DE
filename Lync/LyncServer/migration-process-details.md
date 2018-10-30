---
title: Migrationsprozess – Details
TOCTitle: Migrationsprozess – Details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205264(v=OCS.15)
ms:contentKeyID: 49295405
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrationsprozess – Details

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Verwenden Sie die folgenden Voraussetzungen und ausführlichen Schritte zum Migrieren von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2  Gruppenchat zu Lync Server 2013, Server für beständigen Chat.

## Voraussetzungen für die Migration

Die folgenden Voraussetzungen müssen erfüllt sein, um Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2  Gruppenchat zu Lync Server 2013,  Server für beständigen Chat zu migrieren.

1.  Stellen Sie mindestens einen Lync Server 2013-Pool bereit. Wenn mehrere Lync Server 2013-Pools vorhanden sind, bestimmen Sie den Lync Server 2013-Pool, der als Home-Pool für den neuen Serverpool für beständigen Chat von Lync Server 2013 verwendet werden soll.

2.  Installieren Sie den Serverpool für beständigen Chat von Lync Server 2013. Er ist zunächst leer (keine Kategorien, Chatrooms oder Add-Ins). Vor der Migration Ihrer Kategorien, Chatrooms oder Add-Ins der Vorversion können Sie Chatrooms, Kategorien oder Add-Ins in Ihrer Bereitstellung von Lync Server 2013, Server für beständigen Chat erstellen.
    

    > [!IMPORTANT]
    > Beachten Sie, dass diese neue erstellten Elemente einen Konflikt mit Vorversionselementen, die Sie migrieren, verursachen können. Vermeiden Sie Namenskonflikte. Andernfalls werden die Namen überschrieben, wenn die Vorversionsdaten migriert werden.



## Vorbereiten der Quelldaten für die Migration

Führen Sie die folgenden Schritte aus, um Ihre Quelldaten ordnungsgemäß für die Migration vorzubereiten.

1.  Erstellen Sie eine Sicherungskopie der Quelldatenbanken für Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2  Gruppenchat. Ausführliche Informationen zum Erstellen von Sicherungskopien für SQL Server finden Sie im Abschnitt "Übersicht über Sicherungen (SQL Server)" unter <http://go.microsoft.com/fwlink/p/?linkid=254851>.
    

    > [!IMPORTANT]
    > Für Active Directory-Domänendienste gilt dasselbe. Die Migration in einen Pool in einer anderen Bereitstellung (insbesondere in einer anderen Active Directory-Gesamtstruktur) ist nicht möglich.



2.  Prüfen Sie Ihre Chatrooms und Ihre Kategoriekonfiguration für Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2  Gruppenchat. Alle Änderungen an Kategorien, Chatrooms oder Add-Ins in Ihrer bestehenden Vorversionsbereitstellung werden mit dem Gruppenchat-Verwaltungstool ausgeführt.
    

    > [!TIP]
    > Alle Änderungen an Kategorien, Chatrooms oder Add-Ins in Ihrer Bereitstellung von Lync Server 2013, Server für beständigen Chat werden mit der Lync Server-Systemsteuerung oder mit Windows PowerShell-Cmdlets ausgeführt.

    
    Führen Sie die folgenden Schritte aus, um Ihr Vorversionssystem für die Migration vorzubereiten.
    
    1.  Server für beständigen Chat unterstützt eine einzige Kategorieebene und keine geschachtelte Hierarchie von Kategorien. Nach der Migration werden den Unterkategorien die vollständigen Namen der übergeordneten Kategorie vorangestellt. Sie sollten eventuell Ihre vorhandene Kategoriestruktur vereinfachen, damit die resultierende Struktur Ihre Anforderungen erfüllt.
    
    2.  Überprüfen Sie die **Verantwortlichen** in der Stammkategorie. Falls auf dieser Ebene Verantwortliche vorhanden sind, werden diese Benutzer nach der Migration als **Verantwortliche für alle Chatrooms** hinzugefügt. Falls dies für Ihre Organisation nicht erforderlich ist, müssen Sie diese Verantwortlichen aus der Stammkategorie entfernen.
    
    3.  Überprüfen Sie die Länge der Chatroomnamen. Wenn nach der Migration aufgrund der vereinfachten Kategoriestrukturen Chatrooms in einer untergeordneten Kategorie vorhanden sind, werden ihnen die vollständigen Namen der übergeordneten Kategorie vorangestellt. Namen dürfen aus maximal 256 Zeichen bestehen, einschließlich der Namen für übergeordnete Kategorien. Sie müssen die Länge der Chatroomnamen überprüfen und eventuell deren Länge reduzieren, falls sie zu lang sind.
    
    4.  Wenn in Lync Server 2013 die Einstellungen der Kategorie **Einladung** auf Wahr festgelegt werden, können Sie Wahr oder Falsch für Einladungen zu Chatrooms in dieser Kategorie auswählen. Wenn allerdings die Einstellungen der Kategorie **Einladung** auf False festgelegt werden, sind für Chatrooms in dieser Kategorie Einladungen deaktiviert. Vor der Migration müssen Sie die Einladungseinstellungen in der Vorversion von Lync Server  Gruppenchatserver zurücksetzen, falls Chatrooms in einer bestimmten Kategorie vorhanden sein sollen. Andernfalls zeigt Lync Server 2013 während der Migration Warnungen an und legt für Chatrooms den Standardwert Falsch fest.
    
    5.  Wenn Sie Dateien in Chatrooms verwendet haben, müssen Sie die Dateien nach der Migration per XCOPY manuell in den neuen Dateispeicher von Beständiger Chat kopieren. Dieser Schritt wird nicht von den Tools ausgeführt.
    
    6.  Falls Partnerbenutzer und Chatrooms mit Partnerbenutzern vorhanden waren, sollten Sie beachten, dass der Partnerverbund vom Server für beständigen Chat nicht unterstützt wird. Chatrooms mit Partnerbenutzern werden migriert. Die Benutzer selbst können jedoch nicht auf die Inhalte zugreifen, da der Partnerverbundzugriff nicht unterstützt wird.
    
    7.  Identifizieren Sie die Chatrooms, die Sie nicht migrieren möchten, und kennzeichnen Sie sie als deaktiviert.
    
    8.  Legen Sie das Datum fest, bis zu dem Sie die Chatroominhalte migrieren möchten. Beispielsweise könnten Sie Nachrichten vor dem 1. Januar 2010 nicht migrieren, da diese Nachrichten veraltet oder für die Migration nicht relevant sind.

## Ausführen der Migration

Führen Sie die folgenden Schritte aus, um den Gruppenchatserver der Vorversion zu migrieren.

1.  Fahren Sie die Dienste Lync Server 2010-Gruppenchat, Office Communications Server 2007 R2  Gruppenchat oder Lync Server 2013, Server für beständigen Chat herunter. Alle Dienste müssen beendet werden, weshalb Sie diesen Schritt zu einem Zeitpunkt mit geringer Auslastung ausführen sollten. Sie müssen wie bereits beschrieben eine Sicherungskopie der vorhandenen Gruppenchatdatenbank erstellen.

2.  Führen Sie das Windows PowerShell-Cmdlet **Export-CsPersistentChatData** mit der rollenbasierten Zugriffssteuerungsrolle eines Administrators von Beständiger Chat aus ( CsPersistentChatAdministrator ). Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Konfiguration des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Prüfen Sie die exportieren Inhalte.

3.  Fahren Sie vor dem Importieren die Dienste Lync Server 2013, Server für beständigen Chat herunter. Alle Dienste müssen beendet werden, weshalb Sie diesen Schritt zu einem Zeitpunkt mit geringer Auslastung ausführen sollten.

4.  Erstellen Sie eine Sicherungskopie der Datenbank für Beständiger Chat, falls Sie vor der Migration Kategorien, Chatrooms oder Add-Ins in Ihrer Lync Server 2013-Bereitstellung erstellt haben. Mit dem Export-/Importvorgang werden die Vorversionsdaten in der Lync Server 2013-Bereitstellung zusammengeführt, aber Sie sollten eine Sicherungskopie der Datenbank für den Fall erstellen, dass Inhalte versehentlich überschrieben werden (z. B. falls weiterhin Namenskonflikte bestehen).

5.  Führen Sie das Windows PowerShell-Cmdlet **Import-CsPersistentChatData** (Importtool) mit dem Befehl **WhatIf** aus, um den Back-End-Server des Serverpool für beständigen Chat mit migrierten Daten aufzufüllen. Dabei werden einige Konvertierungen aufgrund des vereinfachten Administrationsmodells ausgeführt. Korrigieren Sie etwaige angezeigte Fehler oder Warnungen.

6.  Führen Sie das Server für beständigen ChatWindows PowerShell-Cmdlet **Import-CsPersistentChatData** mit der rollenbasierten Zugriffssteuerungsrolle eines Administrators von Beständiger Chat aus ( CsPersistentChatAdministrator ). Ausführliche Informationen zu den Export/Import-Cmdlets finden Sie unter [Problembehandlung bei der Konfiguration des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Alle hochgeladenen Dateien (gesamter Ordner) müssen Sie per XCOPY in den neuen Dateispeicher von Lync Server 2013, Beständiger Chat kopieren.
    

    > [!IMPORTANT]
    > Lync 2013 (Client) unterstützt das Hochladen oder Anzeigen von Dateien in Chatrooms nicht. Sie können weiterhin den Vorversionsclient zum Veröffentlichen und Anzeigen von Dateien im Chatroom verwenden.



8.  Portieren Sie den Abfrageserver-URI von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2  Gruppenchat in das Kontaktobjekt von Lync Server 2013, Server für beständigen Chat. Die folgenden Schritte sind erforderlich, wenn Ihre Lync 2010-Gruppenchat- oder Office Communicator 2007 R2  Gruppenchat-Clients nach der Migration ohne clientseitige Konfigurationsänderungen eine Verbindung mit dem neuesten Lync 2013, Beständiger Chat (Client) herstellen müssen:
    
      - Löschen Sie das Abfrageserver-Benutzerkonto ocschat@ *\<Domänenname\>* .com . Mit diesem Benutzerkonto wurde auf den Suchdienst in Lync Server 2010-Gruppenchat verwiesen. Sie können den Pool deinstallieren und vertrauenswürdige Einträge später entfernen.
    
      - Erstellen Sie einen Vorversionsendpunkt (Kontaktobjekt von Server für beständigen Chat), indem Sie das Windows PowerShell-Cmdlet **New-CsPersistentChatEndpoint** mit demselben SIP-URI ausführen, sodass der Vorversionsclient effizient arbeitet, wenn der Dienst neu gestartet wird.
    
    Der obligatorische Migrationsprozess ist damit abgeschlossen. Lync 2010-Gruppenchat (Clients) oder Office Communicator 2007 R2Gruppenchat (Clients) können nun auf nachvollziehbare Weise eine Verbindung mit dem neuen Serverpool für beständigen Chat herstellen.
    
    Führen Sie die folgenden zusätzlichen Schritte für die Außerbetriebnahme für Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2Gruppenchat aus.

9.  Starten Sie die Dienste für den Server für beständigen Chat, indem Sie alle Computer im neuen Serverpool für beständigen Chat einschalten.

10. Überprüfen Sie mit der Lync Server-Systemsteuerung und mit Windows PowerShell-Cmdlets, ob die Daten erfolgreich migriert wurden.

11. Deinstallieren Sie Lync 2010-Gruppenchat oder Office Communicator 2007 R2Gruppenchat auf den Computern im Gruppenchatserver-Pool.

12. Löschen Sie die vertrauenswürdige Anwendung und den Pool mit vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell-Cmdlets. Dadurch werden diese Elemente im zentraler Verwaltungsspeicher und die zugehörigen vertrauenswürdigen Diensteinträge (Trusted Service Entries, TSEs) in Active Directory gelöscht. Alternativ kann dieser Schritt auch mit dem Topologie-Generator ausgeführt werden (die vertrauenswürdigen Anwendungen/Pools haben dort auch einen dedizierten Knoten).

13. Nun können Sie mit dem Aktivieren der Funktionalität von Server für beständigen Chat über die neuen Clients beginnen. Ausführliche Informationen, wie Sie Server für beständigen Chat aktivieren, finden Sie unter [Bereitstellen des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    

    > [!IMPORTANT]
    > Lync Server 2013 unterstützt mehrere Serverpools für beständigen Chat. Wir unterstützen jedoch die Migration eines Lync&nbsp;2010-Gruppenchat- oder Office Communications Server 2007 R2&nbsp; Gruppenchatpools zu einem einzelnen Serverpool für beständigen Chat von Lync Server 2013. Sie können zusätzliche neue Serverpools für beständigen Chat in Ihrer Bereitstellung hinzufügen, um Vorschriften einzuhalten (z.&nbsp;B., dass die Daten innerhalb einer bestimmten Region verbleiben müssen).


