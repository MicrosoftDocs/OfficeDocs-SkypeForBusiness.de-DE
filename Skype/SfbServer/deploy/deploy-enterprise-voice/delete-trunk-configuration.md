---
title: Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Auflistung von trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung zu löschen.'
ms.openlocfilehash: 27e022588798e848cf690bb643d921e46d827b39
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890537"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="23e1c-103">Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="23e1c-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="23e1c-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Auflistung von trunkkonfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="23e1c-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="23e1c-p101">SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network, Festnetz), einer IP-Nebenstellenanlage (Public Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="23e1c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="23e1c-107">Ob Medienumgehung für die Trunks aktiviert werden soll</span><span class="sxs-lookup"><span data-stu-id="23e1c-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="23e1c-108">Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="23e1c-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="23e1c-109">Ob SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden Trunk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="23e1c-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="23e1c-110">Wenn Sie Skype für Business Server installieren, wird eine globale Auflistung von SIP-trunkkonfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="23e1c-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="23e1c-111">Diese globale Auflistung von Einstellungen kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="23e1c-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="23e1c-112">Die Skype für Business Server-Systemsteuerung oder [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) -Cmdlet können Sie jedoch "die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückgesetzt".</span><span class="sxs-lookup"><span data-stu-id="23e1c-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="23e1c-113">Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="23e1c-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="23e1c-p103">Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="23e1c-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="23e1c-p104">Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="23e1c-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="23e1c-118">Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="23e1c-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="23e1c-119">So entfernen Sie Trunk-Konfigurationseinstellungen mit Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="23e1c-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="23e1c-120">Klicken Sie in Skype Business Server-Systemsteuerung auf **VoIP-Routing** , und klicken Sie dann auf **Trunkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="23e1c-p105">Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten** und dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="23e1c-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="23e1c-p106">Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="23e1c-125">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="23e1c-126">Klicken Sie im Dialogfeld **Skype Business Server-Systemsteuerung** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="23e1c-127">Wenn Sie sich umentscheiden und die Auflistung nicht löschen möchten, klicken Sie auf **Commit ausführen** und anschließend auf **Alle noch nicht übernommenen Änderungen verwerfen**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="23e1c-128">Wenn das Dialogfeld **Skype Business Server-Systemsteuerung** angezeigt wird, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="23e1c-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="23e1c-129">Entfernen der Trunkkonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="23e1c-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="23e1c-130">Sie können mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Remove-CsTrunkConfiguration** trunkkonfigurationseinstellungen löschen.</span><span class="sxs-lookup"><span data-stu-id="23e1c-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="23e1c-131">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Skype für Business Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="23e1c-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="23e1c-132">So entfernen Sie eine angegebene Auflistung von Einstellungen</span><span class="sxs-lookup"><span data-stu-id="23e1c-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="23e1c-133">Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="23e1c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="23e1c-134">So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="23e1c-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="23e1c-135">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="23e1c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="23e1c-136">So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="23e1c-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="23e1c-137">Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="23e1c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="23e1c-138">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23e1c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

