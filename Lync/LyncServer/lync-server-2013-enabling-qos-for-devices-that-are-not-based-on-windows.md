---
title: 'Lync Server 2013: Aktivieren von QoS für Geräte, die nicht auf Windows basieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="4efdd-102">Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren</span><span class="sxs-lookup"><span data-stu-id="4efdd-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4efdd-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4efdd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4efdd-104">Wenn Sie Microsoft lync Server 2013 installieren, wird Quality of Service (QoS) für keine Geräte aktiviert, die in Ihrer Organisation verwendet werden, die ein anderes Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="4efdd-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="4efdd-105">Sie können dies überprüfen, indem Sie den folgenden Befehl in der lync Server 2013 Management-Shell ausführen:</span><span class="sxs-lookup"><span data-stu-id="4efdd-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="4efdd-106">Sofern Sie noch keine Änderungen an den Medienkonfigurationseinstellungen vorgenommen haben, sollten ähnliche Informationen wie die folgenden zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="4efdd-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="4efdd-107">Wenn die EnableQoS-Eigenschaft auf false (wie in der vorherigen Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte nicht aktiviert ist, die ein anderes Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="4efdd-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="4efdd-108">QoS ist für lync Phone Edition-Geräte standardmäßig aktiviert; Es ist jedoch möglich, die Dienstqualität für lync Phone Edition zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4efdd-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="4efdd-109">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die Dienstqualität auf globaler Ebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4efdd-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4efdd-p103">Mit dem obigen Befehl wird QoS auf globaler Ebene aktiviert. Es ist jedoch wichtig, dass die Medienkonfigurationseinstellungen auch auf Standortebene angewendet werden können. Wenn Sie QoS für einen Standort aktivieren möchten, müssen Sie beim Aufruf von Set-CsMediaConfiguration die Identität der Konfigurationseinstellungen angeben. Mit dem folgenden Befehl wird QoS beispielsweise für den Standort Redmond aktiviert:</span><span class="sxs-lookup"><span data-stu-id="4efdd-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="4efdd-p104">Müssen Sie QoS auf Standortebene aktivieren? Das kommt darauf an. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Angenommen, Sie haben QoS auf globaler Ebene aktiviert, aber auf Standortebene (für den Standort Redmond) deaktiviert. In diesem Fall wird QoS für den Standort Redmond deaktiviert, da die Standorteinstellungen Vorrang haben. Um QoS für den Standort Redmond zu aktivieren, müssen Sie entsprechende Medienkonfigurationseinstellungen auf den Standort anwenden.</span><span class="sxs-lookup"><span data-stu-id="4efdd-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="4efdd-118">Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="4efdd-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4efdd-119">Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen.</span><span class="sxs-lookup"><span data-stu-id="4efdd-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="4efdd-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4efdd-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="4efdd-121">Auf diese Weise können Sie QoS in einigen Bereichen des Netzwerks implementieren (z. B. für den Standort Redmond), während QoS für andere Bereiche des Netzwerks deaktiviert bleibt.</span><span class="sxs-lookup"><span data-stu-id="4efdd-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="4efdd-122">QoS kann nur mit Windows PowerShell aktiviert und deaktiviert werden, wenn diese Optionen im lync Server-Systemsteuerung nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4efdd-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

