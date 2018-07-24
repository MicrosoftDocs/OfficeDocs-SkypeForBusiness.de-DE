---
title: Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Add-Ins für Chatrooms Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: f96f000c4ac3a78f6ca3ba4972f295e45128ce50
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967733"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="239c8-103">Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="239c8-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="239c8-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von Add-Ins für Chatrooms Persistent Chat Server in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="239c8-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="239c8-105">-Add-ins werden verwendet, um die Erfahrung in Raum durch Zuordnen von URLs zu Chatrooms zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="239c8-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="239c8-106">Diese URLs werden im Erweiterbarkeit Client Unterhaltung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="239c8-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="239c8-107">Ein typisches Add-in gehören eine URL, die auf einer Silverlight-Anwendung, die fängt ab, wenn ein Aktienticker in einem Chatroom gesendet wurde, und den vordefinierten Verlauf im Bereich Erweiterbarkeit zeigt zeigen.</span><span class="sxs-lookup"><span data-stu-id="239c8-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="239c8-108">Weitere Beispiele umfassen Einbetten einer OneNote 2013 URL im Chatroom als ein Add-in einige freigegebenen Kontext, beispielsweise "Oben unter Sicherheitsgesichtspunkten" oder "Thema des Tages".</span><span class="sxs-lookup"><span data-stu-id="239c8-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="239c8-109">Bevor Benutzer ein Add-In im Client sehen können, müssen sie es der Liste registrierter Add-Ins hinzufügen und Chatroom-Manager oder -Ersteller müssen es Räumen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="239c8-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="239c8-110">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="239c8-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="239c8-111">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="239c8-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="239c8-112">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="239c8-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="239c8-113">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="239c8-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="239c8-114">Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="239c8-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="239c8-115">So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="239c8-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="239c8-116">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="239c8-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="239c8-117">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="239c8-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="239c8-118">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.</span><span class="sxs-lookup"><span data-stu-id="239c8-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="239c8-119">Wählen Sie für Bereitstellungen mit mehreren Persistent Chat Server Pool den entsprechenden Pool aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="239c8-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="239c8-120">Klicken Sie auf der Seite **Add-In** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="239c8-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="239c8-121">Wählen Sie unter **Wählen Sie einen Dienst**Dienst entspricht dem Persistent Chat Server Pool, wenn Sie das Add-in erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="239c8-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="239c8-122">Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="239c8-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="239c8-123">Gehen Sie unter **Neues Add-In** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="239c8-123">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="239c8-124">Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.</span><span class="sxs-lookup"><span data-stu-id="239c8-124">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="239c8-p104">Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="239c8-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="239c8-127">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="239c8-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="239c8-128">Konfigurieren von Add-Ins mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="239c8-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="239c8-129">Sie können Add-Ins für Chatrooms mithilfe der Windows PowerShell-Cmdlets konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="239c8-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="239c8-130">Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="239c8-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="239c8-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="239c8-131">**Cmdlet**</span></span>|<span data-ttu-id="239c8-132">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="239c8-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="239c8-133">"New-cspersistentchataddin"</span><span class="sxs-lookup"><span data-stu-id="239c8-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="239c8-134">Erstellt ein neues Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="239c8-135">"Set-cspersistentchataddin"</span><span class="sxs-lookup"><span data-stu-id="239c8-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="239c8-136">Konfiguriert Einstellungen für ein vorhandenes Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="239c8-137">"Get-cspersistentchataddin"</span><span class="sxs-lookup"><span data-stu-id="239c8-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="239c8-138">Ruft Informationen über Add-Ins ab</span><span class="sxs-lookup"><span data-stu-id="239c8-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="239c8-139">"Remove-cspersistentchataddin"</span><span class="sxs-lookup"><span data-stu-id="239c8-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="239c8-140">Entfernt ein Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="239c8-141">Erstellt ein neues Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-141">Create a new add-in</span></span>

<span data-ttu-id="239c8-142">Sie können ein neues Add-in erstellen, mit dem Cmdlet **"New-cspersistentchataddin"** .</span><span class="sxs-lookup"><span data-stu-id="239c8-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="239c8-143">Dem folgenden Befehl wird beispielsweise ein neues Add-in (mit der Bezeichnung ITPersistentChatAddin) für den Pool Atl-Cs-001.contoso.com erstellt.</span><span class="sxs-lookup"><span data-stu-id="239c8-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="239c8-144">Der URL-Parameter und der Wert des Parameters http://atl-cs-001.contoso.com/itchat Geben Sie den Speicherort der Webseite das Add-in:</span><span class="sxs-lookup"><span data-stu-id="239c8-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="239c8-145">Konfiguriert Einstellungen für ein vorhandenes Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="239c8-146">Sie können für ein vorhandenes Add-in-Einstellungen konfigurieren, mit dem Cmdlet **"Set-cspersistentchataddin"** .</span><span class="sxs-lookup"><span data-stu-id="239c8-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="239c8-147">Der folgende Befehl wird beispielsweise die URL für den beständigen Chat-add-in ITPersistentChatAddin geändert.</span><span class="sxs-lookup"><span data-stu-id="239c8-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="239c8-148">In diesem Fall wird die URL in geänderthttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="239c8-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="239c8-149">Ruft Informationen über Add-Ins ab</span><span class="sxs-lookup"><span data-stu-id="239c8-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="239c8-p108">Mithilfe des Cmdlets **Get-CsPersistentChatAddin** können Sie Informationen über Add-Ins abrufen. Beispielsweise liefert der folgende Befehl Informationen über alle Add-Ins für beständigen Chat, die zur Verwendung in der Organisation konfiguriert wurden:</span><span class="sxs-lookup"><span data-stu-id="239c8-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="239c8-152">Entfernt ein Add-In</span><span class="sxs-lookup"><span data-stu-id="239c8-152">Remove an add-in</span></span>

<span data-ttu-id="239c8-153">Sie können ein Add-in mit dem Cmdlet **"Remove-cspersistentchataddin"** entfernen.</span><span class="sxs-lookup"><span data-stu-id="239c8-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="239c8-154">Beispielsweise entfernt der folgende Befehl das Add-In für beständigen Chat namens „ITChatAddin“ aus dem Pool „atl-cs-001.contoso.com“:</span><span class="sxs-lookup"><span data-stu-id="239c8-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


