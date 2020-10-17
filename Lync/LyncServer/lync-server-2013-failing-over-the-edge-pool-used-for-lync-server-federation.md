---
title: 'Lync Server 2013: Fehler bei der Edgepool, die für lync Server Partnerverbund verwendet wird'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ed4849aff6dd65de524a99ac8fc6f886d7c4db5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530922"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Wenn der Edge-Pool ausfällt, in dem der Lync Server-Partnerverbund konfiguriert wurde, müssen Sie den Verbund ändern und einen anderen Edgepool für den Partnerverbund angeben.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Failover des Edgepools für den Lync Server-Verbund

1.  Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder auf den Edgeserverpool, der zurzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

3.  Erweitern Sie **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der jetzt für den Partnerverbund verwendet werden soll. Wählen Sie **Eigenschaften bearbeiten** aus.

4.  Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.

5.  Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.

6.  Öffnen Sie den Assistenten für die Lync Server-Bereitstellung auf dem Edgeserver. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** und dann auf **Lync Server-Komponenten einrichten oder entfernen**. Klicken Sie auf **Erneut ausführen**.

7.  Klicken Sie unter "Lync Server-Komponenten einrichten" auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.
    
    Wenn der Standort mit dem ausgefallenen Edgepool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren und für einen Edgepool an einem Remotestandort konfigurieren, der weiterhin ausgeführt wird. Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Edgeserver Notfallwiederherstellung in lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

