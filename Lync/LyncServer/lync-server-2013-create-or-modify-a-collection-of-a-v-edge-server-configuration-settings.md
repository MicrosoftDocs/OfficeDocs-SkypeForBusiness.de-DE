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

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3bd4a-102">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd4a-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bd4a-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3bd4a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3bd4a-104">Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind).</span><span class="sxs-lookup"><span data-stu-id="3bd4a-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="3bd4a-105">Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="3bd4a-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="3bd4a-106">Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="3bd4a-107">Darüber hinaus können Sie die Windows PowerShell und das Cmdlet New-CsAVEdgeConfiguration verwenden, um neue Einstellungen für den Website Bereich oder den Dienstbereich (also für einen einzelnen A/V-Edgeserver) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="3bd4a-108">Beachten Sie beim Erstellen neuer Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3bd4a-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="3bd4a-109">Im Dienstbereich konfigurierte Einstellungen (also auf einem einzelnen Server) haben Vorrang vor allem.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="3bd4a-110">Die für den Website Bereich konfigurierten Einstellungen haben Vorrang vor den im globalen Bereich konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="3bd4a-111">Dienstbereichs Einstellungen ersetzen jedoch auch die Einstellungen für den Website Bereich.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="3bd4a-112">Einstellungen im globalen Bereich werden nur verwendet, wenn auf dem einzelnen Server keine Diensteinstellungen konfiguriert sind und keine Websiteeinstellungen für die Website vorhanden sind, auf der sich der Server befindet.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="3bd4a-113">Alle Einstellungen können dann mithilfe des Cmdlets "Satz-CsAVEdgeConfiguration" geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3bd4a-114">Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) und Cmdlets für [festgelegte CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="3bd4a-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="3bd4a-115">So erstellen Sie neue A/V-Edge-Konfigurationseinstellungen im Website Bereich</span><span class="sxs-lookup"><span data-stu-id="3bd4a-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="3bd4a-116">Mit dem folgenden Befehl wird eine neue Sammlung von a/V-Edge-Konfigurationseinstellungen für die Website "Redmond" erstellt:</span><span class="sxs-lookup"><span data-stu-id="3bd4a-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="3bd4a-117">So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen im Website Bereich</span><span class="sxs-lookup"><span data-stu-id="3bd4a-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="3bd4a-118">Da keine zusätzlichen Parameter enthalten sind, verwenden diese neuen Einstellungen die Standardwerte für den A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="3bd4a-119">Alternativ können Sie zusätzliche Parameter und Parameterwerte hinzufügen, um eine benutzerdefinierte Sammlung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3bd4a-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="3bd4a-120">Mit diesem Befehl wird beispielsweise die MaxTokenLifetime-Eigenschaft auf 4 Stunden (04 Stunden: 00 Minuten: 00 Sekunden) festgelegt:</span><span class="sxs-lookup"><span data-stu-id="3bd4a-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="3bd4a-121">So erstellen Sie benutzerdefinierte A/V-Edge-Konfigurationseinstellungen im Dienstbereich</span><span class="sxs-lookup"><span data-stu-id="3bd4a-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="3bd4a-122">Mit diesem Befehl wird eine ähnliche Sammlung erstellt, die auf die a/V-Edgeserver-ATL-Edge-001.litwareinc.com angewendet wurde:</span><span class="sxs-lookup"><span data-stu-id="3bd4a-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="3bd4a-123">So ändern Sie vorhandene A/V-Edge-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3bd4a-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="3bd4a-124">In diesem Beispiel wird das Cmdlet "Satz-CsAVEdgeConfiguration" verwendet, um die maximale Token-Lebensdauer für den Standort "Redmond" auf 12 Stunden zu ändern:</span><span class="sxs-lookup"><span data-stu-id="3bd4a-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3bd4a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bd4a-125">See Also</span></span>


[<span data-ttu-id="3bd4a-126">Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd4a-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="3bd4a-127">Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd4a-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="3bd4a-128">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bd4a-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="3bd4a-129">[Neu – CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3bd4a-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="3bd4a-130">[Satz-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3bd4a-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

