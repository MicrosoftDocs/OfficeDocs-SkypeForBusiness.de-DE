---
title: 'Lync Server 2013: Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind). Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).

Wenn Sie Informationen zu den A/V-Edge-Konfigurationseinstellungen zurückgeben möchten, die in Ihrer Organisation verwendet werden, müssen Sie Windows PowerShell und das Cmdlet Get-CsAVEdgeConfiguration verwenden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Informationen, die vom Cmdlet "Get-CsAVEdgeConfiguration" zurückgegeben werden, sehen wie folgt aus:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>So geben Sie Informationen zu allen ihren A/V-Edge-Konfigurationseinstellungen zurück

  - Mit dem folgenden Befehl werden Informationen zu allen A/V-Edge-Konfigurationseinstellungen zurückgegeben, die derzeit in Ihrer Organisation verwendet werden:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>So geben Sie Informationen zu Konfigurationseinstellungen für den Website Bereich A/V-Edge zurück

  - Wenn Sie Informationen zu einer bestimmten Sammlung von a/V-Edge-Konfigurationseinstellungen zurückgeben möchten, geben Sie die Identität dieser Sammlung an, wenn Sie das Cmdlet "Get-CsAVEdgeConfiguration" ausführen. Dieser Befehl gibt beispielsweise nur Informationen für die Einstellungen zurück, die auf die Redmond-Website angewendet wurden:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>So geben Sie Informationen für die Konfigurationseinstellungen des Dienstbereichs A/V-Edge zurück

  - Und dieser Befehl gibt nur Informationen für Einstellungen zurück, auf die ein bestimmter a/V-Edgeserver angewendet wurde:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

