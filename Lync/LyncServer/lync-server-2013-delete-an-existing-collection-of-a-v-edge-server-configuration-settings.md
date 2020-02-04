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

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a9f2a-102">Löschen einer vorhandenen Sammlung von A/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f2a-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9f2a-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9f2a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9f2a-104">Der a/V-Edgedienst bietet internen Benutzern (Benutzern, die bei Ihrem Unternehmensnetzwerk angemeldet sind) die Möglichkeit, Audio und Video für externe Benutzer freizugeben (Benutzer, die nicht bei Ihrem Organisationsnetzwerk angemeldet sind).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="a9f2a-105">Der a/v-Edgedienst wird in erster Linie mithilfe von a/v-Edge-Konfigurationseinstellungen verwaltet, die für den Website Bereich oder den Dienstbereich konfiguriert werden können (d. h., Sie können für einen einzelnen a/v-Edgeserver konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="a9f2a-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="a9f2a-106">Wenn Sie lync Server installieren, wird eine globale Sammlung von a/V-Edge-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="a9f2a-107">Diese globale Sammlung kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="a9f2a-108">Sie können jedoch die Windows PowerShell und das Cmdlet Remove-CsAVEdgeConfiguration verwenden, um die globale Sammlung zurückzusetzen. Das bedeutet einfach, dass alle Eigenschaftswerte in der globalen Sammlung auf ihren Standardwert zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="a9f2a-109">Wenn Sie beispielsweise die MaxTokenLifetime-Eigenschaft für 16 Stunden fest legt haben, wird diese Eigenschaft auf den Standardwert 8 Stunden zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="a9f2a-110">Benutzerdefinierte Einstellungssammlungen, die Sie im Website Bereich oder im Dienstbereich erstellt haben, können jedoch mithilfe des Cmdlets Remove-CsAVEdgeConfiguration gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a9f2a-111">Wenn Sie Websiteeinstellungen löschen, werden die A/V-Edgeserver auf dieser Website durch die globalen Einstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="a9f2a-112">Wenn Sie Dienstbereichs Einstellungen löschen, wird dieser Server dann durch seine Websiteeinstellungen, falls vorhanden, oder durch die globalen Einstellungen verwaltet, wenn keine Websiteeinstellungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9f2a-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="a9f2a-113">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="a9f2a-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="a9f2a-114">So setzen Sie die globale Sammlung zurück</span><span class="sxs-lookup"><span data-stu-id="a9f2a-114">To reset the global collection</span></span>

  - <span data-ttu-id="a9f2a-115">Mit dem folgenden Befehl wird die globale Sammlung von A/V-Edge-Konfigurationseinstellungen zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="a9f2a-116">So entfernen Sie eine Sammlung aus dem Website Bereich</span><span class="sxs-lookup"><span data-stu-id="a9f2a-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="a9f2a-117">Mit diesem Befehl werden die Konfigurationseinstellungen für A/V-Edge entfernt, die auf die Redmond-Website angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="a9f2a-118">So entfernen Sie eine Sammlung aus dem Dienstbereich</span><span class="sxs-lookup"><span data-stu-id="a9f2a-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="a9f2a-119">Mit diesem Befehl werden die auf die A/V-Edgeserver-ATL-Edge-001.litwareinc.com angewendeten Einstellungen entfernt:</span><span class="sxs-lookup"><span data-stu-id="a9f2a-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9f2a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9f2a-120">See Also</span></span>


[<span data-ttu-id="a9f2a-121">Zurückgeben von A/V-Edgeserver-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f2a-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="a9f2a-122">Erstellen oder Ändern einer Sammlung von a/V-Edgeserver-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f2a-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="a9f2a-123">Audio/Video-Edgeserver (A/V) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f2a-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="a9f2a-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a9f2a-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

