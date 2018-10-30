---
title: 'Lync Server 2013: Ausführen eines Failbacks für den Server für beständigen Chat'
TOCTitle: Ausführen eines Failbacks für den Server für beständigen Chat
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204970(v=OCS.15)
ms:contentKeyID: 49294259
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failbacks für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

In dieser Anleitung wird die Vorgehensweise beschrieben, die zur Wiederherstellung nach einem Ausfall des Server für beständigen Chat sowie zur Wiederaufnahme des Betriebs im primären Rechenzentrum erforderlich ist.

Während eines Ausfalls des Server für beständigen Chat fällt das primäre Rechenzentrum komplett aus, und die primäre und die Spiegeldatenbank sind nicht verfügbar. Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.

Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen. Dabei wird davon ausgegangen, dass das primäre Rechenzentrum den Totalausfall überwunden hat und die Datenbanken "mgc" und "mgccomp" mit dem Topologie-Generator wiederhergestellt und erneut installiert wurden.

Des Weiteren wird vorausgesetzt, dass während der Dauer des Ausfalls keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass die einzigen bereitgestellten Server der Sicherungsserver und sein Spiegelserver sind (wie in [Ausführen eines Failovers für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md) festgelegt).

Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat, vorlag.

## So führen Sie das Failback für den Server für beständigen Chat durch

1.  Löschen Sie alle für den Server für beständigen Chat in der Liste "Aktiver Server" aufgeführten Server mithilfe des `Set-CsPersistentChatActiveServer`-Cmdlets in der Lync Server-Verwaltungsshell. Dadurch wird dafür gesorgt, dass während des Failbacks keiner der Server für beständigen Chat mehr Verbindungen zu den Datenbanken "mgc" und "mgccomp" herstellt.
    

    > [!IMPORTANT]
    > Der SQL Server-Agent auf dem sekundären Server für beständigen Chat-Back-End-Server sollte unter einem privilegierten Konto ausgeführt werden. Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen: 
    > <UL>
    > <LI>
    > <P>Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen</P>
    > <LI>
    > <P>Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen</P></LI></UL>



2.  Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung zu der mgc-Sicherungsinstanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** , und klicken Sie dann auf **Spiegeln** .
    
    3.  Klicken Sie auf **Spiegelung entfernen** .
    
    4.  Klicken Sie auf **OK** .
    
    5.  Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.

3.  Sichern Sie die mgc-Datenbank, damit Sie in der neuen primären Datenbank wiederhergestellt werden kann:
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung zu der mgc-Sicherungsinstanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** , und klicken Sie dann auf **Sichern** . Das Dialogfeld **Datenbank sichern** wird angezeigt.
    
    3.  Wählen Sie in **Sicherungstyp** die Option **Vollständig** aus.
    
    4.  Klicken Sie bei **Sicherungskomponente** auf **Datenbank** .
    
    5.  Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie eine anderen Namen ein.
    
    6.  *\<Optional\>* Geben Sie in **Beschreibung** eine Beschreibung für den Sicherungssatz ein.
    
    7.  Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.
    
    8.  Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.
    
    9.  Klicken Sie auf **OK** , um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.

4.  Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.
    
    1.  Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung zu der primären mgc-Instanz her.
    
    2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** , zeigen Sie auf **Wiederherstellen** , und klicken Sie dann auf **Datenbank** . Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.
    
    3.  Wählen Sie **Von Medium** aus.
    
    4.  Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen** , wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK** .
    
    5.  Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.
    
    6.  Klicken Sie auf **Optionen** im Bereich **Seite auswählen** .
    
    7.  Aktivieren Sie in **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben** .
    
    8.  Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen** .
    
    9.  Klicken Sie auf **OK** , um mit dem Wiederherstellungsvorgang zu beginnen.

5.  Konfigurieren Sie SQL Server-Protokollversand für die primäre Datenbank. Folgen Sie dazu der Anleitung aus [Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md), um Protokollversand für die primäre mgc-Datenbank einzurichten.

6.  Legen Sie die aktiven Server für beständigen Chat fest. Verwenden Sie dazu in der Lync Server-Verwaltungsshell das **Set-CsPersistentChatActiveServer**-Cmdlet, um die Liste der aktiven Server festzulegen.
    

    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum, das über eine Verbindung mit einer geringen Latenz und hohen Bandbreite zu der Datenbank verfügt, befinden.



Um den Pool im normalen Zustand wiederherzustellen, führen Sie den folgenden Windows PowerShell-Befehl aus:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Weitere Informationen finden Sie im Hilfethema zum [Set-CsPersistentChatState](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPersistentChatState)-Cmdlet.

