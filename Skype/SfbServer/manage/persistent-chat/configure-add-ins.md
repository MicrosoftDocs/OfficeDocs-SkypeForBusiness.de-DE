---
title: Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Add-Ins für Chatrooms für beständigen Chat-Server in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: 08e71ab989734572d9d44f0bdb42c01511e47f4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279326"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="b0954-103">Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0954-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b0954-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Add-Ins für Chatrooms für beständigen Chat-Server in Skype for Business Server 2015 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0954-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b0954-105">Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern, indem Sie URLs mit Chatrooms verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b0954-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="b0954-106">Diese URLs werden im Bereich für die Erweiterbarkeit von Client Unterhaltungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0954-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="b0954-107">Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Börsenticker in einem Chatroom bereitgestellt wird, und den Aktienverlauf im Bereich "Erweiterbarkeit" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b0954-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="b0954-108">Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen freigegebenen Kontext einzubeziehen, beispielsweise "Top of mindi" oder "Tagesthema".</span><span class="sxs-lookup"><span data-stu-id="b0954-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="b0954-109">Bevor Benutzer ein Add-In im Client sehen können, müssen sie es der Liste registrierter Add-Ins hinzufügen und Chatroom-Manager oder -Ersteller müssen es Räumen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b0954-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0954-110">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0954-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b0954-111">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b0954-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="b0954-112">Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="b0954-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="b0954-113">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="b0954-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="b0954-114">Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b0954-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="b0954-115">So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="b0954-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="b0954-116">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b0954-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b0954-117">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="b0954-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b0954-118">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.</span><span class="sxs-lookup"><span data-stu-id="b0954-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="b0954-119">Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="b0954-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="b0954-120">Klicken Sie auf der Seite **Add-In** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="b0954-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="b0954-121">Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="b0954-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="b0954-122">Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0954-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="b0954-123">Gehen Sie unter **Neues Add-In** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b0954-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="b0954-124">Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.</span><span class="sxs-lookup"><span data-stu-id="b0954-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="b0954-p104">Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0954-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="b0954-127">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b0954-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="b0954-128">Konfigurieren von Add-Ins mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0954-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="b0954-p105">Sie können Add-Ins für Chatrooms mithilfe der Windows PowerShell-Cmdlets konfigurieren. Ausführliche Informationen zur Syntax einschließlich aller verfügbaren Parameter finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="b0954-p105">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets. For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="b0954-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="b0954-131">**Cmdlet**</span></span>|<span data-ttu-id="b0954-132">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b0954-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0954-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="b0954-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="b0954-134">Erstellt ein neues Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="b0954-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="b0954-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="b0954-136">Konfiguriert Einstellungen für ein vorhandenes Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="b0954-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="b0954-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="b0954-138">Ruft Informationen über Add-Ins ab</span><span class="sxs-lookup"><span data-stu-id="b0954-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="b0954-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="b0954-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="b0954-140">Entfernt ein Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="b0954-141">Erstellt ein neues Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-141">Create a new add-in</span></span>

<span data-ttu-id="b0954-142">Sie können ein neues Add-in mit dem Cmdlet **New-CsPersistentChatAddin** erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0954-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="b0954-143">Mit dem folgenden Befehl wird beispielsweise ein neues Add-in (mit dem Namen ITPersistentChatAddin) für den Pool ATL-CS-001.contoso.com erstellt.</span><span class="sxs-lookup"><span data-stu-id="b0954-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="b0954-144">Der URL-Parameter und der Parameter http://atl-cs-001.contoso.com/itchat Wert geben den Speicherort der Webseite des Add-Ins an:</span><span class="sxs-lookup"><span data-stu-id="b0954-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="b0954-145">Konfiguriert Einstellungen für ein vorhandenes Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="b0954-146">Sie können die Einstellungen für ein vorhandenes Add-in mithilfe des Cmdlets " **Satz-CsPersistentChatAddIn** " konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0954-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="b0954-147">Mit dem folgenden Befehl wird beispielsweise die URL geändert, die dem Add-in ITPersistentChatAddin für beständigen Chat zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b0954-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="b0954-148">In diesem Fall wird die URL inhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="b0954-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="b0954-149">Ruft Informationen über Add-Ins ab</span><span class="sxs-lookup"><span data-stu-id="b0954-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="b0954-p108">Mithilfe des Cmdlets **Get-CsPersistentChatAddin** können Sie Informationen über Add-Ins abrufen. Beispielsweise liefert der folgende Befehl Informationen über alle Add-Ins für beständigen Chat, die zur Verwendung in der Organisation konfiguriert wurden:</span><span class="sxs-lookup"><span data-stu-id="b0954-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="b0954-152">Entfernt ein Add-In</span><span class="sxs-lookup"><span data-stu-id="b0954-152">Remove an add-in</span></span>

<span data-ttu-id="b0954-153">Mithilfe des Cmdlets **Remove-CsPersistentChatAddIn** können Sie ein Add-in entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0954-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="b0954-154">Beispielsweise entfernt der folgende Befehl das Add-In für beständigen Chat namens „ITChatAddin“ aus dem Pool „atl-cs-001.contoso.com“:</span><span class="sxs-lookup"><span data-stu-id="b0954-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


