---
title: Löschen einer Archivierungskonfiguration in Skype for Business Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.'
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818937"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="30cf9-103">Löschen einer Archivierungskonfiguration in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30cf9-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="30cf9-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungskonfiguration in Skype for Business Server löschen.</span><span class="sxs-lookup"><span data-stu-id="30cf9-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="30cf9-p101">Eine Standort- oder Benutzerkonfiguration kann gelöscht werden. Die globale Konfiguration kann jedoch nicht gelöscht werden. Wenn Sie die globale Konfiguration löschen, werden die Standardwerte automatisch wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="30cf9-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="30cf9-107">Löschen einer Archivierungskonfiguration mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="30cf9-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="30cf9-108">So löschen Sie eine Archivierungskonfiguration mit der Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="30cf9-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="30cf9-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="30cf9-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="30cf9-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="30cf9-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="30cf9-111">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="30cf9-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="30cf9-112">Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="30cf9-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30cf9-113">Sie können auch auf die globale Konfiguration klicken. Wählen Sie diese Option jedoch nur, wenn Sie die globale Konfiguration auf die Standardwerte zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="30cf9-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="30cf9-114">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="30cf9-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="30cf9-115">Löschen einer Archivierungskonfiguration mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30cf9-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="30cf9-116">Sie können eine Archivierungskonfiguration auch mithilfe des Cmdlets **Remove-CsArchivingConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="30cf9-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="30cf9-p102">Zum Beispiel werden mit dem folgenden Befehl die Einstellungen der Archivierungskonfiguration gelöscht, die auf den Standort „Redmond“ angewendet werden. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, wird für Benutzer, für die zuvor die Standortrichtlinie galt, stattdessen automatisch die globale Archivierungsrichtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="30cf9-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="30cf9-119">Mit dem folgenden Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, die auf Standortebene angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="30cf9-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="30cf9-120">Mit dem nächsten Befehl werden alle Einstellungen der Archivierungskonfiguration entfernt, für die die Exchange-Archivierung deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="30cf9-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="30cf9-121">Sie können auch das Cmdlet **Remove-CsArchivingConfiguration** verwenden, um die globalen Einstellungen auf Standardwerte zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="30cf9-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="30cf9-122">Angenommen, Sie haben die Chat-Sitzungs Archivierung auf globaler Ebene aktiviert. mit dem folgenden Befehl wird der Wert auf den Standardwert None zurückgesetzt, wodurch die Archivierung auf globaler Ebene deaktiviert wird:</span><span class="sxs-lookup"><span data-stu-id="30cf9-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="30cf9-123">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="30cf9-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
