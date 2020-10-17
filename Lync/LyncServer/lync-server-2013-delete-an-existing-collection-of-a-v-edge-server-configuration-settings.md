---
title: Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen
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
ms.openlocfilehash: 80a90e58c1dee8aacae052f916c6fdf6e260b7ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514692"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).

Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt. Diese globale Auflistung kann nicht gelöscht werden. Sie können jedoch die Windows PowerShell und das Remove-CsAVEdgeConfiguration-Cmdlet verwenden, um die globale Auflistung zurückzusetzen. Das bedeutet einfach, dass alle Eigenschaftswerte in der globalen Auflistung auf ihren Standardwert zurückgesetzt werden. Wenn Sie beispielsweise die MaxTokenLifetime-Eigenschaft auf 16 Stunden festgelegt haben, wird diese Eigenschaft auf den Standardwert von 8 Stunden zurückgesetzt.

Ihre auf Standort- oder Dienstebene erstellten benutzerdefinierten Einstellungsauflistungen können Sie jedoch mit dem Remove-CsAVEdgeConfiguration-Cmdlet löschen. Wenn Sie Standorteinstellungen löschen, werden die an diesem Standort befindlichen A/V-Edgeserver anhand der globalen Einstellungen verwaltet. Wenn Sie auf Dienstebene festgelegte Einstellungen löschen, wird der Server dann gemäß den Einstellungen für seinen Standort oder (wenn diese nicht vorhanden sind) anhand der globalen Einstellungen verwaltet.

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>So setzen Sie die globale Auflistung zurück

  - Mit dem folgenden Befehl wird die globale Auflistung von A/V-Edge-Konfigurationseinstellungen zurückgesetzt:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>So entfernen Sie eine Sammlung aus dem Website Bereich

  - Mit diesem Befehl werden die A/V-Edge-Konfigurationseinstellungen entfernt, die für den Standort "Redmond" gelten:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>So entfernen Sie eine Auflistung aus dem Dienstbereich

  - Mit diesem Befehl werden die Einstellungen entfernt, die für den A/V-Edgeserver "atl-edge-001.litwareinc.com" gelten:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

