---
title: 'Lync Server 2013: Zurückgeben von A/V-Edgeserver Konfigurationsinformationen'
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
ms.openlocfilehash: 50cfd257e387c48af8446adc43b25d4fd0818ea5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).

Wenn Sie Informationen zu den in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurückgeben möchten, müssen Sie Windows PowerShell und das Cmdlet Get-CsAVEdgeConfiguration verwenden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Vom Cmdlet Get-CsAVEdgeConfiguration zurückgegebene Informationen sehen in etwa so aus:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>So geben Sie Informationen zu allen A/V-Edge-Konfigurationseinstellungen zurück

  - Der folgende Befehl gibt Informationen über alle derzeit in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurück:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>So geben Sie Informationen zu den standortbezogenen A/V-Edge-Konfigurationseinstellungen zurück

  - Geben Sie zum Zurückgeben von Informationen über eine bestimmte Sammlung von A/V-Edge-Konfigurationseinstellungen die Identität der Sammlung an, wenn das Cmdlet Get-CsAVEdgeConfiguration ausgeführt wird. Beispielsweise gibt dieser Befehl nur Informationen für die Einstellungen zurück, die im Standort Redmond angewendet wurden:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>So geben Sie Informationen zu Dienstbereichs bezogenen A/V-Edge-Konfigurationseinstellungen zurück

  - Und dieser Befehl gibt nur Informationen für Einstellungen zurück, die auf einem bestimmten A/V-Edgeserver angewendet wurden:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

