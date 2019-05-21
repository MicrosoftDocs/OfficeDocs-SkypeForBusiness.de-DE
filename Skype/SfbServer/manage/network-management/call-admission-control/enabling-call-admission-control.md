---
title: Aktivieren der Anrufsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Nachdem Sie das CAC-Netzwerk (Call Admission Control) konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen."
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279550"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="b0e17-103">Aktivieren der Anrufsteuerung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b0e17-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="b0e17-104">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können.</span><span class="sxs-lookup"><span data-stu-id="b0e17-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="b0e17-105">Nachdem Sie das CAC-Netzwerk konfiguriert haben, müssen Sie CAC aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b0e17-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="b0e17-106">Dazu können Sie die Skype for Business Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0e17-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="b0e17-107">So aktivieren Sie CAC über das Skype Control Panel für Unternehmen-Server</span><span class="sxs-lookup"><span data-stu-id="b0e17-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b0e17-108">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b0e17-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0e17-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b0e17-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0e17-110">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="b0e17-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="b0e17-111">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b0e17-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="b0e17-112">Für die Bereitstellung von Skype for Business Server kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b0e17-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="b0e17-113">Sie können die globale Konfiguration nicht umbenennen.</span><span class="sxs-lookup"><span data-stu-id="b0e17-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="b0e17-114">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b0e17-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b0e17-115">Aktivieren Sie auf der Seite **globale Einstellungen bearbeiten** das Kontrollkästchen **Anruf Zulassungs Steuerung aktivieren** , und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b0e17-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="b0e17-116">Wenn Sie auf **Commit**klicken, führen Sie einen Test der Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="b0e17-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="b0e17-117">Das Dialogfeld **globale Einstellungen bearbeiten** wird geschlossen, und Sie kehren zur **globalen** Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="b0e17-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="b0e17-118">Sie erhalten eine Warnung, wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen festgestellt werden, die verhindern, dass Sie ordnungsgemäß funktionieren (Wenn beispielsweise alle Regionen über eine interregions Route nicht mit allen anderen Regionen verbunden sind).</span><span class="sxs-lookup"><span data-stu-id="b0e17-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="b0e17-119">Wenn Sie Änderungen an Ihrer Netzwerkkonfiguration vornehmen, können Sie die Überprüfungs Prüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit**klicken.</span><span class="sxs-lookup"><span data-stu-id="b0e17-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="b0e17-120">Sie müssen CAC nicht zuerst deaktivieren: lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b0e17-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="b0e17-121">Sie können dies jederzeit tun, ohne Konfigurationsänderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b0e17-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0e17-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0e17-122">See Also</span></span>

[<span data-ttu-id="b0e17-123">Planen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="b0e17-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="b0e17-124">Bereitstellen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="b0e17-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="b0e17-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0e17-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="b0e17-126">Satz-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0e17-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="b0e17-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0e17-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
