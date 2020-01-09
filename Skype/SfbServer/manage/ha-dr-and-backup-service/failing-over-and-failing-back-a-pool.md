---
title: Ausführen von Failover und Failback für einen Pool
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991800"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Fehler beim Failover und Zurücksetzen eines Pools in Skype for Business Server 

Führen Sie die folgenden Verfahren aus, wenn ein einzelner Front-End-Pool fehlerhaft ist und ein Failover durchgeführt werden muss, oder wenn der Pool, in dem der Notfall aufgetreten ist, wieder online ist und Sie Ihre Bereitstellung auf normalen Arbeitsstatus wiederherstellen müssen. Sie erfahren außerdem, wie Sie den für Skype for Business Federation oder XMPP Federation verwendeten Edge-Pool für Failover und Failback zurücksetzen oder den Edge-Pool ändern, der einem Front-End-Pool zugeordnet ist.

- [Failover eines Front-End-Pools](#fail-over-a-front-end-pool)
- [Zurücksetzen eines Pools](#fail-back-a-pool)
- [Failover des für den Skype for Business Server-Verbund verwendeten Edge-Pools](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Failover des für die XMPP-Föderation verwendeten Edge-Pools in Skype for Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Zurücksetzen des Edge-Pools, der für Skype for Business Server Federation oder XMPP Federation verwendet wird](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Ändern des Edge-Pools, der einem Front-End-Pool zugeordnet ist](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Failover eines Front-End-Pools

In diesem Verfahren enthält Datacenter1 pool1, und pool1 ist fehlgeschlagen. Sie haben einen Failover zu Pool2 befindet sich in Datacenter2.

Der größte Teil der Arbeit für das Pool-Failover umfasst einen Failover des zentralen Verwaltungsspeichers, falls dies erforderlich ist. Dies ist wichtig, da der zentrale Verwaltungsspeicher funktionsfähig sein muss, wenn die Benutzer des Pools fehlerhaft sind.

Wenn ein Front-End-Pool fehlschlägt, der Edge-Pool an dieser Website jedoch weiterhin ausgeführt wird, müssen Sie wissen, ob der Edge-Pool den fehlerhaften Pool als nächsten Hop-Pool verwendet. Wenn dies der Fall ist, müssen Sie den Edge-Pool so ändern, dass ein anderer Front-End-Pool verwendet wird, bevor der fehlerhafte Front-End-Pool fehlschlägt. Wie Sie die Einstellung für den nächsten Hop ändern, hängt davon ab, ob der Edge-Pool am gleichen Standort wie der Edge-Pool oder auf einer anderen Website verwendet wird.

**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools auf derselben Website ein**

1.  Öffnen Sie den Topologie-Generator, klicken Sie mit der rechten Maustaste auf den zu ändernden Edge-Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Klicken Sie auf **Nächster Hop**. Wählen Sie in der Liste **Nächster Hop-Pool:** den Pool aus, der nun als nächster Hop-Pool fungieren soll.

3.  Klicken Sie auf **OK**, und veröffentlichen Sie die Änderungen.

**So stellen Sie einen Edge-Pool für die Verwendung eines Next Hop-Pools an einer anderen Website ein**

1.  Öffnen Sie ein Skype for Business Server-Verwaltungsshell-Fenster, und geben Sie das folgende Cmdlet ein:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**So führen Sie einen Failover eines Pools in einem Notfall durch**

1.  Ermitteln Sie, welcher Pool der Host für den zentralen Verwaltungsserver ist, indem Sie das folgende Cmdlet auf einem Front-End-Server in Pool2 eingeben:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Die Ergebnisse dieses Cmdlets zeigen, in welchem Pool zurzeit der zentrale Verwaltungs Server gehostet wird. Im weiteren Verlauf dieses Verfahrens wird dieser Pool als "CMS\_-Pool" bezeichnet.

2.  Verwenden Sie den Topologie-Generator, um die Version von Skype for Business Server zu\_finden, die im CMS-Pool ausgeführt wird. Wenn Skype for Business Server ausgeführt wird, verwenden Sie das folgende Cmdlet, um den Sicherungspool von Pool 1 zu finden.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Lassen Sie\_den Backup-Pool zum Backup-Pool werden.

3.  Überprüfen Sie den Status des zentralen Verwaltungsspeichers mit dem folgenden Cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Dieses Cmdlet sollte anzeigen, dass sowohl ActiveMasterFQDN als auch ActiveFileTransferAgents auf den FQDN des CMS\_-Pools verweisen. Wenn Sie leer sind, steht der zentrale Verwaltungs Server nicht zur Verfügung, und Sie müssen einen Failover durchführen.

4.  Wenn der zentrale Verwaltungsspeicher nicht verfügbar ist oder wenn der zentrale Verwaltungsspeicher auf pool1 ausgeführt wurde (also der Pool, bei dem ein Fehler aufgetreten ist), müssen Sie vor dem Failover des Pools einen Failover für den zentralen Verwaltungs Server durchführen. Wenn Sie einen Failover für den zentralen Verwaltungs Server durchführen müssen, der in einem Pool mit Skype for Business Server gehostet wurde, verwenden Sie das Cmdlet in Schritt 5 dieses Verfahrens. Wenn Sie keinen Failover für den zentralen Verwaltungs Server benötigen, fahren Sie mit Schritt 7 dieses Verfahrens fort.

5.  Gehen Sie wie folgt vor, um einen Failover des zentralen Verwaltungsspeichers in einem Pool mit Skype for Business Server auszuführen:
    
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
        ```PowerShell
         
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

7.  Führen Sie einen Failover der Benutzer von pool1 zu Pool2 durch, indem Sie das folgende Cmdlet in einem Skype for Business Server-Verwaltungsshell-Fenster ausführen:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Da die Schritte, die in den vorherigen Abschnitten dieses Verfahrens zur Überprüfung des Status des zentralen Verwaltungsspeichers durchgeführt wurden, nicht universell sind, besteht weiterhin die Möglichkeit, dass dieses Cmdlet fehlschlägt, da der zentrale Verwaltungsspeicher noch nicht vollständig fehlerhaft ist. In diesem Fall müssen Sie den zentralen Verwaltungsspeicher basierend auf den angezeigten Fehlermeldungen korrigieren und dieses Cmdlet dann erneut ausführen.
    
    Wenn die folgende Fehlermeldung angezeigt wird, müssen Sie den Edge-Pool auf dieser Website ändern, um einen anderen Pool als nächsten Hop zu verwenden, bevor Sie einen Failover für den Pool durchführen. Ausführliche Informationen finden Sie in den Verfahren am Anfang dieses Themas.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Zurücksetzen eines Pools

Nachdem der Pool, der das Desaster erlebt hat, wieder online ist (also pool1 in diesem Beispiel), führen Sie die folgenden Schritte aus, um die Bereitstellung auf normalen Arbeitsstatus wiederherzustellen.

Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.

Führen Sie einen Failback für die Benutzer durch, die sich ursprünglich in pool1 begeben haben, und Sie haben ein Failover auf Pool2 durchgeführt, indem Sie das folgende Cmdlet eingegeben haben:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Es sind keine weiteren Schritte erforderlich. Wenn Sie einen Fehler über den zentralen Verwaltungs Server ausgeführt haben, können Sie ihn in Pool2 belassen.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Failover des für den Skype for Business Server-Verbund verwendeten Edge-Pools 

Wenn der Edge-Pool, in dem Sie die Skype for Business Server-Föderation konfiguriert haben, ausfällt, müssen Sie die Föderation so ändern, dass ein anderer Edge-Pool für den Verbund verwendet wird.

1.  Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edge-Server oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**aus.

2.  Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

3.  Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edge-Server oder den Edgeserver-Pool, den Sie jetzt für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**aus.

4.  Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus. Klicken Sie auf **OK**.

5.  Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.

6.  Öffnen Sie auf dem Edgeserver den Assistenten für die Bereitstellung von Skype for Business Server. Klicken Sie auf **Skype for Business Server-System installieren oder aktualisieren**, und klicken Sie dann auf **Setup oder Entfernen von Skype for Business Server-Komponenten**. Klicken Sie **erneut auf Ausführen**.

7.  Klicken Sie auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.
    
    Wenn die Website mit dem fehlerhaften Edge-Pool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um einen Edge-Pool in einer noch ausgeführten Remotewebsite zu verwenden. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Failover des für die XMPP-Föderation verwendeten Edge-Pools in Skype for Business Server 

In Ihrer Organisation gibt es einen Edge-Pool, der als Pool für XMPP-Föderationen verwendet wird. Wenn dieser Pool ausfällt, müssen Sie die XMPP-Föderation nicht verwenden, um einen anderen Edge-Pool zu verwenden, bevor die XMPP-Föderation wieder funktionieren kann.

Wenn Sie Edge-Pools zum ersten Mal installieren und die XMPP-Föderation aktivieren, können Sie den Disaster Recovery-Prozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP Federation einrichten, und nicht nur eine. Jeder dieser SRV-Einträge muss einen anderen Prioritäts Satz aufweisen. Der gesamte XMPP-Verbunddatenverkehr durchläuft den Pool mit dem SRV-Eintrag mit der höchsten Priorität. 

In der folgenden Vorgehensweise ist EdgePool1 der Pool, in dem die XMPP-Föderation ursprünglich gehostet wurde, und EdgePool2 ist der Pool, der nun XMPP-Föderation hostet.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>So führen Sie einen Failover des für die XMPP-Föderation verwendeten Edge-Pools aus

1.  Wenn Sie noch keinen anderen Edge-Pool bereitgestellt haben (außer dem, der zurzeit nicht vorhanden ist), stellen Sie diesen Pool bereit. 

2.  Führen Sie auf jedem Edgeserver des neuen Edge-Pools, in dem nun XMPP Federation (EdgePool2) gehostet wird, das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route auf EdgePool2 zu verweisen:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel ist site2 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeserver in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.

5.  Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.
    
        _xmpp-server._tcp.contoso.com

6.  Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.

7.  Starten Sie die Dienste auf allen Edgeserver im Edge-Pool, die nun die XMPP-Föderation hosten:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Zurücksetzen des Edge-Pools, der für Skype for Business Server Federation oder XMPP Federation verwendet wird 

Nachdem ein ausgefallener Edge-Pool, der zum Hosten der Föderation verwendet wurde, wieder online geschaltet wurde, verwenden Sie dieses Verfahren zum Zurücksetzen der Skype for Business Server-Föderations Route und/oder der XMPP-Föderations Route, um diesen wiederhergestellten Edge-Pool erneut zu verwenden.

1.  Starten Sie in dem jetzt wieder verfügbaren Edge-Pool die Edge-Dienste.

2.  Wenn Sie die Skype for Business Server-Föderations Route für die Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten, gehen Sie folgendermaßen vor:
    
      - Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**aus.
    
      - Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edge-Server oder den Edgeserver-Pool, den Sie erneut für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**aus.
    
      - Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus. Klicken Sie auf **OK**.
    
      - Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
      - Öffnen Sie auf dem Edgeserver den Assistenten für die Bereitstellung von Skype for Business Server. Klicken Sie auf **Skype for Business Server-System installieren oder aktualisieren**, und klicken Sie dann auf **Setup oder Entfernen von Skype for Business Server-Komponenten**. Klicken Sie **erneut auf Ausführen**.
    
      - Klicken Sie auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

3.  Gehen Sie wie folgt vor, wenn Sie die XMPP-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route an den Edge-Pool zu verweisen, der nun XMPP-Föderation hostet (in diesem Beispiel EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel ist site1 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeserver in diesem Pool.
    
      - Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.
    
      - Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.

4.  Wenn die Front-End-Pools weiterhin auf der Website mit dem fehlerhaften Edge-Pool ausgeführt wurden und wiederhergestellt wurden, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um die Edge-Pools auf der lokalen Website erneut zu verwenden.

5.  Wenn der Front-End-Pool am gleichen Standort wie der fehlerhafte Edge-Pool ebenfalls fehlgeschlagen ist, können Sie jetzt Invoke – CsPoolFailback verwenden, um den Front-End-Pool zurückzukehren.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Ändern des Edge-Pools, der einem Front-End-Pool zugeordnet ist

Wenn ein Edge-Pool ausfällt, der Front-End-Pool am gleichen Standort aber noch ausgeführt wird, müssen Sie den Front-End-Pool so einrichten, dass ein Edge-Pool an einer anderen Website verwendet wird, bis der fehlerhafte Edge-Pool wiederhergestellt wird.

1.  Navigieren Sie im Topologie-Generator zu dem Namen des Front-End-Pools, den Sie ändern müssen.

2.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

3.  Verwenden Sie im Abschnitt **Zuordnungen** unter **Edge-Pool zuordnen (für Medienkomponenten)** das Dropdownfeld, um den Edge-Pool auszuwählen, dem Sie diesen Front-End-Pool zuordnen möchten.

4.  Klicken Sie anschließend auf **OK**.
