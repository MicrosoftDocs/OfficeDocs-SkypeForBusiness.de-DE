---
title: 'Lync Server 2013: Fehler bei einem Pool'
description: 'Lync Server 2013: Fehler bei einem Pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554981"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a>Failover eines Pools in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-10_

Wenn ein einzelnes Front-End-Pool fehlgeschlagen ist und ein Failover erfolgen muss, gehen Sie wie folgt vor: In diesem Verfahren enthält Datacenter1 pool1, und pool1 ist fehlgeschlagen. Es tritt ein Failover zu Pool2 auf, das sich in Datacenter2 befindet.

Für den Großteil der Arbeit für das Pool Failover ist ein Failover des zentralen Verwaltungsspeichers erforderlich, falls dies erforderlich ist. Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn die Benutzer des Pools einen Failover durchlaufen.

Wenn ein Front-End-Pool fehlschlägt, aber der Edgepool an diesem Standort noch ausgeführt wird, müssen Sie wissen, ob der Edgepool den ausgefallenen Pool als nächsten Hop-Pool verwendet. Wenn dies der Fall ist, müssen Sie die Edgepool so ändern, dass eine andere Front-End-Pool verwendet wird, bevor ein Failover des fehlerhaften Front-End-Pool fehlschlägt. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob die Edge-Schnittstelle einen Pool am gleichen Standort wie die Edgepool oder eine andere Website verwendet wird.

**So legen Sie einen Edge-Pool so fest, dass ein nächster Hop-Pool am gleichen Standort verwendet wird**

1.  Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den Edgepool, der geändert werden muss, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Klicken Sie auf **Nächster Hop**. Wählen Sie in der Liste **Nächster Hop-Pool** den Pool aus, der nun als nächster Hop-Pool fungieren soll.

3.  Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.

**So legen Sie einen Edge-Pool für die Verwendung eines nächsten Hop-Pools an einem anderen Standort fest**

1.  Öffnen Sie ein lync Server-Verwaltungsshell Fenster, und geben Sie das folgende Cmdlet ein:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**So führen Sie einen Failover eines Pools in einem Notfall durch**

1.  Ermitteln Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse dieses Cmdlets zeigen an, welcher Pool derzeit den zentralen Verwaltungs Server hostet. Im Rest dieses Verfahrens wird dieser Pool als CMS- \_ Pool bezeichnet.

2.  Verwenden Sie den Topologie-Generator, um die Version von lync Server zu finden, die im CMS \_ -Pool läuft. Wenn Sie lync Server 2013 ausführen, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu suchen.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Sicherungs \_ Pool als Sicherungspool zulassen.

3.  Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte zeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS- \_ Pools zeigen. Wenn Sie leer sind, ist der zentrale Verwaltungs Server nicht verfügbar, und Sie müssen einen Failover durchführen.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder der zentrale Verwaltungsspeicher auf pool1 ausgeführt wurde (das heißt, der Pool, der ausgefallen ist), müssen Sie einen Failover des zentralen Verwaltungsservers durchführen, bevor ein Failover des Pools möglich ist. Wenn Sie einen Failover des zentralen Verwaltungsservers ausführen müssen, der in einem Pool mit lync Server 2013 gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie einen Failover des zentralen Verwaltungsservers ausführen müssen, der in einem Pool mit lync Server 2010 gehostet wurde, verwenden Sie das Cmdlet in Schritt 6 dieses Verfahrens. Wenn Sie keinen Failover für den zentralen Verwaltungs Server ausführen müssen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Führen Sie die folgenden Schritte aus, um einen Failover des zentralen Verwaltungsspeichers in einem Pool auszuführen, auf dem lync Server 2013 ausgeführt wird:
    
      - Überprüfen Sie zunächst, welcher Back-End-Server im Sicherungs \_ Pool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back-End-Server im Sicherungs \_ Pool der Prinzipal ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegel-Back-End-Server im Sicherungs \_ Pool der Prinzipal ist, geben Sie Folgendes ein:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, ob das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie Folgendes ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Stellen Sie sicher, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des Sicherungs \_ Pools verweist.
    
      - Überprüfen Sie schließlich den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Stellen Sie sicher, dass alle Replikate den Wert true aufweisen.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-Server des Sicherungs \_ Pools.
    
      - Führen Sie zunächst den folgenden Befehl aus:
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Führen Sie den nächsten Befehl auf einem der Front-End-Server des Sicherungs \_ Pools aus, um die Verlagerung des zentralen Verwaltungsspeichers zu erzwingen:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Überprüfen, ob die Migration abgeschlossen ist:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Stellen Sie sicher, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des Sicherungs \_ Pools verweist.
    
      - Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Stellen Sie sicher, dass alle Replikate den Wert true aufweisen.
    
      - Installieren Sie den zentralen Verwaltungs Server Dienst auf den restlichen Front-End-Servern im Sicherungs \_ Pool. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme derjenigen, die Sie beim Erzwingen des zentralen Verwaltungsspeichers zuvor in diesem Verfahren verwendet haben:
        
            Bootstrapper /Setup 

7.  Führen Sie einen Failover der Benutzer von pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem lync Server-Verwaltungsshell Fenster ausführen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die Schritte in den vorherigen Abschnitten dieses Verfahrens zum Überprüfen des Status des zentralen Verwaltungsspeichers nicht universell ausgeführt werden, besteht immer noch die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig ausgefallen ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den Fehlermeldungen korrigieren, die angezeigt werden, und dann dieses Cmdlet erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie die Edgepool an dieser Stelle ändern, damit ein anderer Pool als nächster Hop verwendet wird, bevor ein Failover des Pools fehlschlägt. Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
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

