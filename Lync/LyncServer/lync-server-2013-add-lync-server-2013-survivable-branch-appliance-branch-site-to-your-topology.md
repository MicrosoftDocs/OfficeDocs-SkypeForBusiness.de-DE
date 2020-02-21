---
title: Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b43272cc5ca054f913d51ec157802dc8f847461
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-07_

Microsoft lync Server 2013 Survivable Branch Appliances (SBA) können keinem Microsoft lync Server 2010 Front-End-Pool als Sicherungs Registrierungsstelle zugeordnet werden. Das SBA muss einem Microsoft lync Server 2013 Front-End-Pool zugeordnet werden. Bei diesen Schritten wird ein Microsoft lync Server 2013 SBA angenommen. Führen Sie dieses Verfahren am zentralen Standort aus.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>So fügen Sie einer Topologie Zweigstellen mit Microsoft lync Server 2013 SBA hinzu

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie den zentralen Standort in der Konsolenstruktur, erweitern Sie **Zweigniederlassungen**, und klicken Sie dann auf **Neue Zweigniederlassung**.

3.  Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** auf **Name**, und geben Sie einen Namen für die neue Zweigniederlassung ein.

4.  (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Zweigniederlassung ein.

5.  Klicken Sie auf **Weiter**.

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.
    
      - Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.
    
      - Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.

7.  Klicken Sie auf **Weiter**, und führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie eine Survivable Branch Appliance oder Survivable Branch Server an dieser Stelle verwenden, müssen Sie sicherstellen, dass das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist.
    
      - Wenn Sie auf dieser Website keine Survivable Branch Appliance oder Survivable Branch Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird.
    
      - Klicken Sie auf **Fertig stellen**, und befolgen Sie die Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter [define a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Definieren eines PSTN-Gateways für einen Zweigstellenstandort in lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

