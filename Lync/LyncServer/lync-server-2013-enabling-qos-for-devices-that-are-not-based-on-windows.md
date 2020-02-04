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
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="9efae-102">Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren</span><span class="sxs-lookup"><span data-stu-id="9efae-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9efae-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9efae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9efae-104">Wenn Sie Microsoft lync Server 2013 installieren, wird Quality of Service (QoS) nicht für alle in Ihrer Organisation verwendeten Geräte aktiviert, die ein anderes Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="9efae-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="9efae-105">Sie können dies überprüfen, indem Sie in der lync Server 2013-Verwaltungsshell den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="9efae-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="9efae-106">Angenommen, Sie haben keine Änderungen an Ihren Medien Konfigurationseinstellungen vorgenommen, sollten Sie Informationen ähnlich wie in diesem Fall wieder finden:</span><span class="sxs-lookup"><span data-stu-id="9efae-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="9efae-107">Wenn die EnableQoS-Eigenschaft auf "false" (wie in der vorhergehenden Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9efae-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="9efae-108">QoS ist standardmäßig für lync Phone Edition-Geräte aktiviert. Es ist jedoch möglich, die Quality of Service für lync Phone Edition zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9efae-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="9efae-109">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um Quality of Service im globalen Bereich zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9efae-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="9efae-110">Der obige Befehl aktiviert QoS im globalen Bereich; Beachten Sie jedoch, dass die Einstellungen für die Medienkonfiguration auch auf den Website Bereich angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9efae-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="9efae-111">Wenn Sie die Dienstqualität für eine Website aktivieren müssen, müssen Sie beim Aufrufen von "CsMediaConfiguration" die Identität der Konfigurationseinstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="9efae-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="9efae-112">Mit diesem Befehl wird beispielsweise QoS für die Website "Redmond" aktiviert:</span><span class="sxs-lookup"><span data-stu-id="9efae-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="9efae-113">Müssen Sie QoS im Website Bereich aktivieren?</span><span class="sxs-lookup"><span data-stu-id="9efae-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="9efae-114">Das hängt davon ab.</span><span class="sxs-lookup"><span data-stu-id="9efae-114">That depends.</span></span> <span data-ttu-id="9efae-115">Dem Website Bereich zugewiesene Einstellungen haben Vorrang vor den dem globalen Bereich zugewiesenen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9efae-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="9efae-116">Angenommen, Sie haben QoS im globalen Bereich aktiviert, aber für den Website Bereich deaktiviert (für die Website "Redmond"). In diesem Fall ist die Dienstqualität für die Website "Redmond" deaktiviert; Das liegt daran, dass die Websiteeinstellungen Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="9efae-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="9efae-117">Um QoS für die Redmond-Website zu aktivieren, müssen Sie die Medien Konfigurationseinstellungen verwenden, die auf diese Website angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9efae-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="9efae-118">Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="9efae-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="9efae-119">Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen.</span><span class="sxs-lookup"><span data-stu-id="9efae-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="9efae-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9efae-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="9efae-121">Dadurch haben Sie die Möglichkeit, QoS in einigen Teilen Ihres Netzwerks (beispielsweise auf der Website "Redmond") zu implementieren, während Sie die Dienstqualität für andere Teile Ihres Netzwerks deaktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="9efae-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="9efae-122">QoS kann nur mithilfe von Windows PowerShell aktiviert und deaktiviert werden diese Optionen stehen in der lync Server-Systemsteuerung nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9efae-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

