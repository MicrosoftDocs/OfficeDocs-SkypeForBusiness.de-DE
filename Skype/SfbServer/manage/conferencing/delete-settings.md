---
title: Löschen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Zusammenfassung: Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="08745-103">Löschen der Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="08745-103">Delete meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="08745-104">**Zusammenfassung:** Informationen zum Löschen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="08745-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="08745-105">Sie können löschen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="08745-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="08745-p101">Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="08745-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="08745-108">Löschen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="08745-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="08745-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="08745-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="08745-110">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="08745-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="08745-111">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="08745-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="08745-112">Klicken Sie in der Liste der Besprechungskonfigurationen auf die Standort- oder Poolkonfiguration, die Sie löschen möchten, klicken Sie dann auf **Bearbeiten** und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="08745-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="08745-113">Löschen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="08745-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="08745-114">Verwenden Sie das Cmdlet **Remove-CsMeetingConfiguration**, um Besprechungseinstellungen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="08745-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="08745-115">Der folgende Befehl löscht die Besprechungskonfigurationseinstellungen des Standorts Redmond:</span><span class="sxs-lookup"><span data-stu-id="08745-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="08745-116">Der nächste Befehl löscht alle Besprechungskonfigurationseinstellungen des Standortbereichs:</span><span class="sxs-lookup"><span data-stu-id="08745-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="08745-117">Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="08745-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

