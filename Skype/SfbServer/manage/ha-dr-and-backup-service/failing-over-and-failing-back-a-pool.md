---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826565"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Führen Sie ein Failing over und ein Failing Back für einen Pool in Skype for Business Server aus. 

Führen Sie die folgenden Verfahren aus, wenn ein einzelner Front-End-Pool fehlgeschlagen ist und ein Fehler durchgeführt werden muss, oder wenn der Pool, bei dem der Notfall aufting, wieder online ist und Sie den normalen Betriebsstatus der Bereitstellung wiederherstellen müssen. Erfahren Sie auch, wie Sie ein Failover für den Edgepool, der für den Skype for Business- oder den XMPP-Verbund verwendet wird, oder den Edgepool ändern, der einem Front-End-Pool zugeordnet ist.

- [Failover eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Fail back a pool](#fail-back-a-pool)
- [Failover für den Edgepool, der für den Skype for Business Server-Verbund verwendet wird](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover des Edgepools, der für den XMPP-Verbund in Skype for Business Server verwendet wird](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fail back the Edge pool used for Skype for Business Server federation or XMPP federation](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des Edgepools, der einem Front-End-Pool zugeordnet ist](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover eines Front-End-Pools

In diesem Verfahren enthält "Datacenter1" "Pool1", und "Pool1" ist fehlgeschlagen. Sie können einen Fehler auf "Pool2" in "Datacenter2" ausf?en.

Der Großteil der Arbeit für das Poolfailover umfasst bei Bedarf ein Failover des zentralen Verwaltungsspeichers. Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn für die Benutzer des Pools ein Fehler auftrat.

Wenn ein Front-End-Pool ausfällt, der Edgepool an diesem Standort jedoch noch ausgeführt wird, müssen Sie außerdem wissen, ob der ausgefallene Pool vom Edgepool als nächster Hoppool verwendet wird. Wenn dies der Fehler ist, müssen Sie den Edgepool so ändern, dass ein anderer Front-End-Pool verwendet wird, bevor ein Fehler beim Front-End-Pool vornimmt. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge einen Pool am selben Standort wie der Edgepool oder einen anderen Standort verwendet.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools am gleichen Standort**

1.  Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den Edgepool, der geändert werden muss, und klicken Sie auf **"Eigenschaften bearbeiten".**

2.  Klicken Sie **auf "Nächster Hop".** Wählen Sie **in der Liste "Nächster Hoppool:** " den Pool aus, der jetzt als nächster Hoppool dienen soll.

3.  Klicken Sie **auf "OK",** und veröffentlichen Sie die Änderungen.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools an einem anderen Standort**

1.  Öffnen Sie ein Skype for Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**So führen Sie ein Failover eines Pools in einem Notfall durch**

1.  Suchen Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse dieses Cmdlets zeigen, welcher Pool derzeit den zentralen Verwaltungsserver hostet. Im restlichen Verfahren wird dieser Pool als "CMS-Pool" \_ bezeichnet.

2.  Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu finden, die im CMS Pool \_ ausgeführt wird. Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu suchen.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Der \_ Sicherungspool soll der Sicherungspool sein.

3.  Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte zeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS-Pools \_ zeigen. Wenn sie leer sind, ist der zentrale Verwaltungsserver nicht verfügbar, und Sie müssen ein Failover des Servers starten.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher in Pool1 ausgeführt wurde (d. h. dem ausgefallenen Pool), müssen Sie ein Failover des zentralen Verwaltungsservers ausführen, bevor Sie einen Failover des Pools ausführen. Wenn Sie ein Failover des zentralen Verwaltungsservers ausführen müssen, der in einem Pool mit Skype for Business Server gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn kein Failover des zentralen Verwaltungsservers erforderlich ist, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Gehen Sie wie folgt vor, um ein Failover für den zentralen Verwaltungsspeicher in einem Pool mit Skype for Business Server zu erstellen:
    
      - Überprüfen Sie zunächst, auf welchem Back-End-Server im Sicherungspool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausgeführt wird, indem Sie \_ Folgendes eingeben:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back-End-Server im \_ Sicherungspool der Prinzipal ist, geben Sie:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegel-Back-End-Server im \_ Sicherungspool der Prinzipal ist, geben Sie:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, ob das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie Folgendes ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des Sicherungspools \_ zeigen.
    
      - Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, ob alle Replikate den Wert "True" haben.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-Server des \_ Sicherungspools.
    
      - Führen Sie zunächst den folgenden Befehl aus:
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Führen Sie den nächsten Befehl auf einem der Front-End-Server des Sicherungspools aus, um das Verschieben des \_ zentralen Verwaltungsspeichers zu erzwingen:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Überprüfen Sie, ob die Bewegung abgeschlossen ist:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des Sicherungspools \_ zeigen.
    
      - Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, ob alle Replikate den Wert "True" haben.
    
      - Installieren Sie den zentralen Verwaltungsserverdienst auf den restlichen Front-End-Servern im \_ Sicherungspool. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme des Befehls, den Sie beim Erzwingen der Verschieben des zentralen Verwaltungsspeichers weiter oben in diesem Verfahren verwendet haben:
        
            Bootstrapper /Setup 

7.  Führen Sie das folgende Cmdlet in einem Fenster der Skype for Business Server-Verwaltungsshell aus, um ein Failover für die Benutzer von Pool1 zu Pool2 zu erstellen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die Schritte in den vorherigen Teilen dieses Verfahrens zum Überprüfen des Status des zentralen Verwaltungsspeichers nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlgeschlagen ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edgepool an diesem Standort so ändern, dass ein anderer Pool als nächster Hop verwendet wird, bevor Sie einen Fehler für den Pool beheben. Weitere Informationen finden Sie in den Verfahren zu Beginn dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Fail back a pool

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Beachten Sie, dass der Failback-Prozess einige Zeit in Anspruch nehmen kann.  So würde zum Beispiel ein Pool mit 20.000 Benutzern bis zu 60 Minuten benötigen.

Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Weitere Schritte sind nicht erforderlich. Wenn ein Fehler auf dem zentralen Verwaltungsserver auftrat, können Sie ihn in Pool2 be lassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover des Edgepools, der für den Skype for Business Server-Verbund verwendet wird 

Wenn der Edgepool, für den Sie den Skype for Business Server-Verbund konfiguriert haben, aus dem Aus ist, müssen Sie den Verbund so ändern, dass er einen anderen Edgepool verwendet, damit der Verbund funktioniert.

1.  Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

3.  Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, den Sie jetzt für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

5.  Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

6.  Öffnen Sie auf dem Edgeserver den Skype for Business Server-Bereitstellungs-Assistenten. Klicken **Sie auf "Skype for Business Server System** installieren oder aktualisieren", und klicken Sie dann auf "Skype for Business Server-Komponenten einrichten **oder entfernen".** Klicken Sie auf **Erneut ausführen**.

7.  Klicken Sie auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.
    
    Wenn der Standort mit dem ausgefallenen Edgepool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren und für einen Edgepool an einem Remotestandort konfigurieren, der weiterhin ausgeführt wird. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover des Edgepools, der für den XMPP-Verbund in Skype for Business Server verwendet wird 

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. 

Im folgenden Verfahren stellt EdgePool1 den Pool dar, in dem der XMPP-Verbund ursprünglich gehostet wurde; EdgePool2 ist der Pool, in dem der XMPP-Verbund jetzt gehostet werden soll.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>So führen Sie ein Failover des Edgepools durch, der für den XMPP-Verbund verwendet wird

1.  Wenn Sie (neben dem ausgefallenen) noch keinen weiteren Edgepool bereitgestellt haben, stellen Sie den Pool jetzt bereit. 

2.  Führen Sie auf jedem Edgeserver im neuen Edgepool, in dem jetzt der XMPP-Verbund gehostet wird (EdgePool2), das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie das folgende Cmdlet aus, damit die XMPP-Verbundroute wieder auf EdgePool2 zeigt:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel stellt Site2 den Standort mit dem Edgepool dar, in dem jetzt die XMPP-Verbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Verbund, sodass dieser auf EdgeServer2.contoso.com verweist.

5.  Wenn Sie noch nicht über einen DNS-SRV-Eintrag für den XMPP-Verbund verfügen, der in den Edgepool aufgelöst wird, in dem jetzt der XMPP-Verbund gehostet wird, müssen Sie diesen hinzufügen, wie im folgenden Beispiel veranschaulicht. Dieser SRV-Eintrag muss den Portwert 5269 aufweisen.
    
        _xmpp-server._tcp.contoso.com

6.  Vergewissern Sie sich, dass in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird, der Port 5269 für die externe Kommunikation geöffnet ist.

7.  Starten Sie die Dienste auf allen Edgeservern in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Fail back the Edge pool used for Skype for Business Server federation or XMPP federation 

Nachdem ein ausgefallener Edgepool, der zum Hosten des Verbunds verwendet wurde, wieder online geschaltet wurde, führen Sie dieses Verfahren aus, um die Skype for Business Server-Verbundroute und/oder die XMPP-Verbundroute zurück zu führen, um diesen wiederhergestellten Edgepool erneut zu verwenden.

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Wenn Sie ein Fail back der Skype for Business Server-Verbundroute für die Verwendung des wiederhergestellten Edgeservers wünschen, gehen Sie wie folgt vor:
    
      - Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder auf den Edgeserverpool, der zurzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserver-Pool, den Sie wieder für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Aktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.
    
      - Öffnen Sie auf dem Edgeserver den Skype for Business Server-Bereitstellungs-Assistenten. Klicken **Sie auf "Skype for Business Server System** installieren oder aktualisieren", und klicken Sie dann **auf "Skype for Business Server-Komponenten einrichten" oder "Entfernen".** Klicken Sie auf **Erneut ausführen**.
    
      - Klicken Sie auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.

3.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die XMPP-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-Partnerverbundroute erneut auf den Edgepool zu verweisen, von dem nun der XMPP-Partnerverbund gehostet wird (in diesem Beispiel EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel ist Site1 der Standort, der den Edgepool enthält, von dem nun die XMPP-Partnerverbundroute gehostet wird. EdgeServer1.contoso.com ist der vollqualifizierte Domänenname (FQDN) eines Edgeservers in diesem Pool.
    
      - Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.
    
      - Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.

4.  Falls die Front-End-Pools weiter an dem Standort ausgeführt werden, der den ausgefallenen und inzwischen wiederhergestellten Edgepool enthält, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End-Pools aktualisieren, sodass wieder die Edgepools am lokalen Standort verwendet werden.

5.  Falls der Front-End-Pool am selben Standort wie der ausgefallene Edgepool ebenfalls ausgefallen ist, können Sie nun mit Invoke–CsPoolFailback ein Failback auf den Front-End-Pool ausführen.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des Edgepools, der einem Front-End-Pool zugeordnet ist

Wenn ein Edgepool ausfällt, aber der Front-End-Pool an demselben Standort noch ausgeführt wird, müssen Sie den Front-End-Pool so konfigurieren, dass er einen Edgepool an einem anderen Standort verwendet, bis der ausgefallene Edgepool wiederhergestellt ist.

1.  Navigieren Sie im Topologie-Generator zum Namen des Front-End-Pools, den Sie ändern möchten.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

3.  Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.

4.  Klicken Sie auf **OK**.
