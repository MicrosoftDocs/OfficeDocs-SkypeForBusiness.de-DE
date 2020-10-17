---
title: Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Partnerverbund verwendet werden
description: Fehler beim Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Partnerverbund verwendet werden.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137910d71de1d6177356e0b7bacbd6d17022d71d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567721"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Nachdem ein ausgefallener Edgepool, von dem der Partnerverbund gehostet wurde, wieder online geschaltet wurde, führen Sie mit diesem Verfahren ein Failback für die Lync Server-Partnerverbundroute und/oder die XMPP-Partnerverbundroute aus, um den wiederhergestellten Edgepool wiederzuverwenden.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Ausführen eines Failbacks für den Partnerverbund für einen wiederhergestellten Edgepool

1.  Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.

2.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die Lync Server-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
      - Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserver-Pool, der aktuell für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserver-Pool, den Sie wieder für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.
    
      - Aktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.
    
      - Öffnen Sie den Assistenten für die Lync Server-Bereitstellung auf dem Edgeserver. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** und dann auf **Lync Server-Komponenten einrichten oder entfernen**. Klicken Sie auf **Erneut ausführen**.
    
      - Klicken Sie unter "Lync Server-Komponenten einrichten" auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.

3.  Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die XMPP-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-Partnerverbundroute erneut auf den Edgepool zu verweisen, von dem nun der XMPP-Partnerverbund gehostet wird (in diesem Beispiel EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel ist Site1 der Standort, der den Edgepool enthält, von dem nun die XMPP-Partnerverbundroute gehostet wird. EdgeServer1.contoso.com ist der vollqualifizierte Domänenname (FQDN) eines Edgeservers in diesem Pool.
    
      - Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.
    
      - Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.

4.  Falls die Front-End-Pools weiter an dem Standort ausgeführt werden, der den ausgefallenen und inzwischen wiederhergestellten Edgepool enthält, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End-Pools aktualisieren, sodass wieder die Edgepools am lokalen Standort verwendet werden. Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Falls der Front-End-Pool am selben Standort wie der ausgefallene Edgepool ebenfalls ausgefallen ist, können Sie nun mit Invoke–CsPoolFailback ein Failback auf den Front-End-Pool ausführen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Edgeserver Notfallwiederherstellung in lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

