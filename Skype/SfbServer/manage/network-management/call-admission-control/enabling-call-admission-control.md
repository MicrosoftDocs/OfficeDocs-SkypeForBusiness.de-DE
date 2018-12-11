---
title: Aktivieren der anrufsteuerung
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Nachdem Sie das Anruf Admission Control (, CAC) Netzwerk konfigurieren, müssen Sie zum Erzwingen der Netzwerkbandbreite ist eingeschränkt CAC aktivieren."
ms.openlocfilehash: 9c264305a38bf4bf9ef3716c5df82d74155e8936
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222835"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="f32d1-103">Aktivieren der anrufsteuerung in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="f32d1-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="f32d1-104">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können.</span><span class="sxs-lookup"><span data-stu-id="f32d1-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="f32d1-105">Nachdem Sie das CAC Netzwerk konfiguriert haben, müssen Sie CAC zum Erzwingen der Netzwerkbandbreite ist eingeschränkt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f32d1-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="f32d1-106">Sie können die Skype Business Server-Systemsteuerung dazu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f32d1-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="f32d1-107">Zum Aktivieren der Anrufsteuerung aus der Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f32d1-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f32d1-108">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f32d1-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f32d1-109">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f32d1-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f32d1-110">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="f32d1-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="f32d1-111">Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** .</span><span class="sxs-lookup"><span data-stu-id="f32d1-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="f32d1-112">Nur ein Netzwerk kann für alle Skype für Business Server-Bereitstellung konfiguriert werden, sodass es nie mehr als eine Netzwerkkonfiguration in der Liste werden.</span><span class="sxs-lookup"><span data-stu-id="f32d1-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="f32d1-113">Die globale Konfiguration kann nicht umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="f32d1-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="f32d1-114">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f32d1-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f32d1-115">Kontrollkästchen Sie auf der Seite **Globale Einstellungen bearbeiten** das **anrufsteuerung aktivieren** , und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f32d1-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="f32d1-116">Wenn Sie auf **Commit ausführen**klicken, führen Sie einen Test der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f32d1-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="f32d1-117">Das **Globale Einstellungen bearbeiten** -Dialogfeld wird geschlossen, Sie auf der Seite **Global** zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f32d1-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="f32d1-118">Sie erhalten eine Warnung, wenn alle Fehler oder Inkonsistenzen in der Netzwerkkonfiguration, die verhindern, dass wird ordnungsgemäß ermittelt werden (z. B., wenn jeder Region nicht mit allen anderen Regionen über eine regionenübergreifende Route verbunden ist).</span><span class="sxs-lookup"><span data-stu-id="f32d1-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="f32d1-119">Wenn Sie Änderungen an der Netzwerkkonfiguration vornehmen, können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f32d1-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="f32d1-120">Sie müssen nicht zuerst deaktivieren, CAC: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f32d1-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="f32d1-121">Sie hierzu können Sie jederzeit ohne konfigurationsänderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f32d1-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f32d1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f32d1-122">See Also</span></span>

[<span data-ttu-id="f32d1-123">Planen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f32d1-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="f32d1-124">Bereitstellen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f32d1-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="f32d1-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f32d1-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="f32d1-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f32d1-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="f32d1-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="f32d1-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
