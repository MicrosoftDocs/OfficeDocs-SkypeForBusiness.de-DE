---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Erfahren Sie, wie eine Archivierungskonfiguration in Skype für Business Server 2015 zu löschen.'
ms.openlocfilehash: 810c195f34a729218118744d4b6943e8dd60eb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server-2015"></a><span data-ttu-id="be896-103">Löschen einer Archivierungskonfiguration in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="be896-103">Delete an archiving configuration in Skype for Business Server 2015</span></span>

<span data-ttu-id="be896-104">**Zusammenfassung:** Erfahren Sie, wie eine Archivierungskonfiguration in Skype für Business Server 2015 zu löschen.</span><span class="sxs-lookup"><span data-stu-id="be896-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="be896-p101">Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="be896-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="be896-107">Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="be896-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="be896-108">So löschen Sie eine Archivierungskonfiguration mit der Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="be896-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="be896-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="be896-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="be896-110">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="be896-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="be896-111">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="be896-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="be896-112">Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="be896-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="be896-113">Sie können auch auf die globale Konfiguration klicken. Wählen Sie diese Option jedoch nur, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="be896-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="be896-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="be896-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="be896-115">Löschen einer Archivierungskonfiguration mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be896-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="be896-116">Sie können auch eine Archivierungskonfiguration löschen, mit dem Cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="be896-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="be896-p102">Zum Beispiel werden mit dem folgenden Befehl die Einstellungen der Archivierungskonfiguration gelöscht, die auf den Standort „Redmond“ angewendet werden. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, wird für Benutzer, für die zuvor die Standortrichtlinie galt, stattdessen automatisch die globale Archivierungsrichtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="be896-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="be896-119">Mit dem folgenden Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, die auf Standortebene angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="be896-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="be896-120">Mit dem nächsten Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, für die die Exchange-Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="be896-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="be896-121">Das Cmdlet **Remove-CsArchivingConfiguration** können auch die globalen Einstellungen auf die Standardwerte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="be896-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="be896-122">Nehmen wir beispielsweise an, dass Sie die Archivierung auf globaler Ebene Sofortnachrichtensitzung aktiviert haben; Der folgende Befehl wird den Wert auf None, wird der Standardwert zurückgesetzt, der Archivierung auf globaler Ebene deaktiviert wird:</span><span class="sxs-lookup"><span data-stu-id="be896-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="be896-123">Weitere Informationen finden Sie im Hilfethema zum [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="be896-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>