---
title: Aktivieren von QoS für Windows-fremde Geräte
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Hier erfahren Sie, wie Sie QoS für Geräte in Ihrer Organisation verwendeten aktivieren, die ein Betriebssystem als Windows verwenden.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232713"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="ea78b-103">Aktivieren von QoS in Skype für Business Server für Geräte, die nicht auf Windows basieren</span><span class="sxs-lookup"><span data-stu-id="ea78b-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="ea78b-104">Bei der Installation von Skype für Business Server wird Quality of Service (QoS) nicht für alle Geräte in Ihrer Organisation verwendeten aktiviert sein, die ein Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea78b-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="ea78b-105">Sie können dies überprüfen, durch den folgenden Befehl aus, in der Skype für Business ServerManagement Shell ausführen:</span><span class="sxs-lookup"><span data-stu-id="ea78b-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="ea78b-106">Vorausgesetzt, dass Sie keine Änderungen an den medienkonfigurationseinstellungen vorgenommen haben, sollten Sie ähnliche Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="ea78b-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="ea78b-107">Wenn die EnableQoS-Eigenschaft auf False (wie in der vorherigen Ausgabe), das heißt festgelegt ist, Quality of Service nicht aktiviert ist für Computer und Geräte, die ein Betriebssystem als Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea78b-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="ea78b-108">Um Quality of Service auf globaler Ebene zu aktivieren, führen Sie den folgenden Befehl aus, in der Skype für Business Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="ea78b-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ea78b-109">Mit dem vorstehende Befehl können QoS auf globaler Ebene. jedoch ist es wichtig zu beachten, dass medienkonfigurationseinstellungen auch, die auf Standortebene angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ea78b-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="ea78b-110">Wenn Sie Quality of Service für eine Website aktivieren möchten, müssen Sie die Identität der Konfigurationseinstellungen für die einbeziehen, beim Aufruf von Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ea78b-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="ea78b-111">Beispielsweise kann mit diesem Befehl QoS für den Standort Redmond:</span><span class="sxs-lookup"><span data-stu-id="ea78b-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="ea78b-112">So aktivieren Sie QoS auf Standortebene muss?</span><span class="sxs-lookup"><span data-stu-id="ea78b-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="ea78b-113">Das ist unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="ea78b-113">That depends.</span></span> <span data-ttu-id="ea78b-114">Einstellungen, die auf Standortebene zugewiesen haben Vorrang vor Einstellungen auf globaler Ebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ea78b-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="ea78b-115">Angenommen Sie, Sie QoS auf globaler Ebene aktiviert, aber die auf Standortebene (für den Standort Redmond) deaktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ea78b-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="ea78b-116">In diesem Fall würde Quality of Service für den Standort Redmond deaktiviert werden. Dies liegt daran die Einstellungen Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="ea78b-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="ea78b-117">Zum Aktivieren von QoS für den Standort Redmond müssten Sie dazu mit der medienkonfigurationseinstellungen auf dieser Website angewendet.</span><span class="sxs-lookup"><span data-stu-id="ea78b-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="ea78b-118">Wenn Sie gleichzeitig QoS für alle medienkonfigurationseinstellungen (unabhängig vom Gültigkeitsbereich) aktivieren möchten, führen Sie folgenden Befehl in der LSkype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="ea78b-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="ea78b-119">Sie können QoS für Geräte deaktivieren, die ein Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea78b-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="ea78b-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea78b-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="ea78b-121">Dadurch werden die Möglichkeit zum Implementieren von QoS auf einige Teile des Netzwerks (beispielsweise auf den Standort Redmond) und dabei Quality of Service auf andere Teile des Netzwerks deaktiviert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="ea78b-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="ea78b-122">QoS kann nur aktiviert, und mithilfe von Windows PowerShell deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ea78b-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="ea78b-123">Diese Optionen sind nicht verfügbar in den Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ea78b-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


