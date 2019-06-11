---
title: 'Lync Server 2013: Definieren der IP-Adresse für ein SIP/CSTA-Gateway'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn lync Server eine Verbindung mit dem SIP/CSTA-Gateway herstellen soll, das Sie für die Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) bereitgestellt haben, müssen Sie die IP-Adresse des Gateways im Topologie-Generator definieren. Dieser Schritt ist für Gateways, die TLS-Verbindungen (Transport Layer Security) unterstützen, nicht erforderlich. Für jedes Gateway, das TLS-Verbindungen unterstützt, können Sie dieses Verfahren überspringen und die Bereitstellung der Remoteanrufsteuerung fortsetzen, indem Sie die Schritte unter [Aktivieren von lync-Benutzern für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md)ausführen.

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>So definieren Sie die IP-Adresse des SIP/CSTA-Gateways mithilfe des Topologie-Generators

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

3.  Wählen Sie die Option zum Herunterladen einer vorhandenen Topologie aus.

4.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

5.  Klicken Sie mit der rechten Maustaste auf den von Ihnen erstellten vertrauenswürdigen Anwendungspool, wie unter [Konfigurieren eines Eintrags für eine vertrauenswürdige Anwendung für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)beschrieben, und klicken Sie dann auf **Eigenschaften bearbeiten**.

6.  Deaktivieren Sie das Kontrollkästchen **Replikation von Konfigurationsdaten an diesen Pool aktivieren** .

7.  Klicken Sie auf **Dienstnutzung auf ausgewählte IP-Adressen einschränken**. Die Standardeinstellung ist " **alle konfigurierten IP-Adressen verwenden**".

8.  Geben Sie im Textfeld **primäre IP-Adresse** die IP-Adresse des SIP/CSTA-Gateways ein.

9.  Wenn Sie die Topologie im zentralen Verwaltungsspeicher aktualisieren möchten, klicken Sie in der Konsolenstruktur auf **lync Server**, und klicken Sie dann im Bereich **Aktionen** auf **veröffentlichen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

