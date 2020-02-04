---
title: 'Lync Server 2013: Erstellen von Netzwerk-standortübergreifenden Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Erstellen von Netzwerk-standortübergreifenden Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Eine *Netzwerk-standortübergreifende Richtlinie* definiert Bandbreiteneinschränkungen zwischen Websites, die direkte WAN-Verbindungen zwischen Ihnen aufweisen.

Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Eine Netzwerk-standortübergreifende Richtlinie ist <EM>nur</EM> erforderlich, wenn zwischen zwei Netzwerkstandorten eine direkte Querverbindung besteht.



</div>

In der Region „Nordamerika“ der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten „Reno“ und „Albuquerque“. Diese beiden Websites erfordern eine standortübergreifende Richtlinie, die ein entsprechendes bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das 20MB\_-Link Profil angewendet.

<div>

## <a name="to-create-a-network-intersite-policy"></a>So erstellen Sie eine netzwerkübergreifende Richtlinie

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet New-CsNetworkInterSitePolicy aus, um netzwerkübergreifende Richtlinien zu erstellen und ein entsprechendes bandbreitenrichtlinienprofil für zwei Websites anzuwenden, die einen direkten Querverweis aufweisen. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Wiederholen Sie Schritt 2 nach Bedarf, um netzwerkübergreifende Richtlinien für alle Netzwerk Website Paare zu erstellen, die eine direkte Kreuzverknüpfung aufweisen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

