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
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278675"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Führen Sie ein Failing over und ein Failing Back für einen Pool in Skype for Business Server aus.

Führen Sie die folgenden Verfahren aus, wenn ein einzelner Front-End-Pool fehlgeschlagen ist und ein Fehler durchgeführt werden muss, oder der Pool, bei dem das Notfall auftstand, wieder online ist und Sie den normalen Betriebsstatus der Bereitstellung wiederherstellen müssen. Erfahren Sie, wie Sie ein Failover für den Edgepool, der für den Skype for Business- oder den XMPP-Verbund verwendet wird, oder den Edgepool ändern, der einem Front-End wird.

- [Failover eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Fail back a pool](#fail-back-a-pool)
- [Failover des Edgepools, der für den Skype for Business Server-Verbund verwendet wird](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover des Edgepools, der für den XMPP-Verbund in Skype for Business Server verwendet wird](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Fail back the Edge pool used for Skype for Business Server federation or XMPP federation](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des Edgepools, der einem Front-End-Pool zugeordnet ist](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover eines Front-End Pools

"Datacenter1" enthält "Pool1", und "Pool1" ist fehlgeschlagen. Sie müssen einen Fehler auf "Pool2" in "Datacenter2" ausf?en.

Der Großteil der Arbeit für das Poolfailover umfasst bei Bedarf ein Failover des zentralen Verwaltungsspeichers. Der zentrale Verwaltungsspeicher muss funktionsfähig sein, wenn für die Benutzer des Pools ein Fehler auftrat.

Wenn ein Front-End ausfällt, der Edgepool an diesem Standort jedoch noch ausgeführt wird, müssen Sie wissen, ob der ausgefallene Pool vom Edgepool als nächster Hoppool verwendet wird. Wenn dies der Fehler ist, müssen Sie den Edgepool so ändern, dass er einen anderen Front-End verwendet, bevor ein Fehler beim Front-End wird. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge einen Pool am selben Standort wie der Edgepool oder einen anderen Standort verwendet.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools am gleichen Standort**

1. Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den Edgepool, der geändert werden muss, und wählen Sie **"Eigenschaften bearbeiten" aus.**

2. Wählen Sie **"Nächster Hop" aus.** Wählen Sie **in der Liste "Nächster Hoppool:** " den Pool aus, der jetzt als nächster Hoppool dienen soll.

3. Wählen Sie **"OK"** aus, und veröffentlichen Sie die Änderungen.

**So legen Sie einen Edgepool für die Verwendung eines nächsten Hoppools an einem anderen Standort**

1. Öffnen Sie ein Skype for Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**So führen Sie ein Failover eines Pools in einem Notfall durch**

1. Suchen Sie den Hostpool für den zentralen Verwaltungsserver, indem Sie das folgende Cmdlet auf einem Front-End in Pool2 eingeben:

        Invoke-CsManagementServerFailover -Whatif

    Die Ergebnisse dieses Cmdlets zeigen, welcher Pool derzeit den zentralen Verwaltungsserver hostet. Im restlichen Verfahren wird dieser Pool als "CMS-Pool" \_ bezeichnet.

2. Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu finden, die im CMS Pool \_ ausgeführt wird. Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu suchen.

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    Der \_ Sicherungspool soll der Sicherungspool sein.

3. Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    Dieses Cmdlet sollte zeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS-Pools \_ zeigen. Wenn sie leer sind, ist der zentrale Verwaltungsserver nicht verfügbar, und Sie müssen ein Failover des Servers starten.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder der zentrale Verwaltungsspeicher in Pool1 ausgeführt wurde (d. h. der ausgefallene Pool), müssen Sie ein Failover des zentralen Verwaltungsservers ausführen, bevor Sie ein Failover des Pools ausführen. Wenn Sie ein Failover des zentralen Verwaltungsservers ausführen müssen, der in einem Pool mit Skype for Business Server gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn kein Failover des zentralen Verwaltungsservers erforderlich ist, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Gehen Sie wie folgt vor, um ein Failover für den zentralen Verwaltungsspeicher in einem Pool mit Skype for Business Server zu erstellen:

      - Überprüfen Sie zunächst, Back-End server im Sicherungspool die Prinzipalinstanz des zentralen Verwaltungsspeichers ausgeführt wird, indem Sie \_ Folgendes eingeben:

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Wenn der primäre Back-End im \_ Sicherungspool der Prinzipal ist, geben Sie Denktyp ein:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Wenn der Spiegelserver Back-End Im \_ Sicherungspool der Prinzipal ist, geben Sie Denktyp ein:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Überprüfen Sie, ob das Failover des zentralen Verwaltungsservers abgeschlossen ist. Geben Sie den folgenden Befehl ein:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Überprüfen Sie, ob sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des Sicherungspools \_ zeigen.
    
      - Überprüfen Sie abschließend den Replikatstatus für alle Front-End Server, indem Sie Folgendes eingeben:
        
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
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edgepool an diesem Standort so ändern, dass ein anderer Pool als nächster Hop verwendet wird, bevor Ein Fehler im Pool verursacht werden. Weitere Informationen finden Sie in den Verfahren zu Beginn dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Fail back a pool

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Der Failbackprozess dauert mehrere Minuten. Als Referenz wird erwartet, dass es bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten dauert.

Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Weitere Schritte sind nicht erforderlich. Wenn ein Fehler auf dem zentralen Verwaltungsserver auftrat, können Sie ihn in Pool2 be lassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover des Edgepools, der für den Skype for Business Server-Verbund verwendet wird 

Wenn der Edgepool, für den Sie den Skype for Business Server-Verbund konfiguriert haben, aus dem Aus ist, müssen Sie den Verbund so ändern, dass er einen anderen Edgepool verwendet, damit der Verbund funktioniert.

1.  Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

3.  Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, den Sie jetzt für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.

5.  Select **Action**, select **Topology**, select **Publish**. Wenn Sie zum Veröffentlichen **der Topologie aufgefordert werden,** wählen Sie **"Weiter" aus.** Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **"Fertig stellen" aus.**

6.  Öffnen Sie auf dem Edgeserver den Skype for Business Server-Bereitstellungs-Assistenten. Wählen **Sie "Skype for Business Server System** installieren oder aktualisieren" und dann "Skype for Business Server-Komponenten einrichten oder **entfernen" aus.** Select **Run Again**.

7.  Wählen Sie **Weiter**. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Sobald die Bereitstellung erfolgt ist, wählen **Sie "Protokoll anzeigen" aus,** um die verfügbaren Protokolldateien zu sehen. Wählen Sie **"Fertig** stellen" aus, um die Bereitstellung fertig zu stellen.
    
    Wenn der Standort mit dem ausgefallenen Edgepool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools so aktualisieren, dass ein Edgepool an einem Remotestandort verwendet wird, der noch ausgeführt wird. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover des Edgepools, der für den XMPP-Verbund in Skype for Business Server verwendet wird 

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. 

Im folgenden Verfahren ist EdgePool1 der Pool, der ursprünglich den XMPP-Verbund gehostet hat, und EdgePool2 ist der Pool, der jetzt den XMPP-Verbund hosten wird.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>So führen Sie ein Failover des Edgepools durch, der für den XMPP-Verbund verwendet wird

1.  Wenn Sie noch keinen anderen Edgepool bereitgestellt haben (neben dem, der derzeit nicht vorhanden ist), stellen Sie den Pool zur Verfügung. 

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

Nachdem ein ausgefallener Edgepool, der zum Hosten des Verbunds verwendet wurde, wieder online geschaltet wurde, führen Sie dieses Verfahren aus, um ein Fail back für die Skype for Business Server-Verbundroute und/oder die XMPP-Verbundroute zur erneuten Verwendung dieses wiederhergestellten Edgepools zu erstellen.

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Wenn Sie ein Fail back der Skype for Business Server-Verbundroute für die Verwendung des wiederhergestellten Edgeservers wünschen, gehen Sie wie folgt vor:
    
      - Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
      - Erweitern **Sie Edgepools,** und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserverpool, den Sie erneut für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Wählen Sie **OK** aus.
    
      - Select **Action**, select **Topology**, select **Publish**. Wenn Sie zum Veröffentlichen **der Topologie aufgefordert werden,** wählen Sie **"Weiter" aus.** Wenn die Veröffentlichung abgeschlossen ist, wählen Sie **"Fertig stellen" aus.**
    
      - Öffnen Sie auf dem Edgeserver den Skype for Business Server-Bereitstellungs-Assistenten. Wählen **Sie "Skype for Business Server System** installieren oder aktualisieren" und dann "Skype for Business Server-Komponenten einrichten oder **entfernen" aus.** Select **Run Again**.
    
      - Wählen Sie **Weiter**. Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Sobald die Bereitstellung erfolgt ist, wählen **Sie "Protokoll anzeigen" aus,** um die verfügbaren Protokolldateien zu sehen. Wählen Sie **"Fertig** stellen" aus, um die Bereitstellung fertig zu stellen.

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

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und wählen Sie dann **"Eigenschaften bearbeiten" aus.**

3.  Wählen Sie im Abschnitt **Zuordnungen** unter **Edgepool zuordnen (für Medienkomponenten)** im Dropdownfeld den Edgepool aus, den Sie diesem Front-End-Pool zuordnen möchten.

4.  Wählen Sie **OK** aus.
