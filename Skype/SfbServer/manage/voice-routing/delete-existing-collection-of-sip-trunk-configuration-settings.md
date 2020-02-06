---
title: Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. '
ms.openlocfilehash: 5be81bccdb5df94cff4e8a2a13aaabb20dfdce29
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816975"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9121e-103">Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9121e-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="9121e-104">SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="9121e-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="9121e-105">Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="9121e-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="9121e-106">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9121e-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="9121e-107">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9121e-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="9121e-108">Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9121e-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="9121e-109">Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="9121e-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9121e-110">Diese globale Auflistung von Einstellungen kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9121e-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="9121e-111">Sie können jedoch das Skype for Business servercontrol-Panel oder das Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) verwenden, um die Eigenschaften in der globalen Sammlung auf ihre Standardwerte zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="9121e-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="9121e-112">Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9121e-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="9121e-p103">Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9121e-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="9121e-p104">Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9121e-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="9121e-117">Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9121e-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="9121e-118">**So entfernen Sie die trunk-Konfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung**</span><span class="sxs-lookup"><span data-stu-id="9121e-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="9121e-119">Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9121e-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="9121e-120">Wählen Sie auf der Registerkarte **trunk Configuration** die Sammlung der zu löschenden SIP-Trunk-Konfigurationseinstellungen aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9121e-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="9121e-121">Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="9121e-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="9121e-p106">Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9121e-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="9121e-124">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9121e-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="9121e-125">Klicken Sie im Dialogfeld **Skype for Business Server Control Panel** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9121e-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="9121e-126">Wenn Sie es sich anders überlegen und die Sammlung nicht löschen möchten, klicken Sie auf **Commit**, und klicken Sie dann auf **alle nicht übernommenen Änderungen abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="9121e-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="9121e-127">Wenn das Dialogfeld " **Skype for Business Server Control Panel** " angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9121e-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9121e-128">Entfernen von trunk-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9121e-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="9121e-129">Sie können trunk-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsTrunkConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="9121e-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="9121e-130">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="9121e-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="9121e-131">**So entfernen Sie eine angegebene Auflistung von Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="9121e-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="9121e-132">Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="9121e-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="9121e-133">**So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden**</span><span class="sxs-lookup"><span data-stu-id="9121e-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="9121e-134">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="9121e-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="9121e-135">**So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist**</span><span class="sxs-lookup"><span data-stu-id="9121e-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="9121e-136">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="9121e-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="9121e-137">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9121e-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
