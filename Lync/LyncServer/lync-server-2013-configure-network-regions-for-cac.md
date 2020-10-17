---
title: 'Lync Server 2013: Konfigurieren von netzwerkregionen für die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520542"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Wenn Sie bereits Netzwerkregionen für E9-1-1 oder die Medienumgehung erstellt haben, können Sie diesen Netzwerkregionen mithilfe des <STRONG>Set-CsNetworkRegion</STRONG>-Cmdlets Einstellungen für die Anrufsteuerung (Call Admission Control, CAC) hinzufügen. Ein Beispiel für das Ändern einer netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>.



</div>

Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Erstellen Sie mithilfe des folgenden Verfahrens Netzwerkregionen gemäß denen in der Beispielnetzwerktopologie für die Anrufsteuerung. Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

Die Beispielnetzwerktopologie für die Anrufsteuerung umfasst drei Regionen: Nordamerika, EMEA und APAC. Jede Region verfügt über einen eigenen zentralen Standort. Der Name des zentralen Standorts in der Region "North America" lautet CHICAGO. Das folgende Beispiel zeigt, wie Sie die Region "North America" mithilfe des **New-CsNetworkRegion**-Cmdlets erstellen können.

<div>


> [!NOTE]  
> Im folgenden Verfahren wird lync Server-Verwaltungsshell verwendet, um eine netzwerkregion zu erstellen. Ausführliche Informationen zur Verwendung lync Server-Systemsteuerung zum Erstellen einer netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>So erstellen Sie eine Netzwerkregion für die Anrufsteuerung

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie für jede Region, die Sie erstellen möchten, das **New-CsNetworkRegion**-Cmdlet aus. Zum Erstellen der Region "North America" führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Wiederholen Sie Schritt 2, um die Netzwerkregionen "EMEA" und "APAC" zu erstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

