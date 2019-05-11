---
title: Löschen von QoE-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Zusammenfassung: Erfahren Sie, wie Quality of Experience (QoE)-Einstellungen in Skype für Business Server löschen.'
ms.openlocfilehash: e177b0870192eba996984e1eb3aae6d520db4661
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926627"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="71aba-103">Löschen von QoE-Konfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="71aba-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="71aba-104">**Zusammenfassung:** Erfahren Sie, wie Quality of Experience (QoE)-Einstellungen in Skype für Business Server löschen.</span><span class="sxs-lookup"><span data-stu-id="71aba-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="71aba-p101">QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="71aba-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="71aba-107">Bei der Installation von Skype für ein einzelnes Business Server ist die globale Auflistung von QoE-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="71aba-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="71aba-108">Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="71aba-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="71aba-109">Prinzipiell gilt, dass auf Standortebene konfigurierte Einstellungen Vorrang vor auf globaler Ebene konfigurierten Einstellungen haben.</span><span class="sxs-lookup"><span data-stu-id="71aba-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="71aba-110">Wenn Sie Einstellungen auf Standortebene löschen, wird QoE an diesem Standort unter Verwendung der globalen Einstellungen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="71aba-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="71aba-111">Beachten Sie, dass Sie auch "die globalen Einstellungen löschen können".</span><span class="sxs-lookup"><span data-stu-id="71aba-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="71aba-112">Allerdings werden die globalen Einstellungen dabei nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="71aba-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="71aba-113">Vielmehr werden alle Eigenschaften in dieser Auflistung auf ihre Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="71aba-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="71aba-114">Ein Beispiel: Angenommen, in einer Auflistung von QoE-Konfigurationseinstellungen ist standardmäßig die Bereinigung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="71aba-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="71aba-115">Sie ändern nun die globale Auflistung dahin gehend, dass Bereinigung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="71aba-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="71aba-116">Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="71aba-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="71aba-117">In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="71aba-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="71aba-118">Sie können die QoE-Konfigurationseinstellungen mithilfe der Skype Business Server-Systemsteuerung oder mit dem [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) -Cmdlet entfernen.</span><span class="sxs-lookup"><span data-stu-id="71aba-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="71aba-119">So löschen Sie QoE-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="71aba-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="71aba-p104">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="71aba-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="71aba-122">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="71aba-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="71aba-123">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="71aba-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="71aba-124">Klicken Sie auf der Seite **QoE-Daten** auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="71aba-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="71aba-125">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="71aba-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71aba-126">Entfernen der QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="71aba-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71aba-127">Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet **Remove-CsQoEConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="71aba-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="71aba-128">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="71aba-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71aba-129">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="71aba-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="71aba-130">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="71aba-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="71aba-131">So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="71aba-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="71aba-132">Mit diesem Befehl werden die QoE-Konfigurationseinstellungen entfernt, die auf den Standort Redmond angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="71aba-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="71aba-133">So entfernen Sie alle QoE-Konfigurationseinstellungen, die auf Standortebene angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="71aba-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="71aba-134">Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="71aba-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="71aba-135">So entfernen Sie alle QoE-Konfigurationseinstellungen, in denen QoE-Überwachung deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="71aba-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="71aba-136">Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, in denen die QoE-Überwachung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="71aba-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="71aba-137">Weitere Informationen hierzu finden Sie unter [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="71aba-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71aba-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71aba-138">See also</span></span>

[<span data-ttu-id="71aba-139">Manuelles Löschen der KDS- und Quality of Experience-Datenbanken in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="71aba-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

