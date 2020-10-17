---
title: 'Lync Server 2013: Hinzufügen von Zweigstellenstandorten zur Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521572"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Zweigstellenstandorte repräsentieren physische Zweigstellenbüros, die über einen WAN-Link mit Ihren Hauptbüros verbunden sind. Führen Sie dieses Verfahren am zentralen Standort aus, um einen Zweigstellenstandort zu Ihrer Lync-Topologie hinzuzufügen.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>So fügen Sie Zweigstellenstandorte zu einer Topologie hinzu

1.  Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie den zentralen Standort in der Konsolenstruktur, klicken Sie mit der rechten Maustaste auf **Zweigstellenstandorte**, und klicken Sie dann auf **Neuer Zweigstellenstandort**.

3.  Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.

4.  (Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.

5.  Klicken Sie auf **Weiter**.

6.  (Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.
    
      - Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.
    
      - Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.

7.  Klicken Sie auf **Weiter**, und führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie an dieser Stelle eine Survivable Branch Appliance oder einen Server verwenden, müssen Sie sicherstellen, dass das Kontrollkästchen neuen übermäßigen **Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist, klicken Sie auf **Fertig stellen**, und folgen Sie dann den Anweisungen im Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter [define a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Wenn Sie an diesem Standort keinen Survivable Branch Appliance oder Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.

8.  Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.

**Nächster Schritt:**

Bei Survivable Branch Appliances oder Servern: [Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Für nicht belastbare PSTN-Konnektivität: [definieren Sie ein PSTN-Gateway für einen Zweigstellenstandort in lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Konfigurieren Sie einen trunk mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

