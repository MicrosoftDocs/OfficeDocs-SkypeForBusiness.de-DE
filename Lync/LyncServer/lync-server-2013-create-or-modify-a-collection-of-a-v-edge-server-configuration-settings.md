---
title: Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind). Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).

Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Sie die Windows PowerShell und das Cmdlet New-CsAVEdgeConfiguration verwenden, um neue Einstellungen für den Website Bereich oder den Dienstbereich (also für einen einzelnen A/V-Edgeserver) zu erstellen. Beachten Sie beim Erstellen neuer Einstellungen Folgendes:

  - Im Dienstbereich konfigurierte Einstellungen (also auf einem einzelnen Server) haben Vorrang vor allem.

  - Die für den Website Bereich konfigurierten Einstellungen haben Vorrang vor den im globalen Bereich konfigurierten Einstellungen. Dienstbereichs Einstellungen ersetzen jedoch auch die Einstellungen für den Website Bereich.

  - Einstellungen im globalen Bereich werden nur verwendet, wenn auf dem einzelnen Server keine Diensteinstellungen konfiguriert sind und keine Websiteeinstellungen für die Website vorhanden sind, auf der sich der Server befindet.

Alle Einstellungen können dann mithilfe des Cmdlets "Satz-CsAVEdgeConfiguration" geändert werden. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) und Cmdlets für [festgelegte CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>So erstellen Sie neue A/V-Edge-Konfigurationseinstellungen im Website Bereich

  - Mit dem folgenden Befehl wird eine neue Sammlung von a/V-Edge-Konfigurationseinstellungen für die Website "Redmond" erstellt:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen im Website Bereich

  - Da keine zusätzlichen Parameter enthalten sind, verwenden diese neuen Einstellungen die Standardwerte für den A/V-Edgedienst. Alternativ können Sie zusätzliche Parameter und Parameterwerte hinzufügen, um eine benutzerdefinierte Sammlung zu erstellen. Mit diesem Befehl wird beispielsweise die MaxTokenLifetime-Eigenschaft auf 4 Stunden (04 Stunden: 00 Minuten: 00 Sekunden) festgelegt:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen im Dienstbereich

  - Mit diesem Befehl wird eine ähnliche Sammlung erstellt, die auf die a/V-Edgeserver-ATL-Edge-001.litwareinc.com angewendet wurde:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>So ändern Sie vorhandene A/V-Edge-Konfigurationseinstellungen

  - In diesem Beispiel wird das Cmdlet "Satz-CsAVEdgeConfiguration" verwendet, um die maximale Token-Lebensdauer für den Standort "Redmond" auf 12 Stunden zu ändern:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Neu – CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Satz-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

