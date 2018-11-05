---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat'
TOCTitle: Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204653(v=OCS.15)
ms:contentKeyID: 49293095
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-12_

Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Datenbankinstanz für den Protokollversand des Server für beständigen Chat her. Stellen Sie dabei sicher, dass der SQL Server-Agent ausgeführt wird.

Wenn Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Instanz der primären Datenbank für Beständiger Chat hergestellt haben, führen Sie die folgenden Schritte aus:

1.  Vergewissern Sie sich, dass der SQL Server-Agent ausgeführt wird.

2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.

3.  Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.

4.  Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren** .

5.  Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen** .

6.  Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.

7.  Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (z. B. "c:/backup")** ein. (Befindet sich der Sicherungsordner nicht auf dem primären Server, können Sie dieses Feld leer lassen.)
    

    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto unter dem lokalen Systemkonto auf dem primären Server ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad für diesen Ordner angeben.



8.  Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in** .

9.  Sehen Sie sich den im Feld **Zeitplan** unter **Sicherungsauftrag** aufgeführten Sicherungszeitplan an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan** , und passen Sie den SQL Server-Agent-Zeitplan entsprechend an.

10. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus, und klicken Sie dann auf **OK** .

11. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen** .

12. Klicken Sie auf **Verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.

13. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.

14. Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist).** .

15. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.

16. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan** , und passen Sie den SQL Server-Agent-Zeitplan entsprechend an. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

17. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.

18. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.

19. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.

20. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan** , passen Sie den SQL Server-Agent-Zeitplan entsprechend an, und klicken Sie auf **OK** . Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

21. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK** , um den Konfigurationsprozess zu starten.

