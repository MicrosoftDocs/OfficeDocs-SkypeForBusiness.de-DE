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
ms.openlocfilehash: 576fcb445eb37b92356ad9fdf36de716581ca6fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="473a5-102">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="473a5-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="473a5-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="473a5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="473a5-p101">Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="473a5-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="473a5-106">Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="473a5-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="473a5-107">Darüber hinaus können Sie die Windows PowerShell und das Cmdlet New-CsAVEdgeConfiguration verwenden, um neue Einstellungen auf Standort-oder Dienstebene (d. h. für einen einzelnen A/V-Edgeserver) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="473a5-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="473a5-108">Beachten Sie bei der Erstellung neuer Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="473a5-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="473a5-109">Auf Dienstebene konfigurierte Einstellungen (d. h. auf einem einzelnen Server) haben die höchste Priorität.</span><span class="sxs-lookup"><span data-stu-id="473a5-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="473a5-p103">Auf Standortebene zugewiesene Einstellungen haben Vorrang vor den global zugewiesenen Einstellungen. Auf Dienstebene vorgenommene Einstellungen ersetzen jedoch ebenfalls auf Standortebene vorgenommene Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="473a5-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="473a5-112">Einstellungen auf globaler Ebene werden nur verwendet, wenn auf dem einzelnen Server keine auf Dienstebene vorgenommenen Einstellungen konfiguriert wurden und wenn keine auf Standortebene vorgenommenen Einstellungen für den Standort, wo sich der Server befindet, vorliegen.</span><span class="sxs-lookup"><span data-stu-id="473a5-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="473a5-113">Anschließend können all Ihre Einstellungen mit dem Cmdlet Set-CsAVEdgeConfiguration bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="473a5-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="473a5-114">Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) und [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="473a5-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="473a5-115">So erstellen Sie neue A/V-Edge-Konfigurationseinstellungen auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="473a5-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="473a5-116">Der folgende Befehl erstellt eine neue Auflistung von Konfigurationseinstellungen für A/V-Edgeserver für den Standort "Redmond".</span><span class="sxs-lookup"><span data-stu-id="473a5-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="473a5-117">So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="473a5-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="473a5-p105">Da keine weiteren Parameter vorhanden sind, verwenden diese neuen Einstellungen die Standardwerte für den A/V-Edgedienst. Alternativ können Sie zusätzliche Parameter und Parameterwerte verwenden, um eine benutzerdefinierte Auflistung zu erstellen. Der folgende Befehl legt beispielsweise die Eigenschaft "MaxTokenLifetime" auf vier Stunden (04 Stunden : 00 Minuten : 00 Sekunden) fest:</span><span class="sxs-lookup"><span data-stu-id="473a5-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="473a5-121">So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen auf Dienstebene</span><span class="sxs-lookup"><span data-stu-id="473a5-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="473a5-122">Dieser Befehl erstellt eine ähnliche Auflistung, die auf den A/V-Edgeserver "atl-edge-001.litwareinc.com" angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="473a5-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="473a5-123">So ändern Sie vorhandene A/V-Edge-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="473a5-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="473a5-124">In diesem Beispiel wird das Cmdlet Set-CsAVEdgeConfiguration verwendet, um die maximale Gültigkeitsdauer von Token für den Standort Redmond auf zwölf Stunden festzulegen:</span><span class="sxs-lookup"><span data-stu-id="473a5-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="473a5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="473a5-125">See Also</span></span>


[<span data-ttu-id="473a5-126">Zurückgeben von A/V-Edgeserver Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="473a5-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="473a5-127">Löschen einer vorhandenen Auflistung von A/V-Edgeserver Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="473a5-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="473a5-128">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="473a5-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="473a5-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="473a5-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="473a5-130">[Gruppe-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="473a5-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

