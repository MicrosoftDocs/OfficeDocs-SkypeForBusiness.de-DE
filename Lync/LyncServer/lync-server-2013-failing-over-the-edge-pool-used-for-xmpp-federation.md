---
title: 'Lync Server 2013: Ausführen eines Failovers für den Edgepool, der für den XMPP-Partnerverbund verwendet wird'
TOCTitle: Ausführen eines Failovers für den Edgepool, der für den XMPP-Partnerverbund verwendet wird
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49890757
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. Weitere Informationen über das Aktivieren und Einrichten von XMPP-Verbünden finden Sie unter [Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Im folgenden Verfahren stellt EdgePool1 den Pool dar, in dem der XMPP-Verbund ursprünglich gehostet wurde; EdgePool2 ist der Pool, in dem der XMPP-Verbund jetzt gehostet werden soll.

## Ausführen eines Failovers für den Edgepool, der für den XMPP-Partnerverbund verwendet wird

1.  Wenn Sie (neben dem ausgefallenen) noch keinen weiteren Edgepool bereitgestellt haben, stellen Sie den Pool jetzt bereit. Ausführliche Informationen finden Sie unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Führen Sie auf jedem Edgeserver im neuen Edgepool, in dem jetzt der XMPP-Verbund gehostet wird (EdgePool2), das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie das folgende Cmdlet aus, damit die XMPP-Verbundroute wieder auf EdgePool2 zeigt:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel stellt Site2 den Standort mit dem Edgepool dar, in dem jetzt die XMPP-Verbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.

5.  Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.
    
        _xmpp-server._tcp.contoso.com

6.  Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.

7.  Starten Sie die Dienste auf allen Edgeservern in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird:
    
        Start-CsWindowsService

