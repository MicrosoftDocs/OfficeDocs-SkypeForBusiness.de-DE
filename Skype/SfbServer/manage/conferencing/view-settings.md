---
title: Anzeigen von Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Zusammenfassung: Informationen zum Anzeigen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="0a5a0-103">Anzeigen von Konfigurationseinstellungen für Besprechungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a5a0-103">View meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0a5a0-104">**Zusammenfassung:** Informationen zum Anzeigen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0a5a0-105">Sie können anzeigen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0a5a0-106">Anzeigen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0a5a0-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="0a5a0-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5a0-107"></span></span>

1. <span data-ttu-id="0a5a0-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0a5a0-109">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0a5a0-110">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="0a5a0-111">Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="0a5a0-112">Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="0a5a0-113">**Bearbeiten Besprechungskonfiguration - \<Richtlinie\> ** die Einstellungen für die ausgewählte Richtlinie wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="0a5a0-114">Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [Create besprechungskonfigurationseinstellungen in Skype für Business Server 2015](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0a5a0-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server 2015](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0a5a0-115">Anzeigen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0a5a0-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="0a5a0-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5a0-116"></span></span>

<span data-ttu-id="0a5a0-117">Verwenden Sie Das Cmdlet **Get-CsMeetingConfiguration**, um Informationen über sämtliche Besprechungskonfigurationseinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a5a0-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="0a5a0-118">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="0a5a0-118">This command will return information similar to the following:</span></span>
  
```
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True

```

<span data-ttu-id="0a5a0-119">Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0a5a0-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

