---
title: Ändern der Einstellungen für die besprechungskonfiguration in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Einstellungen für die besprechungskonfiguration in Skype for Business Server ändern.'
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992852"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="31b17-103">Ändern der Einstellungen für die besprechungskonfiguration in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31b17-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="31b17-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie die Konfigurationseinstellungen für Besprechungen in Skype for Business Server ändern.</span><span class="sxs-lookup"><span data-stu-id="31b17-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="31b17-105">Sie können die Einstellungen für die besprechungskonfiguration über die Skype for Business Server-Systemsteuerung oder über die Skype for Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="31b17-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="31b17-106">Ändern der Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="31b17-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="31b17-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="31b17-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="31b17-108">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="31b17-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="31b17-109">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="31b17-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="31b17-110">Klicken Sie in der Liste mit den Besprechungskonfigurationen auf die Konfiguration, die Sie ändern möchten, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="31b17-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="31b17-111">Ändern Sie in **Besprechungskonfiguration bearbeiten** beliebige Konfigurationseinstellungen. Hiervon ausgenommen ist der Konfigurationsname, dieser kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="31b17-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="31b17-112">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="31b17-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="31b17-113">Ändern der Einstellungen für die besprechungskonfiguration mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="31b17-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="31b17-114">Verwenden Sie Das Cmdlet **Set-CsMeetingConfiguration**, um die Besprechungskonfigurationseinstellungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="31b17-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="31b17-p101">Über den Befehl im folgenden Beispiel werden die Konfigurationseinstellungen für Besprechungen geändert, die dem Standort „Redmond“ (-Identity site:Redmond) zugewiesen sind. In diesem Fall wird der Wert der Eigenschaft „DesignateAsPresenter“ auf „Everyone“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31b17-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="31b17-117">Weitere Informationen, einschließlich einer vollständigen Liste der Parameter, finden Sie unter [Satz-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="31b17-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

