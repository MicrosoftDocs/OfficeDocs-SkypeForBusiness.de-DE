---
title: 'Lync Server 2013: Ausführen eines Failovers für einen Pool'
TOCTitle: Ausführen eines Failovers für einen Pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204678(v=OCS.15)
ms:contentKeyID: 49293208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failovers für einen Pool in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-10-10_

Wenn ein einzelner Front-End-Pool ausgefallen ist und ein Failover erforderlich ist, wenden Sie das folgende Verfahren an. In diesem Verfahren enthält „Datacenter1“ „Pool1“ und „Pool1“ ist ausgefallen. Sie führen ein Failover auf „Pool2“ in „Datacenter2“ aus.

Der größte Aufwand beim Poolfailover besteht im Durchführen des Failovers des zentralen Verwaltungsspeichers, falls erforderlich. Dies ist wichtig, da der zentralen Verwaltungsspeicher funktionieren muss, wenn das Failover der Benutzer des Pools ausgeführt wird.

Wenn ein Front-End-Pool ausfällt, der Edgepool am selben Standort jedoch noch funktioniert, müssen Sie außerdem wissen, ob der Edgepool den ausgefallenen Pool als nächsten Hoppool verwendet. Wenn dies der Fall ist, müssen Sie den Edgepool so ändern, dass er einen anderen Front-End-Pool verwendet, bevor ein Failover für den ausgefallenen Front-End-Pool ausgeführt wird. Die Änderung der Einstellung des nächsten Hoppools hängt davon ab, ob der Edgepool einen Pool am selben oder einem anderen Standort verwendet.

**So konfigurieren Sie einen Edgepool zur Verwendung als nächsten Hoppool am selben Standort fest**

1.  Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den zu ändernden Edgepool und klicken Sie auf **Eigenschaften bearbeiten** .

2.  Klicken Sie auf **Nächster Hop** . Wählen Sie in der Liste **Nächster Hoppool** den Pool aus, der als nächster Hoppool dienen soll.

3.  Klicken Sie auf **OK** , veröffentlichen Sie dann die Änderungen.

**So konfigurieren Sie einen Edgepool zur Verwendung als nächsten Hoppool an einem anderen Standort fest**

1.  Öffnen Sie ein Lync Server-Verwaltungsshell-Fenster und geben Sie das folgende Cmdlet ein:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Failover eines Pools im Notfall**

1.  Ermitteln Sie, welcher Pool als Host für den zentraler Verwaltungsserver dient, indem Sie auf einem Front-End-Server in „Pool2“ folgendes Cmdlet eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse dieses Cmdlets geben an, welcher Pool derzeit als Host für den zentraler Verwaltungsserver dient. Im weiteren Verfahren wird dieser Pool als „CMS\_Pool“ bezeichnet.

2.  Verwenden Sie den Topologie-Generators, um die im CMS\_Pool ausgeführte Lync Server-Version zu ermitteln. Wenn Lync Server 2013 ausgeführt wird, verwenden Sie folgendes Cmdlet, um den Sicherungspool von Pool 1 zu finden.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Verwenden Sie „Backup\_Pool“ als Sicherungspool.

3.  Überprüfen Sie den Status von zentralen Verwaltungsspeicher mit folgendem Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte angeben, dass sowohl "ActiveMasterFQDN" und „ActiveFileTransferAgents“ auf den FQDN von „CMS\_Pool“ verweisen. Wenn sie leer sind, ist der zentraler Verwaltungsserver nicht verfügbar und sie müssen ein Failover dafür ausführen.

4.  Wenn der zentralen Verwaltungsspeicher nicht verfügbar ist oder wenn der zentralen Verwaltungsspeicher in „Pool1“ ausgeführt wurde (d. h. dem ausgefallenen Pool), müssen Sie ein Failover für den zentraler Verwaltungsserver ausführen, bevor Sie ein Failover für den Pool ausführen. Wenn Sie ein Failover für den zentraler Verwaltungsserver ausführen müssen, der in einem Pool gehostet war, in dem Lync Server 2013 ausgeführt wurde, verwenden Sie das Cmdlet aus Schritt 5 in diesem Verfahren. Wenn Sie ein Failover für den zentraler Verwaltungsserver ausführen müssen, der in einem Pool gehostet war, in dem Lync Server 2010 ausgeführt wurde, verwenden Sie das Cmdlet aus Schritt 6 in diesem Verfahren. Wenn Sie kein Failover für den zentraler Verwaltungsserver ausführen müssen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Gehen Sie wie folgt vor, um ein Failover für den zentralen Verwaltungsspeicher in einem Pool durchzuführen, in dem Lync Server 2013 ausgeführt wird:
    
      - Ermitteln Sie zunächst, auf welchem Back-End-Server in „Backup\_Pool“ die Prinzipalinstanz des zentralen Verwaltungsspeichers ausgeführt wird, indem Sie Folgendes eingeben:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back-End-Server in „Backup\_Pool“ der Prinzipalserver ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegel-Back-End-Server in „Backup\_Pool“ der Prinzipalserver ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, dass das zentraler Verwaltungsserver-Failover abgeschlossen ist. Geben Sie Folgendes ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, dass sowohl „ActiveMasterFQDN“ als auch „ActiveFileTransferAgents“ auf den FQDN von „Backup\_Pool“ verweisen.
    
      - Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, dass alle Replikate den Wert „True“ aufweisen.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-Server von „Backup\_Pool“.
    
      - Führen Sie zuerst den folgenden Befehl aus:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Führen Sie den nächsten Befehl auf einem der Front-End-Server von „Backup\_Pool“ aus, um die Verschiebung des zentralen Verwaltungsspeichers zu erzwingen:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Prüfen Sie, ob die Verschiebung abgeschlossen ist:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, dass sowohl „ActiveMasterFQDN“ als auch „ActiveFileTransferAgents“ auf den FQDN von „Backup\_Pool“ verweisen.
    
      - Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, dass alle Replikate den Wert „True“ aufweisen.
    
      - Installieren Sie den zentraler Verwaltungsserver-Dienst auf den übrigen Front-End-Servern in „Backup\_Pool“. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme des Servers den Sie beim Erzwingen der Verschiebung von zentralen Verwaltungsspeicher in diesem Verfahren bereits verwendet haben:
        
            Bootstrapper /Setup 

7.  Führen Sie ein Failover der Benutzer von „Pool1“ nach „Pool2“ aus, indem Sie das folgende Cmdlet in einem Lync Server-Verwaltungsshell-Fenster ausführen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die zuvor in diesem Verfahren ausgeführten Schritte zum Überprüfen des zentralen Verwaltungsspeicher-Status nicht universell sind, besteht dennoch die Möglichkeit, dass dieses Cmdlet fehlschlägt, da das Failover von zentralen Verwaltungsspeicher noch nicht vollständig ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und das Cmdlet anschließend erneut ausführen.
    
    Wenn folgende Fehlermeldung angezeigt wird, müssen Sie den Edgepool an diesem Standort so ändern, dass er einen andern Pool als nächsten Hop verwendet, bevor das Failover für den Pool durchgeführt wird. Nähere Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

