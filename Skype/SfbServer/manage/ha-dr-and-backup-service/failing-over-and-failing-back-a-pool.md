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
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0e738faa84053f9a4d4c92127b008d397f042499
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013909"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Ausführen eines Failovers und Ausführen eines Failbacks für einen Pool in Skype for Business Server

Verwenden Sie die folgenden Verfahren, wenn ein einzelner Front-End Pool fehlgeschlagen ist und ein Failover ausgeführt werden muss, oder wenn der Pool, in dem das Notfall aufgetreten ist, wieder online ist und Sie ihre Bereitstellung auf den regulären Arbeitsstatus wiederherstellen müssen. Erfahren Sie, wie Sie den Edgepool, der für Skype for Business Partnerverbund oder XMPP-Partnerverbund verwendet wird, failovern und zurücksetzen oder den Edgepool ändern, der einem Front-End Pool zugeordnet ist.

- [Failover eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Failback eines Pools](#fail-back-a-pool)
- [Failover des für Skype for Business Server Partnerverbund verwendeten Edgepools](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover des Edgepools, der für den XMPP-Partnerverbund in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Ausführen eines Failbacks für den Edgepool, der für Skype for Business Server Partnerverbund oder XMPP-Partnerverbund verwendet wird](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des einem Front-End-Pool zugeordneten Edgepools](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover eines Front-End-Pools

Datacenter1 enthält Pool1, und Pool1 ist fehlgeschlagen. Sie wechseln nicht zu Pool2 in Datacenter2.

Der Großteil der Arbeit für das Poolfailover umfasst einen Failover des zentralen Verwaltungsspeichers, falls erforderlich. Der zentrale Verwaltungsspeicher muss funktionsfähig sein, wenn für die Benutzer des Pools ein Failover ausgeführt wird.

Wenn ein Front-End-Pool fehlschlägt, der Edgepool an diesem Standort aber noch ausgeführt wird, müssen Sie wissen, ob der Edgepool den ausgefallenen Pool als nächsten Hoppool verwendet. Andernfalls müssen Sie den Edgepool so ändern, dass er einen anderen Front-End Pool verwendet, bevor ein Failover des fehlgeschlagenen Front-End-Pools ausgeführt wird. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge einen Pool am selben Standort wie der Edgepool oder einen anderen Standort verwendet.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools am selben Standort fest**

1. Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den Edgepool, der geändert werden muss, und wählen Sie **"Eigenschaften bearbeiten"** aus.

2. Wählen Sie **"Nächster Hop" aus.** Wählen Sie in der Liste **"Nächster Hoppool:** Liste" den Pool aus, der jetzt als nächster Hoppool fungiert.

3. Wählen Sie **"OK"** aus, und veröffentlichen Sie die Änderungen.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools an einem anderen Standort fest**

1. Öffnen Sie ein fenster Skype for Business Server Verwaltungsshell, und geben Sie das folgende Cmdlet ein:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**So führen Sie einen Failover für einen Pool in einem Notfall durch**

1. Suchen Sie den Hostpool für den zentralen Verwaltungsserver, indem Sie das folgende Cmdlet auf einem Front-End Server in Pool2 eingeben:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Die Ergebnisse dieses Cmdlets zeigen, welcher Pool derzeit den zentralen Verwaltungsserver hostet. Im restlichen Teil dieses Verfahrens wird dieser Pool als \_ CMS-Pool bezeichnet.

2. Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu finden, die im \_ CMS-Pool ausgeführt werden. Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Sicherungspool \_ soll der Sicherungspool sein.

3. Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Dieses Cmdlet sollte zeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des \_ CMS-Pools verweisen. Wenn sie leer sind, ist der zentrale Verwaltungsserver nicht verfügbar, und Sie müssen einen Failover ausführen.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher in Pool1 ausgeführt wurde (d. h. der pool, der fehlgeschlagen ist), müssen Sie einen Failover auf dem zentralen Verwaltungsserver ausführen, bevor Sie einen Failover für den Pool ausführen. Wenn Sie einen Failover des zentralen Verwaltungsservers ausführen müssen, der in einem Pool mit Skype for Business Server gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie den zentralen Verwaltungsserver nicht übergehen müssen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Führen Sie die folgenden Schritte aus, um einen Failover des zentralen Verwaltungsspeichers in einem Pool auszuführen, der Skype for Business Server ausgeführt wird:

    1. Überprüfen Sie zunächst, welcher Back-End Server im \_ Sicherungspool die Hauptinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Wenn der primäre Back-End Server im \_ Sicherungspool der Prinzipal ist, geben Sie Folgendes ein:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Wenn die Spiegelung Back-End Server im \_ Sicherungspool der Prinzipal ist, geben Sie Folgendes ein:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Überprüfen Sie, ob das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie den folgenden Befehl ein:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des \_ Sicherungspools zeigen.
    
    1. Überprüfen Sie abschließend den Replikatstatus für alle Front-End Server, indem Sie Folgendes eingeben:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Überprüfen Sie, ob alle Replikate den Wert True aufweisen.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-Server des \_ Sicherungspools.
    
    1. Führen Sie zunächst den folgenden Befehl aus:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Führen Sie den nächsten Befehl auf einem der Front-End-Server des \_ Sicherungspools aus, um die Verschiebung des zentralen Verwaltungsspeichers zu erzwingen:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. Überprüfen Sie, ob die Verschiebung abgeschlossen ist:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des \_ Sicherungspools zeigen.
    
    1. Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Überprüfen Sie, ob alle Replikate den Wert True aufweisen.
    
    1. Installieren Sie den zentralen Verwaltungsserverdienst auf den restlichen Front-End-Servern im \_ Sicherungspool. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme des Befehls, den Sie beim Erzwingen der Verschiebung des zentralen Verwaltungsspeichers weiter oben in diesem Verfahren verwendet haben:

        ```console
        Bootstrapper /Setup
        ```

7.  Führen Sie ein Failover der Benutzer von Pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem Skype for Business Server Verwaltungsshell-Fenster ausführen:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Da die Schritte in den vorherigen Teilen dieses Verfahrens zum Überprüfen des Status des zentralen Verwaltungsspeichers nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlgeschlagen ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edgepool an diesem Standort so ändern, dass ein anderer Pool als nächster Hop verwendet wird, bevor ein Failover über den Pool ausgeführt wird. Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Failback eines Pools

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Der Failbackvorgang dauert mehrere Minuten. Als Referenz wird erwartet, dass es bis zu 60 Minuten für einen Pool mit 20.000 Benutzern dauert.

Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

Weitere Schritte sind nicht erforderlich. Wenn ein Fehler auf dem zentralen Verwaltungsserver aufgetreten ist, können Sie ihn in Pool2 belassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover des für Skype for Business Server Partnerverbund verwendeten Edgepools 

Wenn der Edgepool, in dem Sie Skype for Business Server Verbund konfiguriert haben, ausfällt, müssen Sie den Partnerverbund so ändern, dass ein anderer Edgepool verwendet wird, damit der Partnerverbund funktioniert.

1.  Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie **Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

3.  Erweitern Sie **Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, den Sie jetzt für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

5.  Wählen Sie **"Aktion",** **"Topologie"** und **"Veröffentlichen"** aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen,** wählen Sie **"Weiter"** aus. Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **Fertig stellen** aus.

6.  Öffnen Sie auf dem Edgeserver den Skype for Business Server Bereitstellungs-Assistenten. Wählen Sie **"Skype for Business Server System installieren oder aktualisieren"** und dann **"Setup" oder "Skype for Business Server Komponenten entfernen"** aus. Wählen Sie **Erneut ausführen** aus.

7.  Wählen Sie **Weiter** aus. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Wählen Sie nach Abschluss der Bereitstellung **"Protokoll anzeigen"** aus, um die verfügbaren Protokolldateien anzuzeigen. Wählen Sie **"Fertig stellen"** aus, um die Bereitstellung abzuschließen.
    
    Wenn der Standort, der den fehlerhaften Edgepool enthält, front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End Pools aktualisieren, um einen Edgepool an einem Remotestandort zu verwenden, der noch ausgeführt wird. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover des für den XMPP-Partnerverbund in Skype for Business Server verwendeten Edgepools 

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. 

Im folgenden Verfahren ist EdgePool1 der Pool, der ursprünglich den XMPP-Partnerverbund gehostet hat, und EdgePool2 ist der Pool, der jetzt den XMPP-Partnerverbund hosten wird.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>So führen Sie einen Failover des Edgepools durch, der für den XMPP-Partnerverbund verwendet wird

1.  Wenn Sie noch keinen anderen Edgepool bereitgestellt haben (neben dem, der derzeit nicht verfügbar ist), stellen Sie diesen Pool bereit. 

2.  Führen Sie auf jedem Edgeserver im neuen Edgepool, in dem jetzt der XMPP-Verbund gehostet wird (EdgePool2), das folgende Cmdlet aus:

    ```powershell
    Stop-CsWindowsService
    ```

3.  Führen Sie das folgende Cmdlet aus, damit die XMPP-Verbundroute wieder auf EdgePool2 zeigt:

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    In diesem Beispiel stellt Site2 den Standort mit dem Edgepool dar, in dem jetzt die XMPP-Verbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Verbund, sodass dieser auf EdgeServer2.contoso.com verweist.

5.  Wenn Sie noch nicht über einen DNS-SRV-Eintrag für den XMPP-Verbund verfügen, der in den Edgepool aufgelöst wird, in dem jetzt der XMPP-Verbund gehostet wird, müssen Sie diesen hinzufügen, wie im folgenden Beispiel veranschaulicht. Dieser SRV-Eintrag muss den Portwert 5269 aufweisen.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  Vergewissern Sie sich, dass in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird, der Port 5269 für die externe Kommunikation geöffnet ist.

7.  Starten Sie die Dienste auf allen Edgeservern in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird:

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Ausführen eines Failbacks für den Edgepool, der für Skype for Business Server Partnerverbund oder XMPP-Partnerverbund verwendet wird 

Nachdem ein fehlgeschlagener Edgepool, der zum Hosten des Partnerverbunds verwendet wurde, wieder online geschaltet wurde, führen Sie dieses Verfahren aus, um die Skype for Business Server Partnerverbundroute und/oder die XMPP-Partnerverbundroute zum erneuten Verwenden dieses wiederhergestellten Edgepools zu verwenden.

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Wenn Sie die Skype for Business Server Verbundroute für die Verwendung des wiederhergestellten Edgeservers zurücksetzen möchten, gehen Sie wie folgt vor:
    
    1. Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie **Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
    1. Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
    1. Erweitern Sie **Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserverpool, den Sie erneut für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
    1. Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
    1. Wählen Sie **"Aktion",** **"Topologie"** und **"Veröffentlichen"** aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen,** wählen Sie **"Weiter"** aus. Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **Fertig stellen** aus.
    
    1. Öffnen Sie auf dem Edgeserver den Skype for Business Server-Bereitstellungs-Assistenten. Wählen Sie **"Skype for Business Server System installieren oder aktualisieren"** und dann **"Setup" oder "Skype for Business Server Komponenten entfernen"** aus. Wählen Sie **Erneut ausführen** aus.
    
    1. Wählen Sie **Weiter** aus. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Wählen Sie nach Abschluss der Bereitstellung **"Protokoll anzeigen"** aus, um die verfügbaren Protokolldateien anzuzeigen. Wählen Sie **"Fertig stellen"** aus, um die Bereitstellung abzuschließen.

3.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die XMPP-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
    1. Führen Sie das folgende Cmdlet aus, um die XMPP-Partnerverbundroute erneut auf den Edgepool zu verweisen, von dem nun der XMPP-Partnerverbund gehostet wird (in diesem Beispiel EdgeServer1):
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        In diesem Beispiel ist Site1 der Standort, der den Edgepool enthält, von dem nun die XMPP-Partnerverbundroute gehostet wird. EdgeServer1.contoso.com ist der vollqualifizierte Domänenname (FQDN) eines Edgeservers in diesem Pool.
    
    1. Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.
    
    1. Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.

4.  Falls die Front-End-Pools weiter an dem Standort ausgeführt werden, der den ausgefallenen und inzwischen wiederhergestellten Edgepool enthält, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End-Pools aktualisieren, sodass wieder die Edgepools am lokalen Standort verwendet werden.

5.  Falls der Front-End-Pool am selben Standort wie der ausgefallene Edgepool ebenfalls ausgefallen ist, können Sie nun mit Invoke–CsPoolFailback ein Failback auf den Front-End-Pool ausführen.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des einem Front-End-Pool zugeordneten Edgepools

Wenn ein Edgepool ausfällt, aber der Front-End-Pool an demselben Standort noch ausgeführt wird, müssen Sie den Front-End-Pool so konfigurieren, dass er einen Edgepool an einem anderen Standort verwendet, bis der ausgefallene Edgepool wiederhergestellt ist.

1.  Navigieren Sie im Topologie-Generator zum Namen des Front-End-Pools, den Sie ändern möchten.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und wählen Sie dann **Eigenschaften bearbeiten** aus.

3.  Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.

4.  Wählen Sie **OK** aus.
