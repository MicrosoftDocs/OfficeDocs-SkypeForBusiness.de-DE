---
title: 'Lync Server 2013: Konfigurieren von Netzwerkstandorten für die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2c956eb4f50a0a5e7ce1bafe955b5cea092cd2c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Wenn Sie bereits Netzwerkstandorte für E9-1-1 oder medienumgehung erstellt haben, können Sie die vorhandenen Netzwerkstandorte so ändern, dass ein bandbreitenrichtlinienprofil mithilfe des Cmdlets " <STRONG>CsNetworkSite</STRONG> " angewendet wird. Ein Beispiel für das Ändern eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.



</div>

*Netzwerkstandorte* sind die Büros oder Standorte in den einzelnen netzwerkregionen der Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medien Umgehungs Bereitstellungen. Verwenden Sie die folgenden Verfahren, um Netzwerkstandorte zu erstellen, die an Netzwerkstandorten in der Beispiel Netzwerktopologie für die Anrufsteuerung ausgerichtet sind. Diese Verfahren zeigen, wie Sie Netzwerkstandorte erstellen und konfigurieren, die von der WAN-Bandbreite abhängig sind, und daher Bandbreitenrichtlinien benötigen, die den Datenfluss in Echtzeit über Audio oder Video begrenzen.

In der Beispielbereitstellung für die Anrufsteuerung verfügt die Region "Nordamerika" über sechs Standorte. Drei dieser Standorte sind von der WAN-Bandbreite eingeschränkt: Reno, Portland und Albuquerque. Die anderen drei Standorte, die *nicht* durch WAN-Bandbreite eingeschränkt sind: New York, Chicago und Detroit. Ein Beispiel für das Erstellen oder Ändern dieser anderen Netzwerkstandorte finden Sie unter [erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

<div class=" ">


> [!NOTE]  
> Im folgenden Verfahren wird lync Server-Verwaltungsshell zum Erstellen eines Netzwerkstandorts verwendet. Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung zum Erstellen eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>So erstellen Sie Netzwerkstandorte für die Anrufsteuerung

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerkstandorte zu erstellen und ein entsprechendes bandbreitenrichtlinienprofil auf jeden Standort anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Zum Abschließen der Erstellung von Netzwerkstandorten für die gesamte Beispieltopologie wiederholen Sie Schritt 2 für die Netzwerkstandorte mit Bandbreiteneinschränkungen in den Regionen EMEA und APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

