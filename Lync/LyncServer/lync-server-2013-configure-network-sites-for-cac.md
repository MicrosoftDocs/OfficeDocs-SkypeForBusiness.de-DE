---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Websites für CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Konfigurieren von Netzwerk Websites für CAC in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Wenn Sie bereits Netzwerk Websites für E9-1-1 oder Media Bypass erstellt haben, können Sie die vorhandenen Netzwerk Websites so ändern, dass ein bandbreitenrichtlinienprofil mithilfe des Cmdlets " <STRONG>CsNetworkSite</STRONG> " angewendet wird. Ein Beispiel für das Ändern einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.



</div>

*Netzwerk Websites* sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen. Führen Sie die folgenden Verfahren aus, um Netzwerk Websites zu erstellen, die in der Beispiel Netzwerktopologie für CAC an Netzwerk Websites ausgerichtet sind. In diesen Verfahren wird gezeigt, wie Netzwerk Websites erstellt und konfiguriert werden, die durch WAN-Bandbreite eingeschränkt sind, und daher Bandbreitenrichtlinien erforderlich sind, die den Echt Zeit Durchsatz von Audio-oder Videodaten einschränken.

Im Beispiel für die CAC-Bereitstellung verfügt die Region Nordamerika über sechs Websites. Drei dieser Websites sind durch die WAN-Bandbreite beschränkt: Reno, Portland und Albuquerque. Die anderen drei Websites, die *nicht* von der WAN-Bandbreite abhängig sind: New York, Chicago und Detroit. Ein Beispiel zum Erstellen oder Ändern dieser anderen Netzwerk Websites finden Sie unter [erstellen oder Ändern einer Netzwerk Website in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

<div class=" ">


> [!NOTE]  
> Im folgenden Verfahren wird die lync Server-Verwaltungsshell zum Erstellen einer Netzwerk Website verwendet. Details zur Verwendung der lync Server-Systemsteuerung zum Erstellen einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>So erstellen Sie Netzwerk Websites für die Anrufsteuerung

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerk Websites zu erstellen und auf jede Website ein entsprechendes bandbreitenrichtlinienprofil anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Um das Erstellen von Netzwerk Websites für die gesamte Beispieltopologie abzuschließen, wiederholen Sie Schritt 2 für die Netzwerk Websites mit Bandbreiteneinschränkungen in den Regionen EMEA und APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

