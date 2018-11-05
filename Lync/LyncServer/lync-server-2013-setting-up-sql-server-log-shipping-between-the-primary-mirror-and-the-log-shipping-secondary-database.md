---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands'
TOCTitle: Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204887(v=OCS.15)
ms:contentKeyID: 49293962
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Führen Sie die folgenden Schritte aus, um den Protokollversand beim einem Failover der primären Beständiger Chat-Datenbank zur gespiegelten Datenbank fortzusetzen.

1.  Führen Sie ein manuelles Failover der primären Beständiger Chat-Datenbank zur gespiegelten Datenbank durch, indem Sie das Cmdlet Lync Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** verwenden. Nähere Informationen finden Sie unter "Verwenden von Lync Server-Verwaltungsshell-Cmdlets" in [Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der primären Server für beständigen Chat-Spiegelinstanz her.

3.  Vergewissern Sie sich, dass der SQL Server-Agent ausgeführt wird.

4.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften** .

5.  Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand** .

6.  Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren** .

7.  Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen** .

8.  Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.

9.  Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    

    > [!IMPORTANT]
    > Wenn das SQL Server-Dienstkonto unter dem lokalen Systemkonto auf dem primären Server ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad für diesen Ordner angeben.



10. Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in** .

11. Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Um den Zeitplan für Ihre Installation anzupassen, klicken Sie auf **Zeitplan** , und passen Sie den Zeitplan für den SQL Server-Agent nach Bedarf an.
    

    > [!IMPORTANT]
    > Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben.



12. Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus, und klicken Sie auf **OK** .

13. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen** .

14. Klicken Sie auf **Verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.

15. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.

16. Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus. aus.

17. Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK** . Dieser Ordner befindet sich i. d. R. auf dem sekundären Server.

18. Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** , und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.

19. Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK** , um mit der Konfiguration zu beginnen.

20. Wählen Sie die erste Hälfte der Abfrage (siehe Schritt 18) bis zur Zeile -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\* aus, und führen Sie diese aus.
    

    > [!IMPORTANT]
    > Das Skript muss manuell ausgeführt werden, weil SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Konfiguration für den Protokollversand nicht unterstützt.



21. Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert.

22. Führen Sie ein manuelles Failback der primären Beständiger Chat-Datenbank zum primären Server durch, indem Sie das Cmdlet Lync Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** verwenden. Nähere Informationen finden Sie unter "Verwenden von Lync Server-Verwaltungsshell-Cmdlets" in [Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

## Siehe auch

#### Konzepte

[Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

