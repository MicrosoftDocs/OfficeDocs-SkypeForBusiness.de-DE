---
title: Aktivieren von QoS für Windows-fremde Geräte
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Hier erfahren Sie, wie Sie QoS für in Ihrer Organisation verwendete Geräte aktivieren, die ein anderes Betriebssystem als Windows verwenden.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279410"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="ed300-103">Aktivieren von QoS in Skype for Business Server für Geräte, die nicht auf Windows basieren</span><span class="sxs-lookup"><span data-stu-id="ed300-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="ed300-104">Wenn Sie Skype for Business Server installieren, wird Quality of Service (QoS) nicht für alle in Ihrer Organisation verwendeten Geräte aktiviert, die ein anderes Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed300-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="ed300-105">Sie können dies überprüfen, indem Sie in der Skype for Business-Servermanagement-Shell den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ed300-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="ed300-106">Angenommen, Sie haben keine Änderungen an den Medien Konfigurationseinstellungen vorgenommen, sollten Sie Informationen ähnlich wie in diesem Fall zurück erhalten:</span><span class="sxs-lookup"><span data-stu-id="ed300-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="ed300-107">Wenn die EnableQoS-Eigenschaft auf "false" (wie in der vorhergehenden Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ed300-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="ed300-108">Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell aus, um Quality of Service auf globaler Ebene zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ed300-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ed300-109">Der obige Befehl aktiviert QoS im globalen Bereich; Beachten Sie jedoch, dass die Einstellungen für die Medienkonfiguration auch auf den Website Bereich angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ed300-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="ed300-110">Wenn Sie die Dienstqualität für eine Website aktivieren müssen, müssen Sie beim Aufrufen von "CsMediaConfiguration" die Identität der Konfigurationseinstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="ed300-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="ed300-111">Mit diesem Befehl wird beispielsweise QoS für die Website "Redmond" aktiviert:</span><span class="sxs-lookup"><span data-stu-id="ed300-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="ed300-112">Müssen Sie QoS im Website Bereich aktivieren?</span><span class="sxs-lookup"><span data-stu-id="ed300-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="ed300-113">Das hängt davon ab.</span><span class="sxs-lookup"><span data-stu-id="ed300-113">That depends.</span></span> <span data-ttu-id="ed300-114">Dem Website Bereich zugewiesene Einstellungen haben Vorrang vor den dem globalen Bereich zugewiesenen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ed300-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="ed300-115">Angenommen, Sie haben QoS im globalen Bereich aktiviert, aber für den Website Bereich deaktiviert (für die Website "Redmond").</span><span class="sxs-lookup"><span data-stu-id="ed300-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="ed300-116">In diesem Fall ist die Dienstqualität für die Website "Redmond" deaktiviert; Das liegt daran, dass die Websiteeinstellungen Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="ed300-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="ed300-117">Um QoS für die Website "Redmond" zu aktivieren, müssen Sie die Medien Konfigurationseinstellungen verwenden, die auf diese Website angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ed300-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="ed300-118">Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der LSkype for Business Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="ed300-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ed300-119">Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen.</span><span class="sxs-lookup"><span data-stu-id="ed300-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="ed300-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed300-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="ed300-121">Dadurch haben Sie die Möglichkeit, QoS in einigen Teilen Ihres Netzwerks (beispielsweise auf der Website "Redmond") zu implementieren, während Sie die Dienstqualität für andere Teile Ihres Netzwerks deaktiviert lassen.</span><span class="sxs-lookup"><span data-stu-id="ed300-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="ed300-122">QoS kann nur mithilfe von Windows PowerShell aktiviert und deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ed300-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="ed300-123">Diese Optionen stehen im Skype Control Panel für Unternehmen-Server nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ed300-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


