---
title: Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec601a9c51e1b8d5785e91bae1f1f82c13bf245
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514772"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).

Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Sie die Windows PowerShell und das New-CsAVEdgeConfiguration-Cmdlet verwenden, um neue Einstellungen auf Standort-oder Dienstebene (d. h. für einen einzelnen A/V-Edgeserver) zu erstellen. Beachten Sie bei der Erstellung neuer Einstellungen Folgendes:

  - Auf Dienstebene konfigurierte Einstellungen (d. h. auf einem einzelnen Server) haben die höchste Priorität.

  - Auf Standortebene zugewiesene Einstellungen haben Vorrang vor den global zugewiesenen Einstellungen. Auf Dienstebene vorgenommene Einstellungen ersetzen jedoch ebenfalls auf Standortebene vorgenommene Einstellungen.

  - Einstellungen auf globaler Ebene werden nur verwendet, wenn auf dem einzelnen Server keine auf Dienstebene vorgenommenen Einstellungen konfiguriert wurden und wenn keine auf Standortebene vorgenommenen Einstellungen für den Standort, wo sich der Server befindet, vorliegen.

Anschließend können all Ihre Einstellungen mit dem Cmdlet Set-CsAVEdgeConfiguration bearbeitet werden. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) und [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>So erstellen Sie neue A/V-Edge-Konfigurationseinstellungen auf Standortebene

  - Der folgende Befehl erstellt eine neue Auflistung von Konfigurationseinstellungen für A/V-Edgeserver für den Standort "Redmond".
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen auf Standortebene

  - Da keine weiteren Parameter vorhanden sind, verwenden diese neuen Einstellungen die Standardwerte für den A/V-Edgedienst. Alternativ können Sie zusätzliche Parameter und Parameterwerte verwenden, um eine benutzerdefinierte Auflistung zu erstellen. Der folgende Befehl legt beispielsweise die Eigenschaft "MaxTokenLifetime" auf vier Stunden (04 Stunden : 00 Minuten : 00 Sekunden) fest:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen auf Dienstebene

  - Dieser Befehl erstellt eine ähnliche Auflistung, die auf den A/V-Edgeserver "atl-edge-001.litwareinc.com" angewendet wird:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>So ändern Sie vorhandene A/V-Edge-Konfigurationseinstellungen

  - In diesem Beispiel wird das Cmdlet Set-CsAVEdgeConfiguration verwendet, um die maximale Gültigkeitsdauer von Token für den Standort Redmond auf zwölf Stunden festzulegen:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/Video-Edgeserver (A/V) in lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Gruppe-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

