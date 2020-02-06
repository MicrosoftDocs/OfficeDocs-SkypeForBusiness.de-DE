---
title: Add-In für beständigen Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Sie können den Bereich "Add-in" auf der Seite "beständiger Chat" verwenden, um URLs mit beständigen Chatrooms zu verknüpfen. Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt. Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.
ms.openlocfilehash: 2122f07bb51167dbaea6eb7d0881443e1ff44575
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822568"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="e2407-105">Add-In für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="e2407-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="e2407-106">Sie können den Bereich " **Add-in** " auf der Seite " **beständiger Chat** " verwenden, um URLs mit beständigen Chatrooms zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e2407-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="e2407-107">Diese URLs werden im Client im Chatroom des Erweiterungsbereichs für Unterhaltungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e2407-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="e2407-108">Ein Administrator muss der Liste der registrierten Add-Ins weitere Add-Ins hinzufügen und Verwalter und Ersteller von Chatrooms müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer dieses Upgrade in ihrem Client sehen können.</span><span class="sxs-lookup"><span data-stu-id="e2407-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="e2407-109">Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e2407-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="e2407-110">Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Börsenticker in einem Chatroom bereitgestellt wird, und den Aktienverlauf im Bereich "Erweiterbarkeit" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e2407-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="e2407-111">Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen freigegebenen Kontext einzubeziehen, beispielsweise "Top of mindi" oder "Tagesthema".</span><span class="sxs-lookup"><span data-stu-id="e2407-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="e2407-112">Informationen zum Erstellen von Add-Ins für beständige Chatrooms finden Sie unter [Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e2407-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="e2407-113">Wenn Sie ein beständiger Chat-Administrator sind, können Sie Add-Ins mithilfe der Systemsteuerung oder Windows PowerShell-Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2407-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="e2407-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e2407-114">Tasks that you can perform</span></span>

<span data-ttu-id="e2407-115">Auf der Seite **Add-In** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e2407-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="e2407-116">Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2407-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="e2407-117">So konfigurieren Sie Add-ins für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e2407-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="e2407-118">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2407-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="e2407-119">Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e2407-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e2407-120">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="e2407-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e2407-121">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Systemsteuerung anwenden können, finden Sie unter [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="e2407-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="e2407-122">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.</span><span class="sxs-lookup"><span data-stu-id="e2407-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="e2407-123">Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="e2407-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="e2407-124">Klicken Sie auf der Seite **Add-In** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="e2407-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="e2407-125">Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="e2407-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="e2407-126">Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2407-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="e2407-127">Gehen Sie unter **Neues Add-In** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e2407-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="e2407-128">Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.</span><span class="sxs-lookup"><span data-stu-id="e2407-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="e2407-p107">Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2407-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="e2407-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e2407-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2407-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2407-132">See also</span></span>

<span data-ttu-id="e2407-133">Ausführliche Informationen zu den Features und Funktionen des beständigen Chat Servers finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)und [Verwalten des beständigen Chat Servers in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="e2407-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


