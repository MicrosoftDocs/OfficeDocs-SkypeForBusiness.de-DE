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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Verzweigungs Websites stellen physische Zweigstellen dar, die über eine WAN-Verbindung mit ihren Hauptniederlassungen verbunden sind. Wenn Sie Ihrer lync-Topologie eine Verzweigungs Website hinzufügen möchten, führen Sie diese Schritte am zentralen Standort aus.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>So fügen Sie Ihrer Topologie Verzweigungs Websites hinzu

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur die zentrale Website, klicken Sie mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.

3.  Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.

4.  Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.

5.  Klicken Sie auf **Weiter**.

6.  Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.
    
      - Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.
    
      - Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.

7.  Klicken Sie auf **weiter**, und führen Sie dann eine der folgenden Aktionen aus:
    
      - Wenn Sie eine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, stellen Sie sicher, dass das Kontrollkästchen **den neuen Überlebenden Assistenten beim Schließen des Assistenten öffnen** aktiviert ist, klicken Sie auf **Fertig stellen**, und folgen Sie dann den Anweisungen des Assistenten, der geöffnet wird. Informationen zu Assistenten Elementen finden Sie unter Definieren einer überlebensfähigen [Verzweigungs Einheit oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.

8.  Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie zur Topologie hinzufügen möchten.

**Nächster Schritt:**

Für Survivable Branch-Appliances oder-Server: Definieren einer überlebensfähigen [Branch-Appliance oder eines Survivable-Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Für nicht belastbare PSTN-Konnektivität: [Definieren eines PSTN-Gateways für eine Zweigstelle in lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Konfigurieren eines Trunks mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)oder [Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

