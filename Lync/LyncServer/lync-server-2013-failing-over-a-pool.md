---
title: 'Lync Server 2013: Ausführen eines Failovers für einen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Ausführen eines Failovers für einen Pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-10_

Wenn ein einzelner Front-End-Pool ausgefallen ist und ein Failover durchgeführt werden muss, gehen Sie wie folgt vor: In diesem Verfahren enthält Datacenter1 pool1, und pool1 ist fehlgeschlagen. Sie haben einen Failover zu Pool2 befindet sich in Datacenter2.

Der größte Teil der Arbeit für das Pool-Failover umfasst einen Failover des zentralen Verwaltungsspeichers, falls dies erforderlich ist. Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn die Benutzer des Pools fehlerhaft sind.

Wenn ein Front-End-Pool fehlschlägt, der Edge-Pool an dieser Website jedoch weiterhin ausgeführt wird, müssen Sie wissen, ob der Edge-Pool den fehlerhaften Pool als nächsten Hop-Pool verwendet. Wenn dies der Fall ist, müssen Sie den Edge-Pool so ändern, dass ein anderer Front-End-Pool verwendet wird, bevor der fehlerhafte Front-End-Pool fehlschlägt. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge-Pool am gleichen Standort wie der Edge-Pool oder auf einer anderen Website verwendet wird.

**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools auf derselben Website ein**

1.  Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den zu ändernden Edge-Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Klicken Sie auf **Nächster Hop**. Wählen Sie in der Liste **Nächster Hop-Pool:** den Pool aus, der nun als nächster Hop-Pool fungieren soll.

3.  Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.

**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools an einer anderen Website ein**

1.  Öffnen Sie ein lync Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**So führen Sie einen Failover eines Pools in einem Notfall durch**

1.  Ermitteln Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse dieses Cmdlets zeigen, in welchem Pool zurzeit der zentrale Verwaltungs Server gehostet wird. Im weiteren Verlauf dieses Verfahrens wird dieser Pool als "CMS\_-Pool" bezeichnet.

2.  Verwenden Sie den Topologie-Generator, um die Version von lync Server zu\_finden, die im CMS-Pool ausgeführt wird. Wenn Sie lync Server 2013 ausführen, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Lassen Sie\_den Backup-Pool zum Backup-Pool werden.

3.  Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte anzeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS\_-Pools verweisen. Wenn Sie leer sind, steht der zentrale Verwaltungs Server nicht zur Verfügung, und Sie müssen einen Failover durchführen.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher auf pool1 ausgeführt wurde (also der Pool, bei dem ein Fehler aufgetreten ist), müssen Sie vor dem Failover des Pools einen Failover für den zentralen Verwaltungs Server durchführen. Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit lync Server 2013 gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit lync Server 2010 gehostet wurde, verwenden Sie das Cmdlet in Schritt 6 dieses Verfahrens. Wenn Sie keinen Failover für den zentralen Verwaltungs Server benötigen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Gehen Sie wie folgt vor, um einen Failover des zentralen Verwaltungsspeichers in einem Pool mit lync Server 2013 auszuführen:
    
      - Überprüfen Sie zunächst, welcher Back-End\_-Server im Sicherungs Pool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back-End-Server\_im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegelungs-Back-End\_-Server im Sicherungs Pool der Prinzipal ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, ob der Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie Folgendes ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.
    
      - Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, ob alle Replikate den Wert true aufweisen.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-\_Server des Sicherungs Pools.
    
      - Führen Sie zunächst den folgenden Befehl aus:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Führen Sie den nächsten Befehl auf einem der Front-End-Server\_des Sicherungs Pools aus, um den Wechsel des zentralen Verwaltungsspeichers zu erzwingen:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Überprüfen Sie, ob die Verschiebung abgeschlossen ist:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des\_Sicherungs Pools verweisen.
    
      - Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, ob alle Replikate den Wert true aufweisen.
    
      - Installieren Sie den zentralen Verwaltungs Server Dienst auf den restlichen Front-End-Servern im\_Sicherungs Pool. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme derjenigen, die Sie beim Erzwingen des zentralen Verwaltungsspeichers weiter oben in diesem Verfahren verwendet haben:
        
            Bootstrapper /Setup 

7.  Führen Sie einen Failover der Benutzer von pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem Fenster der lync Server-Verwaltungsshell ausführen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die Schritte, die in den vorherigen Abschnitten dieses Verfahrens zur Überprüfung des Status des zentralen Verwaltungsspeichers durchgeführt wurden, nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlerhaft ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool auf dieser Website ändern, um einen anderen Pool als nächsten Hop zu verwenden, bevor Sie einen Failover für den Pool durchführen. Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

