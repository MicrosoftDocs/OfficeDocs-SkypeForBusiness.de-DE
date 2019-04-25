---
title: Verwalten von Archivierungsoptionen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Archivierungsoptionen für Skype für Business Server.'
ms.openlocfilehash: db0fbe113f38065e85419b05d39fd0176b5ba845
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232368"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="eb65e-103">Verwalten von Archivierungsoptionen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="eb65e-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="eb65e-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von Archivierungsoptionen für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb65e-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="eb65e-105">Erstkonfiguration Archivierung bei der Bereitstellung, aber Sie können ändern, hinzufügen und Löschen von Konfigurationen nach der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="eb65e-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="eb65e-106">Archivierungsoptionen zu bestimmen, ob:</span><span class="sxs-lookup"><span data-stu-id="eb65e-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="eb65e-107">Archivierung aktivieren oder deaktivieren</span><span class="sxs-lookup"><span data-stu-id="eb65e-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="eb65e-108">Chatsitzungen archivieren</span><span class="sxs-lookup"><span data-stu-id="eb65e-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="eb65e-109">Webkonferenzsitzungen archivieren</span><span class="sxs-lookup"><span data-stu-id="eb65e-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="eb65e-110">Aktivitäten blockieren, wenn keine Archivierung verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="eb65e-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="eb65e-111">Exchange-Integration verwenden</span><span class="sxs-lookup"><span data-stu-id="eb65e-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="eb65e-112">Löschen und Exportieren von Daten einrichten</span><span class="sxs-lookup"><span data-stu-id="eb65e-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="eb65e-113">Sie können Konfigurationsoptionen auf den folgenden Ebenen festlegen:</span><span class="sxs-lookup"><span data-stu-id="eb65e-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="eb65e-114">Konfiguration auf globaler Ebene, die standardmäßig erstellt wird, bei der Bereitstellung von Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="eb65e-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="eb65e-115">Optionale Konfigurationen auf Standortebene, um anzugeben, wie die Archivierung für einen bestimmten Standort implementiert wird</span><span class="sxs-lookup"><span data-stu-id="eb65e-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="eb65e-116">Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird</span><span class="sxs-lookup"><span data-stu-id="eb65e-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="eb65e-117">Standort- oder Poolkonfigurationen können gelöscht werden, nicht aber die globale Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eb65e-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="eb65e-118">Wenn Sie die globale Konfiguration löschen, wird sie automatisch auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="eb65e-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="eb65e-119">Weitere Informationen dazu, wie Sie die Archivierung Konfigurationen implementiert werden und die Hierarchie der Archivierungskonfigurationen, finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="eb65e-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="eb65e-120">Konfigurieren von Archivierungsoptionen mit der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="eb65e-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="eb65e-121">Sie können die Archivierungsoptionen wie folgt mit der Systemsteuerung konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="eb65e-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="eb65e-122">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="eb65e-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="eb65e-123">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eb65e-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="eb65e-124">Klicken Sie in der linken Navigationsleiste auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="eb65e-125">Konfigurieren von Archivierungsoptionen mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb65e-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="eb65e-126">Sie können die Archivierungsoptionen auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb65e-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="eb65e-127">Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="eb65e-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="eb65e-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="eb65e-128">**Cmdlet**</span></span>|<span data-ttu-id="eb65e-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eb65e-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb65e-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb65e-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="eb65e-131">Gibt Informationen zu den in Ihrer Organisation verwendeten Konfigurationseinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="eb65e-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="eb65e-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb65e-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="eb65e-133">Erstellt einen neuen Satz mit Chatnachrichteneinstellungen. Diese Einstellungen dienen zum Aktivieren bzw. Deaktivieren der automatischen Speicherung von Chatsitzungen. Sie ermöglichen ferner das Blockieren von Chatnachrichten, die nicht archiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb65e-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="eb65e-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb65e-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="eb65e-135">Entfernt die angegebene Auflistung von Archivierungseinstellungen. Archivierungseinstellungen dienen zum Aktivieren und Deaktivieren des automatischen Speicherns von Chatsitzungen sowie zum optionalen Sperren aller Chatnachrichten, die nicht archiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb65e-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="eb65e-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb65e-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="eb65e-137">Ändert eine bestehende Auflistung von Optionen zur Archivierungskonfiguration für Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="eb65e-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
