---
title: 'Lync Server 2013: Ausführen eines Failbacks für den Edgepool, der für den Lync Server- oder XMPP-Partnerverbund verwendet wird'
TOCTitle: Ausführen eines Failbacks für den Edgepool, der für den Lync Server- oder XMPP-Partnerverbund verwendet wird
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49890961
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem ein ausgefallener Edgepool, von dem der Partnerverbund gehostet wurde, wieder online geschaltet wurde, führen Sie mit diesem Verfahren ein Failback für die Lync Server-Partnerverbundroute und/oder die XMPP-Partnerverbundroute aus, um den wiederhergestellten Edgepool wiederzuverwenden.

## Ausführen eines Failbacks für den Partnerverbund für einen wiederhergestellten Edgepool

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die Lync Server-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
      - Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edgepools** , und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserver-Pool, der aktuell für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** . Klicken Sie auf **OK** .
    
      - Erweitern Sie **Edgepools** , und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserver-Pool, den Sie wieder für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Aktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** . Klicken Sie auf **OK** .
    
      - Klicken Sie auf **Aktion** , wählen Sie **Topologie** aus, und wählen Sie **Veröffentlichen** aus. Wenn eine entsprechende Eingabeaufforderung angezeigt wird, klicken Sie in **Topologie veröffentlichen** auf **Weiter** . Klicken Sie auf **Fertig stellen** , wenn die Veröffentlichung abgeschlossen ist.
    
      - Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .
    
      - Klicken Sie auf der Seite Lync Server-Komponenten einrichten auf **Weiter** . Im Zusammenfassungsbildschirm werden die ausgeführten Aktionen angezeigt. Nach Abschluss der Bereitstellung klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

3.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die XMPP-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-Partnerverbundroute erneut auf den Edgepool zu verweisen, von dem nun der XMPP-Partnerverbund gehostet wird (in diesem Beispiel EdgeServer1 ):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel ist Site1 der Standort, der den Edgepool enthält, von dem nun die XMPP-Partnerverbundroute gehostet wird. EdgeServer1.contoso.com ist der vollqualifizierte Domänenname (FQDN) eines Edgeservers in diesem Pool.
    
      - Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.
    
      - Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.

4.  Falls die Front-End-Pools weiter an dem Standort ausgeführt werden, der den ausgefallenen und inzwischen wiederhergestellten Edgepool enthält, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End-Pools aktualisieren, sodass wieder die Edgepools am lokalen Standort verwendet werden. Weitere Informationen finden Sie unter [Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Falls der Front-End-Pool am selben Standort wie der ausgefallene Edgepool ebenfalls ausgefallen ist, können Sie nun mit Invoke-CsPoolFailback ein Failback auf den Front-End-Pool ausführen.

## Siehe auch

#### Aufgaben

[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  

#### Konzepte

[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

