---
title: 'Lync Server 2013: Ausführen eines Failovers für den Edgepool, der für den Lync Server-Partnerverbund verwendet wird'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Wenn der Edge-Pool, in dem Sie den lync Server-Verbund konfiguriert haben, ausfällt, müssen Sie die Föderation so ändern, dass ein anderer Edge-Pool für den Verbund verwendet wird.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Failover des für den lync Server-Verbund verwendeten Edge-Pools

1.  Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edgeserver-Pool, der derzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten**aus.

2.  Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

3.  Erweitern Sie **Edge-Pools**, und klicken Sie dann mit der rechten Maustaste auf den Edge-Server oder den Edgeserver-Pool, den Sie jetzt für den Verbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten**aus.

4.  Wählen Sie in **Eigenschaften bearbeiten** unter **Allgemein** **die Option Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus. Klicken Sie auf **OK**.

5.  Klicken Sie auf **Aktion**, wählen Sie **Topologie**aus, und wählen Sie **veröffentlichen**aus. Wenn Sie dazu aufgefordert werden, **die Topologie zu veröffentlichen**, klicken Sie auf **weiter**. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf **Fertig stellen**.

6.  Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **lync Server System installieren oder aktualisieren**und dann auf **lync Server-Komponenten einrichten oder entfernen**. Klicken Sie **erneut auf Ausführen**.

7.  Klicken Sie bei der Installation von lync Server-Komponenten auf **weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.
    
    Wenn die Website mit dem fehlerhaften Edge-Pool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren, um einen Edge-Pool in einer noch ausgeführten Remotewebsite zu verwenden. Weitere Informationen finden Sie unter [Ändern des Edge-Pools, der einem Front-End-Pool in lync Server 2013 zugeordnet](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Notfallwiederherstellung für Edgeserver in Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

