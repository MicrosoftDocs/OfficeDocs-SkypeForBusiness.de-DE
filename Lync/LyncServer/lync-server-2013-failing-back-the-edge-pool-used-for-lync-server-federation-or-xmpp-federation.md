---
title: Ausführen eines Failbacks für den Edgepool, der für den Lync Server- oder XMPP-Partnerverbund verwendet wird
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
ms.openlocfilehash: 98fec3082c172cc9e31d931d1c64ef3eaeccd04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem ein ausgefallener Edge-Pool, der zum Hosten der Föderation verwendet wurde, wieder online geschaltet wurde, verwenden Sie dieses Verfahren zum Zurücksetzen der lync Server-Föderations Route und/oder der XMPP-Föderations Route, um diesen wiederhergestellten Edge-Pool erneut zu verwenden.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Fehler beim Zurücksetzen des Verbund zu einem wiederhergestellten Edge-Pool

1.  Starten Sie in dem jetzt wieder verfügbaren Edge-Pool die Edge-Dienste.

2.  Gehen Sie wie folgt vor, wenn Sie die lync Server-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:
    
      - Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**aus.
    
      - Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.
    
      - Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edge-Server oder den Edgeserver-Pool, den Sie erneut für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**aus.
    
      - Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus. Klicken Sie auf **OK**.
    
      - Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
      - Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **lync Server System installieren oder aktualisieren**und dann auf **lync Server-Komponenten einrichten oder entfernen**. Klicken Sie **erneut auf Ausführen**.
    
      - Klicken Sie bei der Installation von lync Server-Komponenten auf **weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

3.  Gehen Sie wie folgt vor, wenn Sie die XMPP-Föderations Route zur Verwendung des wiederhergestellten Edge-Servers zurücksetzen möchten:
    
      - Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route an den Edge-Pool zu verweisen, der nun XMPP-Föderation hostet (in diesem Beispiel EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        In diesem Beispiel ist site1 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer1.contoso.com ist der FQDN eines Edgeserver in diesem Pool.
    
      - Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.
        
            _xmpp-server._tcp.contoso.com
    
      - Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.
    
      - Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.

4.  Wenn die Front-End-Pools weiterhin auf der Website mit dem fehlerhaften Edge-Pool ausgeführt wurden und wiederhergestellt wurden, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um die Edge-Pools auf der lokalen Website erneut zu verwenden. Weitere Informationen finden Sie unter [Ändern des Edge-Pools, der einem Front-End-Pool in lync Server 2013 zugeordnet](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)ist.

5.  Wenn der Front-End-Pool am gleichen Standort wie der fehlerhafte Edge-Pool ebenfalls fehlgeschlagen ist, können Sie jetzt Invoke – CsPoolFailback verwenden, um den Front-End-Pool zurückzukehren.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

