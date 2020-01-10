---
title: Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Sammlung von trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels löschen.'
ms.openlocfilehash: 97a0820258a837968b88e6840232829f3ad11d21
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000995"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e7b39-103">Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7b39-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e7b39-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Sammlung von trunk-Konfigurationseinstellungen mithilfe des Skype for Business Server-Control Panels löschen.</span><span class="sxs-lookup"><span data-stu-id="e7b39-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e7b39-p101">SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="e7b39-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="e7b39-107">Ob Medienumgehung für die Trunks aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7b39-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="e7b39-108">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7b39-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="e7b39-109">Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e7b39-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="e7b39-110">Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7b39-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e7b39-111">Diese globale Auflistung von Einstellungen kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e7b39-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="e7b39-112">Sie können jedoch die Skype for Business Server-Systemsteuerung oder das Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) verwenden, um die Eigenschaften in der globalen Sammlung auf ihre Standardwerte zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e7b39-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="e7b39-113">Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e7b39-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="e7b39-p103">Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e7b39-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="e7b39-p104">Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e7b39-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="e7b39-118">Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e7b39-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e7b39-119">So entfernen Sie die trunk-Konfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e7b39-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e7b39-120">Klicken Sie in der Skype for Business Server-Systemsteuerung auf **VoIP-Routing** und dann auf **trunk-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="e7b39-p105">Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten** und dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e7b39-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="e7b39-p106">Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="e7b39-125">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="e7b39-126">Klicken Sie im Dialogfeld **Skype for Business Server Control Panel** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="e7b39-127">Wenn Sie es sich anders überlegen und die Sammlung nicht löschen möchten, klicken Sie auf **Commit** , und klicken Sie dann auf **alle nicht übernommenen Änderungen abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="e7b39-128">Wenn das Dialogfeld " **Skype for Business Server Control Panel** " angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b39-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="e7b39-129">Entfernen von trunk-Konfigurationseinstellungen mithilfe von Skype for Business Server-Verwaltungsshell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e7b39-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="e7b39-130">Sie können trunk-Konfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell und des Cmdlets **Remove-CsTrunkConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="e7b39-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="e7b39-131">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung der Skype for Business Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7b39-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="e7b39-132">So entfernen Sie eine angegebene Auflistung von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e7b39-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="e7b39-133">Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e7b39-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="e7b39-134">So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="e7b39-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="e7b39-135">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e7b39-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="e7b39-136">So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="e7b39-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="e7b39-137">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="e7b39-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="e7b39-138">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e7b39-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

