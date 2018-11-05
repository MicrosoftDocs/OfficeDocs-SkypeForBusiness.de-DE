---
title: 'Lync Server 2013: Ausführen eines Failovers für den Edgepool, der für den Lync Server-Partnerverbund verwendet wird'
TOCTitle: Ausführen eines Failovers für den Edgepool, der für den Lync Server-Partnerverbund verwendet wird
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49890764
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Wenn der Edge-Pool ausfällt, in dem der Lync Server-Partnerverbund konfiguriert wurde, müssen Sie den Verbund ändern und einen anderen Edgepool für den Partnerverbund angeben.

## Ausführen eines Failovers für den Edgepool, der für den Lync Server-Partnerverbund verwendet wird

1.  Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edgepools** , und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserver-Pool, der aktuell für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** . Klicken Sie auf **OK** .

3.  Erweitern Sie **Edge-Pools** , und klicken Sie mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der jetzt für den Partnerverbund verwendet werden soll. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Aktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** . Klicken Sie auf **OK** .

5.  Klicken Sie auf **Aktion** , wählen Sie **Topologie** aus, und wählen Sie **Veröffentlichen** aus. Wenn eine entsprechende Eingabeaufforderung angezeigt wird, klicken Sie in **Topologie veröffentlichen** auf **Weiter** . Klicken Sie auf **Fertig stellen** , wenn die Veröffentlichung abgeschlossen ist.

6.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

7.  Klicken Sie auf der Seite Lync Server-Komponenten einrichten auf **Weiter** . Im Zusammenfassungsbildschirm werden die ausgeführten Aktionen angezeigt. Nach Abschluss der Bereitstellung klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.
    
    Wenn der Standort mit dem ausgefallenen Edgepool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren und für einen Edgepool an einem Remotestandort konfigurieren, der weiterhin ausgeführt wird. Nähere Informationen finden Sie unter [Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

## Siehe auch

#### Aufgaben

[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  

#### Konzepte

[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

