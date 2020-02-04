---
title: 'Lync Server 2013: Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5e0247ccdff82737c2ed7ed830b0a99b7da1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

In den folgenden Beispielen wird gezeigt, wie Sie die in Erstellen von [Standortrichtlinien in lync Server 2013](lync-server-2013-create-location-policies.md) definierte Standortrichtlinie für **Redmond** zu einer vorhandenen Netzwerk Website hinzufügen und wie Sie eine neue Netzwerk Website erstellen, die die Standortrichtlinie für **Redmond** verwendet.

Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.
    
    Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.
    
    Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

