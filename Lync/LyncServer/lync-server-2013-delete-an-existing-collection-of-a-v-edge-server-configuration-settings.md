---
title: Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind). Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).

Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt. Diese globale Sammlung kann nicht gelöscht werden. Sie können jedoch die Windows PowerShell und das Cmdlet Remove-CsAVEdgeConfiguration verwenden, um die globale Sammlung zurückzusetzen. Das bedeutet einfach, dass alle Eigenschaftswerte in der globalen Sammlung auf ihren Standardwert zurückgesetzt werden. Wenn Sie beispielsweise die MaxTokenLifetime-Eigenschaft für 16 Stunden fest legt haben, wird diese Eigenschaft auf den Standardwert 8 Stunden zurückgesetzt.

Benutzerdefinierte Einstellungssammlungen, die Sie im Website Bereich oder im Dienstbereich erstellt haben, können jedoch mithilfe des Cmdlets Remove-CsAVEdgeConfiguration gelöscht werden. Wenn Sie Websiteeinstellungen löschen, werden die A/V-Edgeserver auf dieser Website durch die globalen Einstellungen verwaltet. Wenn Sie Dienstbereichs Einstellungen löschen, wird dieser Server dann durch seine Websiteeinstellungen, falls vorhanden, oder durch die globalen Einstellungen verwaltet, wenn keine Websiteeinstellungen verfügbar sind.

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>So setzen Sie die globale Sammlung zurück

  - Mit dem folgenden Befehl wird die globale Sammlung von A/V-Edge-Konfigurationseinstellungen zurückgesetzt:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>So entfernen Sie eine Sammlung aus dem Website Bereich

  - Mit diesem Befehl werden die Konfigurationseinstellungen für A/V-Edge entfernt, die auf die Redmond-Website angewendet werden:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>So entfernen Sie eine Sammlung aus dem Dienstbereich

  - Mit diesem Befehl werden die auf die A/V-Edgeserver-ATL-Edge-001.litwareinc.com angewendeten Einstellungen entfernt:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

