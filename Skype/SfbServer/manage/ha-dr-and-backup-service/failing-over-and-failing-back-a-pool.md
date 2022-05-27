---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675037"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Failover und Failover eines Pools in Skype for Business Server

Verwenden Sie die folgenden Verfahren, wenn ein einzelner Front-End Pool fehlgeschlagen ist und erneut fehlgeschlagen sein muss oder der Pool, in dem die Katastrophe aufgetreten ist, wieder online ist und Sie Ihre Bereitstellung auf den regulären Arbeitsstatus zurücksetzen müssen. Erfahren Sie, wie Sie den Edgepool, der für Skype for Business Partnerverbund oder XMPP-Partnerverbund verwendet wird, fehlschlagen oder den Edgepool ändern, der einem Front-End Pool zugeordnet ist.

- [Failover eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Failback eines Pools](#fail-back-a-pool)
- [Fail over the Edge pool used for Skype for Business Server federation](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Fail over the Edge pool used for XMPP federation in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Failback des Edgepools, der für Skype for Business Server-Partnerverbund oder XMPP-Partnerverbund verwendet wird](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des Einem Front-End-Pool zugeordneten Edgepools](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Fail over a Front-End pool

Datacenter1 enthält Pool1, und Pool1 ist fehlgeschlagen. Sie können nicht zu Pool2 wechseln, der sich in Datacenter2 befindet.

Der Großteil der Arbeit für das Poolfailover umfasst ein Failover über den zentralen Verwaltungsspeicher, falls dies erforderlich ist. Der zentrale Verwaltungsspeicher muss funktionsfähig sein, wenn die Benutzer des Pools nicht erfolgreich sind.The Central Management Store must be functional when the pool's users are failed over.

Wenn ein Front-End-Pool fehlschlägt, der Edgepool an diesem Standort jedoch noch ausgeführt wird, müssen Sie wissen, ob der Edgepool den fehlgeschlagenen Pool als nächsten Hoppool verwendet. In diesem Beispiel müssen Sie den Edgepool so ändern, dass er einen anderen Front-End-Pool verwendet, bevor Sie den fehlgeschlagenen Front-End-Pool nicht ausführen. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge einen Pool am selben Standort wie der Edgepool oder einen anderen Standort verwendet.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools am selben Standort fest**

1. Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den Edgepool, der geändert werden muss, und wählen Sie **"Eigenschaften bearbeiten"** aus.

2. Wählen Sie **"Nächster Hop" aus**. Wählen Sie in der Liste **"Nächster Hoppool:** " den Pool aus, der jetzt als nächster Hoppool dienen soll.

3. Wählen Sie **"OK**" aus, und veröffentlichen Sie die Änderungen.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools an einem anderen Standort fest**

1. Öffnen Sie ein Skype for Business Server-Shell-Fenster, und geben Sie das folgende Cmdlet ein:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**So schlagen Sie bei einem Notfall über einen Pool fehl**

1. Suchen Sie den Hostpool für den zentralen Verwaltungsserver, indem Sie das folgende Cmdlet auf einem Front-End Server in Pool2 eingeben:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Die Ergebnisse dieses Cmdlets zeigen, welcher Pool derzeit den zentralen Verwaltungsserver hostet. Im restlichen Teil dieses Verfahrens wird dieser Pool als CMS-Pool\_bezeichnet.

2. Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu finden, die im CMS-Pool\_ausgeführt wird. Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Lassen Sie Backup\_ Pool der Sicherungspool sein.

3. Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Dieses Cmdlet sollte zeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS-Pools\_verweisen. Wenn sie leer sind, ist der zentrale Verwaltungsserver nicht verfügbar, und Sie müssen ihn überschreiben.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher auf Pool1 ausgeführt wurde (d. h. der Pool, der fehlgeschlagen ist), müssen Sie einen Fehler über den zentralen Verwaltungsserver ausführen, bevor Sie den Pool überschlagen. Wenn Sie einen Fehler über den zentralen Verwaltungsserver ausführen müssen, der in einem Pool gehostet wurde, auf dem Skype for Business Server ausgeführt wird, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie keinen Fehler über den zentralen Verwaltungsserver ausführen müssen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Führen Sie die folgenden Schritte aus, um den zentralen Verwaltungsspeicher in einem Pool zu überschreiben, der Skype for Business Server ausgeführt wird:

    1. Überprüfen Sie zunächst, welcher Back-End Server in Backup\_ Pool die Hauptinstanz des zentralen Verwaltungsspeichers ausführt, indem Sie Folgendes eingeben:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Wenn der primäre Back-End Server in Backup\_ Pool der Prinzipal ist, geben Sie Folgendes ein:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Wenn der Spiegelserver Back-End in Backup\_ Pool der Prinzipal ist, geben Sie Folgendes ein:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Überprüfen Sie, ob das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie den folgenden Befehl ein:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN von Backup\_ Pool verweisen.
    
    1. Überprüfen Sie abschließend den Replikatstatus für alle Front-End Server, indem Sie Folgendes eingeben:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Überprüfen Sie, ob alle Replikate den Wert "True" aufweisen.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf dem Back-End-Server von Backup\_ Pool.
    
    1. Führen Sie zuerst den folgenden Befehl aus:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Führen Sie den nächsten Befehl auf einem der Front-End-Server von Backup\_ Pool aus, um die Verschiebung des zentralen Verwaltungsspeichers zu erzwingen:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. Überprüfen Sie, ob die Verschiebung abgeschlossen ist:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN von Backup\_ Pool verweisen.
    
    1. Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Überprüfen Sie, ob alle Replikate den Wert "True" aufweisen.
    
    1. Installieren Sie den zentralen Verwaltungsserverdienst auf den restlichen Front-End-Servern in Backup\_ Pool. Führen Sie dazu den folgenden Befehl auf allen Front-End-Servern aus, mit Ausnahme des Servers, den Sie beim Verschieben des zentralen Verwaltungsspeichers zuvor in diesem Verfahren verwendet haben:

        ```console
        Bootstrapper /Setup
        ```

7.  Führen Sie das folgende Cmdlet in einem Skype for Business Server-Shell-Fenster aus, um die Benutzer von Pool1 zu Pool2 zu überlisten:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Da die Schritte in den vorherigen Teilen dieses Verfahrens zum Überprüfen des Status des zentralen Verwaltungsspeichers nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlgeschlagen ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edgepool an diesem Standort so ändern, dass er einen anderen Pool als nächsten Hop verwendet, bevor Sie einen Fehler über den Pool ausführen. Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Failback eines Pools

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Der Failbackvorgang dauert mehrere Minuten. Als Referenz wird erwartet, dass ein Pool von 20.000 Benutzern bis zu 60 Minuten dauert.

Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

Weitere Schritte sind nicht erforderlich. Wenn Sie über den zentralen Verwaltungsserver einen Fehler aufgetreten sind, können Sie ihn in Pool2 belassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Fail over the Edge pool used for Skype for Business Server federation 

Wenn der Edgepool, in dem Sie Skype for Business Server Partnerverbund konfiguriert haben, ausfällt, müssen Sie den Partnerverbund so ändern, dass ein anderer Edgepool verwendet wird, damit der Partnerverbund funktioniert.

1.  Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

3.  Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, den Sie jetzt für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

5.  Wählen Sie **"Aktion**", dann **"Topologie**" und dann " **Veröffentlichen"** aus. Wenn Sie auf **"Topologie veröffentlichen"** aufgefordert werden, wählen Sie **"Weiter**" aus. Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **"Fertig stellen**" aus.

6.  Öffnen Sie auf dem Edgeserver den Skype for Business Server Bereitstellungs-Assistenten. Wählen Sie **"Skype for Business Server System installieren oder aktualisieren**" und dann **"Setup" oder "Skype for Business Server Komponenten entfernen**" aus. Wählen Sie **"Erneut ausführen" aus**.

7.  Wählen Sie **Weiter** aus. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Sobald die Bereitstellung abgeschlossen ist, wählen Sie **"Protokoll anzeigen** " aus, um die verfügbaren Protokolldateien anzuzeigen. Wählen Sie **"Fertig stellen** " aus, um die Bereitstellung abzuschließen.
    
    Wenn die Website, die den fehlgeschlagenen Edgepool enthält, noch ausgeführte Front-End-Server enthält, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst für diese Front-End Pools aktualisieren, um einen Edgepool an einem Remotestandort zu verwenden, der noch ausgeführt wird. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Fail over the Edge pool used for XMPP federation in Skype for Business Server 

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. 

Im folgenden Verfahren ist EdgePool1 der Pool, der ursprünglich den XMPP-Partnerverbund gehostet hat, und EdgePool2 ist der Pool, der jetzt den XMPP-Partnerverbund hostet.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>To fail over the Edge pool used for XMPP federation

1.  Wenn Sie noch keinen anderen Edgepool bereitgestellt haben (neben dem derzeit nicht vorhandenen), stellen Sie diesen Pool bereit. 

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

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Failback des Edgepools, der für Skype for Business Server-Partnerverbund oder XMPP-Partnerverbund verwendet wird 

Nachdem ein fehlgeschlagener Edgepool, der zum Hosten des Partnerverbunds verwendet wurde, wieder online geschaltet wurde, verwenden Sie dieses Verfahren, um die Skype for Business Server Partnerverbundroute und/oder die XMPP-Verbundroute zurückzugeben, um diesen wiederhergestellten Edgepool erneut zu verwenden.

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Wenn Sie die Skype for Business Server Partnerverbundroute zur Verwendung des wiederhergestellten Edgeservers zurücksetzen möchten, gehen Sie folgendermaßen vor:
    
    1. Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
    1. Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
    1. Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserverpool, den Sie erneut für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
    1. Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
    1. Wählen Sie **"Aktion**", dann **"Topologie**" und dann " **Veröffentlichen"** aus. Wenn Sie auf **"Topologie veröffentlichen"** aufgefordert werden, wählen Sie **"Weiter**" aus. Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **"Fertig stellen**" aus.
    
    1. Öffnen Sie auf dem Edgeserver den Skype for Business Server Bereitstellungs-Assistenten. Wählen Sie **"Skype for Business Server System installieren oder aktualisieren**" und dann **"Setup" oder "Skype for Business Server Komponenten entfernen**" aus. Wählen Sie **"Erneut ausführen" aus**.
    
    1. Wählen Sie **Weiter** aus. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Sobald die Bereitstellung abgeschlossen ist, wählen Sie **"Protokoll anzeigen** " aus, um die verfügbaren Protokolldateien anzuzeigen. Wählen Sie **"Fertig stellen** " aus, um die Bereitstellung abzuschließen.

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


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des Einem Front-End-Pool zugeordneten Edgepools

Wenn ein Edgepool ausfällt, aber der Front-End-Pool an demselben Standort noch ausgeführt wird, müssen Sie den Front-End-Pool so konfigurieren, dass er einen Edgepool an einem anderen Standort verwendet, bis der ausgefallene Edgepool wiederhergestellt ist.

1.  Navigieren Sie im Topologie-Generator zum Namen des Front-End-Pools, den Sie ändern möchten.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und wählen Sie dann " **Eigenschaften bearbeiten"** aus.

3.  Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.

4.  Wählen Sie **OK** aus.
