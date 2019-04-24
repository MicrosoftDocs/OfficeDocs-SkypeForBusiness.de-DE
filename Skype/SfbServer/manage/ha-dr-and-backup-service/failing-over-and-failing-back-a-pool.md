---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197800"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Stets über, ansonsten einen Pool in Skype für Business Server 

Gehen Sie folgendermaßen vor, wenn ein einzelner Front-End-Pool ist fehlgeschlagen und muss ein Failover oder den Pool, der ausgefallenen wieder online ist und Sie für reguläre Arbeitsstatus Ihrer Bereitstellung wiederherstellen müssen. Auch hier erfahren Sie, wie Sie ein Failover und Failback für den Edge-Pool für Skype für Business verbunden oder XMPP-Verbund verwendet, oder ändern Sie den Edge-Pool einen Front-End-Pool zugeordnet.

- [Ausführen eines Failovers eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Führen einen Sie Failback eines Pools](#fail-back-a-pool)
- [Ein Failover des edgepools für Skype für den Verbund Business Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Ein Failover des edgepools für XMPP-Verbund in Skype für Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Failover des edgepools für Skype für Business Server- oder XMPP-Verbund](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des Edge-Pools einen Front-End-Pool zugeordnet](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Ausführen eines Failovers eines Front-End-Pools

In diesem Verfahren Datacenter1 enthält Pool1 und Pool1 ist fehlgeschlagen. Sie sind auf Pool2 befindet sich im Datacenter2 Failovervorgängen.

Die meisten Aufgaben für den poolfailover umfasst Failover des zentralen Verwaltungsspeichers, wenn es erforderlich ist. Dies ist wichtig, da des zentralen Verwaltungsspeichers funktionsfähig sein muss, wenn die Benutzer des Pools ein Failover ausgeführt werden.

Darüber hinaus muss bei ein Front-End-Pool Fehler auftreten, aber der Edge-Pool an diesem Standort weiterhin ausgeführt wird, wissen, ob der Edge-Pool den ausgefallenen Pool als nächsten hoppool verwendet wird. Wenn dies der Fall ist, müssen Sie einen anderen Front-End-Pool vor dem über den fehlerhaften Front-End-Pool verwenden, um den Edge-Pool ändern. Ändern Sie die Einstellung der nächste Hop, hängt davon ab, ob der Rand einen Pool am selben Standort befinden wie der Edge-Pool oder einem anderen Standort verwendet werden.

**Festlegen ein Edge-Pools einen nächsten hoppool am selben Standort verwenden**

1.  Öffnen Sie den Topologie-Generator rechten Maustaste auf den Edge-Pool, der geändert werden soll, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Klicken Sie auf **Nächster Hop**. Aus der **Nächster hoppool:** , wählen Sie den Pool der jetzt als den nächsten hoppool dienen soll.

3.  Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.

**Festlegen ein Edge-Pools einen nächsten hoppool an einem anderen Standort verwenden**

1.  Öffnen Sie einen Skype für Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Failover eines Pools im Notfall**

1.  Suchen Sie nach dem Pool den Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse der dieses Cmdlet anzeigen, welcher Pool den zentralen Verwaltungsserver derzeit gehostet wird. Die restlichen Schritte dieses Verfahrens in diesem Pool wird CMS genannt\_Pool.

2.  Topologie-Generator verwenden, um die Version von Skype für Business Server, auf dem zentralen Verwaltungsspeicher finden\_Pool. Wenn es Skype für Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool Pool 1 suchen.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Lassen Sie Sicherung\_Pool den Sicherungspool ausgeführt werden.

3.  Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte angezeigt werden, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" mit dem FQDN des CMS zeigen\_Pool. Wenn sie leer sind, den zentralen Verwaltungsserver ist nicht verfügbar, und Sie müssen Sie als ein Failover.

4.  Wenn Sie der zentralen Verwaltungsspeicher nicht verfügbar ist oder des zentralen Verwaltungsspeichers auf Pool1 ausgeführt wurde (d. h., den Pool, der ein Fehler aufgetreten ist), müssen Sie den zentralen Verwaltungsserver vor dem Failover, über den Pool. Wenn Sie den zentralen Verwaltungsserver Failover, die in einem Pool mit Skype für Business Server gehostet wurde müssen, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie nicht den zentralen Verwaltungsserver Failover müssen, fahren Sie mit Schritt 7 fortfahren.

5.  Gehen Sie wie folgt vor, um das Failover des zentralen Verwaltungsspeichers in einem Pool mit Skype für Business Server:
    
      - Überprüfen Sie zunächst, welche Back End-Server in Sicherung\_Pool führt die Prinzipalinstanz des zentralen Verwaltungsspeichers, indem Sie Folgendes eingeben:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back End-Server in Sicherung\_Pool ist der Prinzipal, Typ:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegel-Back-End-Server in Sicherung\_Pool ist der Prinzipal, Typ:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, dass das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie Folgendes ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" auf die FQDN Sicherung zeigen\_Pool.
    
      - Überprüfen Sie abschließend den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, dass alle Replikate den Wert True haben.
        
        Fahren Sie mit Schritt 7 in diesem Verfahren fort.

6.  Installieren Sie den zentralen Verwaltungsspeicher auf der Back-End Server des\_Pool.
    
      - Führen Sie zuerst den folgenden Befehl aus:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Führen den nächsten Befehl auf einem der Front-End-Server der Sicherung\_Pool verschieben des zentralen Verwaltungsspeichers erzwingen:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Überprüfen Sie die Verschiebung abgeschlossen ist:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, dass sowohl "ActiveMasterFQDN" auch "activefiletransferagents" auf die FQDN Sicherung zeigen\_Pool.
    
      - Überprüfen Sie den Replikatstatus für alle Front-End-Server, indem Sie Folgendes eingeben:
        
            Get-CsManagementStoreReplicationStatus 
        
        Überprüfen Sie, dass alle Replikate den Wert True haben.
    
      - Installieren Sie den zentralen Verwaltungsserver-Dienst auf den Rest der Front-End-Server in Sicherung\_Pool. Zu diesem Zweck führen Sie den folgenden Befehl auf allen Front-End-Servern, mit Ausnahme des, mit dem Erzwingen der zentralen Speicher weiter oben in diesem Verfahren verschieben:
        
            Bootstrapper /Setup 

7.  Ausführen eines Failovers der Benutzer von Pool1 zu Pool2, indem Sie das folgende Cmdlet in einen Skype für Business Server-Verwaltungsshell-Fenster ausführen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die Schritte in den vorherigen Teilen dieses Verfahrens zum Überprüfen des Status des zentralen Speicher nicht universelle sind, ist weiterhin eine Möglichkeit, die dieses Cmdlet schlägt fehl, da es sich bei der zentralen Verwaltungsspeicher nicht noch vollständig Failover ausgeführt wird. In diesem Fall müssen Sie beheben des zentralen Verwaltungsspeichers basierend auf Fehlermeldungen, die Sie sehen, und führen Sie dieses Cmdlet erneut aus.
    
    Wenn Sie die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool an diesem Standort für die Verwendung von eines anderen Pools als nächsten Hop vor dem über den Pool zu ändern. Weitere Informationen hierzu finden Sie die Verfahren am Anfang dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Führen einen Sie Failback eines Pools

Nachdem der Pool, der ausgefallenen wieder online ist (d. h., in diesem Beispiel Pool1), gehen Sie folgendermaßen vor Ihrer Bereitstellung in reguläre Arbeitsstatus wiederherstellen.

Beachten Sie, dass der Failback-Prozess einige Zeit in.Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.

Failback der Benutzer, die wurden die ursprünglich in Pool1 verwaltet und wurde Failover durchgeführt wurde Pool2 durch das folgende Cmdlet eingeben:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Es sind keine weiteren Schritte erforderlich. Wenn Sie über den zentralen Verwaltungsserver ausgefallen ist, können Sie es in Pool2 lassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Ein Failover des edgepools für Skype für den Verbund Business Server 

Wenn der Edge-Pool, in dem Sie Skype für Business Server den Verbund konfiguriert haben, ausfällt, müssen Sie den Verbund verwenden einen anderen edgepool für den Verbund für die Arbeit ändern.

1.  Öffnen Sie auf einem Front-End-Server-Topologie-Generator. Erweitern Sie **edgepools**, und klicken Sie dann die mit der rechten Maustaste die Edge-Server oder Edge-Server-Pool, der aktuell für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**.

2.  **Bearbeiten von Eigenschaften** unter **Allgemein**deaktivieren Sie **aktivieren den Verbund für diesen edgepool (Port 5061)**. Klicken Sie auf **OK**.

3.  Erweitern Sie **edgepools**, und klicken Sie dann die mit der rechten Maustaste die Edge-Server oder Pool für Edge-Server, die Sie nun für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**.

4.  **Eigenschaften bearbeiten** unter **Allgemein**die Option **Partnerverbund für diesen edgepool (Port 5061) aktivieren**. Klicken Sie auf **OK**.

5.  Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, wählen Sie **Veröffentlichen**aus. **Veröffentlichen der Topologie**auf dazu aufgefordert werden, klicken Sie auf **Weiter**. Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf **Fertig stellen**.

6.  Öffnen Sie auf dem Edgeserver der Skype für Business Server-Bereitstellungs-Assistenten. Klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, und klicken Sie dann auf **einrichten oder Entfernen von Skype für Business Server-Komponenten**. Klicken Sie auf **erneut ausführen**.

7.  Klicken Sie auf **Weiter**. Im Fenster Zusammenfassung anzeigen die Aktionen, wie diese ausgeführt werden. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.
    
    Wenn die Website mit der ausgefallene edgepool Front-End-Server, der noch ausgeführt werden enthält, müssen Sie aktualisieren die Webkonferenzdienst und A / V-Konferenzdienst auf diesen Front-End-Pools verwenden ein Edge-Pools in einer site also weiterhin ausgeführt. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Ein Failover des edgepools für XMPP-Verbund in Skype für Business Server 

In Ihrer Organisation müssen Sie ein Edge-Pool als den Pool für XMPP-Verbund zu verwendenden vorhanden ist. Wenn dieser Pool ausfällt, müssen Sie ein Failover XMPP-Verbund auf einen anderen edgepool verwenden, bevor XMPP-Verbund erneut arbeiten kann.

Wenn Sie zuerst installieren von Edge-Pools und XMPP-Partnerverbund aktivieren, können Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP-Verbund, statt nur einem Einrichten der Wiederherstellung vereinfachen. Jedem dieser SRV-Datensätze muss eine andere Priorität festgelegt werden. Alle XMPP-Verbund-Datenverkehr wird über den Pool mit der SRV-Eintrag mit der höchsten Priorität. 

In der folgenden Prozedur EdgePool1 den Pool der XMPP-Verbund ursprünglich gehostet wird, und EdgePool2 ist der Pool, der XMPP-Verbund jetzt gehostet wird.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Failover des edgepools für XMPP-Verbund

1.  Wenn Sie noch nicht bereitgestellt (außer derjenigen, die derzeit ausgefallen ist), einen anderen edgepool diesen Pool bereitstellen. 

2.  Führen Sie auf jedem Edgeserver im neuen edgepool, der nun der XMPP-Verbund (EdgePool2) gehostet wird das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie die XMPP-partnerverbundroute auf EdgePool2 zu verweisen, das folgende Cmdlet aus:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel Site2 ist die Website mit der Edge-Pool, der nun die XMPP-partnerverbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Verbund auf EdgeServer2.contoso.com verweist.

5.  Wenn Sie bereits einen DNS-SRV-Eintrag für XMPP-Verbund keinen der in der Edge-Pool dem XMPP-Verbund jetzt gehostet wird, aufgelöst wird, müssen Sie, wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert 5269 haben.
    
        _xmpp-server._tcp.contoso.com

6.  Stellen Sie sicher, dass der Edge-Pool, der XMPP-Verbund jetzt gehostet wird Port 5269 open extern ist.

7.  Starten Sie die Dienste auf allen Edge-Servern in der Edge-Pool, der XMPP-Verbund jetzt gehostet wird:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Failover des edgepools für Skype für Business Server- oder XMPP-Verbund 

Nach einer fehlerhaften Kante Pool, mit dem Host Verbund gebracht worden wieder online, die mit diesem Verfahren können Sie ein Failback der Skype für partnerverbundroute Business Server und/oder die XMPP-partnerverbundroute, um diesen wiederhergestellten edgepool erneut zu verwenden.

1.  Starten Sie auf den Edge-Pool, der nun wieder verfügbar ist, die Edgedienste.

2.  Wenn Sie ein Failback der Skype für partnerverbundroute Business Server um den wiederhergestellten Edgeserver zu verwenden möchten, führen Sie folgende Schritte aus:
    
      - Öffnen Sie auf einem Front-End-Server-Topologie-Generator. Erweitern Sie die **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder Edge-Server-Pool, der aktuell für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**.
    
      - **Bearbeiten von Eigenschaften** unter **Allgemein**deaktivieren Sie **aktivieren den Verbund für diesen edgepool (Port 5061)**. Klicken Sie auf **OK**.
    
      - Erweitern Sie die **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den ursprünglichen Edgeserver oder edgeserverpool, den Sie erneut für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**.
    
      - **Eigenschaften bearbeiten** unter **Allgemein**die Option **Partnerverbund für diesen edgepool (Port 5061) aktivieren**. Klicken Sie auf **OK**.
    
      - Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, wählen Sie **Veröffentlichen**aus. **Veröffentlichen der Topologie**auf dazu aufgefordert werden, klicken Sie auf **Weiter**. Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
      - Öffnen Sie auf dem Edgeserver der Skype für Business Server-Bereitstellungs-Assistenten. Klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**und dann auf **einrichten oder Entfernen von Skype für Business Server-Komponenten**. Klicken Sie auf **erneut ausführen**.
    
      - Klicken Sie auf **Weiter**. Im Fenster Zusammenfassung anzeigen die Aktionen, wie diese ausgeführt werden. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

3.  Wenn Sie das Failback für der XMPP-partnerverbundroute, um den wiederhergestellten Edgeserver zu verwenden möchten, führen Sie folgende Schritte aus:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-partnerverbundroute an den Edge-Pool verweisen, von dem nun der XMPP-Verbund (in diesem Beispiel EdgeServer1) gehostet wird:
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel Site1 ist die Website mit der Edge-Pool, der nun die XMPP-partnerverbundroute gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeservers in diesem Pool.
    
      - Wenn Sie bereits einen DNS-SRV-Eintrag für XMPP-Verbund keinen der in der Edge-Pool dem XMPP-Verbund jetzt gehostet wird, aufgelöst wird, müssen Sie, wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert 5269 haben.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Verbund auf EdgeServer2.contoso.com verweist.
    
      - Stellen Sie sicher, dass der Edge-Pool, der XMPP-Verbund jetzt gehostet wird Port 5269 open extern ist.

4.  Wenn der Front-End-Pools in die Website mit der Edge-Pool, die wiederhergestellt wurde nicht erfolgreich ausgeführt wird blieb, sollten Sie aktualisieren die Webkonferenzdienst und A / V-Konferenzdienst auf diesen Front-End-pools erneut verwenden die Edge-Pools in ihrer lokalen Website.

5.  Wenn Sie der Front-End-Pool am selben Standort wie der ausgefallene edgepool ebenfalls ausgefallen ist, können Sie jetzt Invoke – CsPoolFailback Failback für den Front-End-Pool verwenden.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des Edge-Pools einen Front-End-Pool zugeordnet

Wenn Sie ein edgepool ausfällt, jedoch der Front-End-Pool am selben Standort weiterhin ausgeführt wird, müssen Sie den Front-End-Pool einen edgepool an einem anderen Standort verwenden, bis der ausgefallene edgepool wiederhergestellt wird festgelegt.

1.  Navigieren Sie im Topologie-Generator auf den Namen des Front-End-Pools, den Sie ändern möchten.

2.  Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Verwenden Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** das Dropdown-Feld den Edge-Pool wählen, dem Sie diese Front-End-Pool zuordnen möchten.

4.  Klicken Sie anschließend auf **OK**.
