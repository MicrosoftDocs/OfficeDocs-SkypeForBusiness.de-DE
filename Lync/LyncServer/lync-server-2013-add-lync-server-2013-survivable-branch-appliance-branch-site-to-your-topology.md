---
title: Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Hinzufügen eines Zweigstellenstandorts mit einer Lync Server 2013 Survivable Branch Appliance zu einer Topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Microsoft lync Server 2013 Survivor-Branch-Appliances (SBA) können einem Microsoft lync Server 2010-Front-End-Pool nicht als Sicherungs Registrierungsstelle zugeordnet werden. Die SBA muss einem Microsoft lync Server 2013-Front-End-Pool zugeordnet sein. Bei diesen Schritten wird von einem Microsoft lync Server 2013 SBA ausgegangen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>So fügen Sie Ihrer Topologie Verzweigungs Websites mit Microsoft lync Server 2013 SBA hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die zentrale Website, erweitern Sie **Verzweigungs Standorte**, und klicken Sie dann auf **neue Verzweigungs Website**.

3.  Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann einen Namen für die neue Verzweigungs Website ein.

4.  Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.

5.  Klicken Sie auf **Weiter**.

6.  Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.
    
      - Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.
    
      - Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.

7.  Klicken Sie auf **weiter**, und führen Sie dann eine der folgenden Aktionen aus:
    
      - Wenn Sie eine Survivable Branch-Appliance oder einen Survivable Branch-Server an diesem Standort verwenden, stellen Sie sicher, dass das Kontrollkästchen neuen überlebensfähigen **Assistenten öffnen, wenn dieser Assistent geschlossen** wird, aktiviert ist.
    
      - Wenn Sie auf dieser Website keine überlebensfähige Branch Appliance oder einen Survivable Branch-Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird.
    
      - Klicken Sie auf **Fertig stellen**, und folgen Sie dann den Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter Definieren einer überlebensfähigen [Verzweigungs Einheit oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie zur Topologie hinzufügen möchten.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definieren eines PSTN-Gateways für eine Zweigstelle in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

