---
title: Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Zusammenfassung: Erfahren Sie, wie KDS-Konfigurationseinstellungen in Skype für Business Server zu entfernen.'
ms.openlocfilehash: 2319cd8548b3f183af6e54bbe1f24870093ae641
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926550"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a11fe-103">Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a11fe-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a11fe-104">**Zusammenfassung:** Erfahren Sie, wie Sie KDS-Konfigurationseinstellungen in Skype für Business Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a11fe-p101">Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.</span><span class="sxs-lookup"><span data-stu-id="a11fe-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="a11fe-107">Bei der Installation von Skype für Business Server, einer einzelnen wird die globale Auflistung von KDS-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="a11fe-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="a11fe-108">Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a11fe-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="a11fe-109">Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="a11fe-110">Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a11fe-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="a11fe-111">Beachten Sie, dass Sie auch "die globalen Einstellungen löschen können".</span><span class="sxs-lookup"><span data-stu-id="a11fe-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="a11fe-112">Allerdings werden die globalen Einstellungen dabei nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="a11fe-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="a11fe-113">Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a11fe-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="a11fe-114">Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a11fe-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="a11fe-115">Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="a11fe-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="a11fe-116">Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a11fe-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="a11fe-117">In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a11fe-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="a11fe-118">Sie können KDS-Konfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung oder [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) -Cmdlet entfernen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a11fe-119">So entfernen Sie KDS-Konfigurationseinstellungen mit Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a11fe-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a11fe-120">Skype für Business Server-Systemsteuerung klicken Sie auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="a11fe-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="a11fe-p104">Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die Strg-Taste gedrückt und klicken Sie dann auf weitere Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="a11fe-123">Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a11fe-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="a11fe-124">Die Skype für Dialogfeld Business Server-Systemsteuerung klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a11fe-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a11fe-125">Entfernen KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a11fe-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a11fe-126">Sie können Konfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet **Remove-CsCdrConfiguration** Aufzeichnung von kommunikationsdatensätzen löschen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="a11fe-127">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a11fe-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a11fe-128">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="a11fe-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a11fe-129">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="a11fe-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="a11fe-130">So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a11fe-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="a11fe-131">Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort „Redmond“ angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="a11fe-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="a11fe-132">So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf Standortebene angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="a11fe-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="a11fe-133">Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="a11fe-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="a11fe-134">So entfernen Sie alle KDS-Konfigurationseinstellungen, die die Aufzeichnung von Kommunikationsdatensätzen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="a11fe-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="a11fe-135">Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, bei denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="a11fe-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="a11fe-136">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a11fe-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a11fe-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a11fe-137">See also</span></span>

[<span data-ttu-id="a11fe-138">Manuelles Löschen der KDS- und Quality of Experience-Datenbanken in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a11fe-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

