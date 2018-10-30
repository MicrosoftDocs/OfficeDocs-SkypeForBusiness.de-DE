---
title: 'Lync Server 2013: Ausführen eines Failovers für den Server für beständigen Chat'
TOCTitle: Ausführen eines Failovers für den Server für beständigen Chat
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204772(v=OCS.15)
ms:contentKeyID: 49293530
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failovers für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Das Failover für den Server für beständigen Chat ist im Wesentlichen als manueller Prozess konzipiert.

Das Failoververfahren basiert auf der Annahme, dass das sekundäre Datencenter ordnungsgemäß ausgeführt wird, aber die Dienste für den Server für beständigen Chat, in denen sich die Beständiger Chat-Primärdatenbank befindet, überhaupt nicht verfügbar sind, einschließlich:

  - Die Server für beständigen Chat-Primärdatenbank und die Server für beständigen Chat-Spiegeldatenbank sind ausgefallen.

  - Der Lync Server- Front-End-Server ist ausgefallen.

Das Verfahren basiert auf zwei grundlegenden Schritten:

  - Wiederherstellen der Beständiger Chat-Primärdatenbank (mgc)

  - Einrichten der Spiegelung für die neue Primärdatenbank

Für die Beständiger Chat-Konformitätsdatenbank (mgccomp) findet kein Failover statt. Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet. Sie als Beständiger Chat-Administrator sind dafür verantwortlich, die Adapterausgabe korrekt zu verwalten, um einen Datenverlust zu vermeiden.

## So führen Sie ein Failover für Server für beständigen Chat durch

1.  Entfernen Sie den Protokollversand aus der Server für beständigen Chat-Sicherungsdatenbank für den Protokollversand.
    
    1.  Stellen Sie mit SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die mgc-Sicherungsdatenbank für den Server für beständigen Chat befindet.
    
    2.  Öffnen Sie ein Abfragefenster zur Masterdatenbank.
    
    3.  Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.

3.  Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an. Detaillierte Informationen finden Sie unter "Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL)" unter **http://go.microsoft.com/fwlink/?linkid=247428\&clcid=0x407** .

4.  Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:
    
    1.  Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:
        
        1.  Geben Sie **\\exec sp\_who2** ein, um Verbindungen mit der mgc-Datenbank zu identifizieren.
        
        2.  Geben Sie **\\kill \<spid\>** ein, um diese Verbindungen zu beenden.
    
    2.  Stellen Sie die Datenbank online bereit:
        
        1.  Führen Sie für die mgc-Datenbank mit **\\restore** eine Wiederherstellung durch.

5.  Verwenden Sie in der Lync Server-Verwaltungsshell den Befehl **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver**, um ein Failover zur mgc-Backupdatenbank durchzuführen. Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat für atl-cs-001.litwareinc.com zu ersetzen.
    
    Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.

6.  Verwenden Sie in der Lync Server-Verwaltungsshell das Cmdlet **Install-CsMirrorDatabase**, um für die Sicherungsdatenbank, die jetzt als Primärdatenbank dient, eine Hochverfügbarkeitsspiegelung einzurichten. Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz. Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde. Detailliere Informationen finden Sie im Abschnitt "Verwenden von Lync Server-Verwaltungsshell-Cmdlets" in [Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Legen Sie die aktiven Server für den Server für beständigen Chat fest. Verwenden Sie in der Lync Server-Befehlsshell das Cmdlet **Set-CsPersistentChatActiveServer**, um die Liste der aktiven Server festzulegen.
    

    > [!IMPORTANT]
    > Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum, das über eine Verbindung mit einer geringen Latenz und hohen Bandbreite zu der Datenbank verfügt, befinden.

    
    An dieser Stelle wird das Failover der Server für beständigen Chat-Primärdatenbank zur Server für beständigen Chat-Sicherungsdatenbank erfolgreich abgeschlossen.

