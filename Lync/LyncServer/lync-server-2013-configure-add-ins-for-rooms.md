---
title: 'Lync Server 2013: Konfigurieren von Add-Ins für Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a9e7a2c947d18e8359e2199ec8c3e40e00ed98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="d51b1-102">Konfigurieren von Add-Ins für Chatrooms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d51b1-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d51b1-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d51b1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d51b1-104">In lync Server 2013 Systemsteuerung können Sie den Abschnitt **Add-in** der Seite **beständiger Chat** verwenden, um URLs mit beständigen Chatrooms zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d51b1-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="d51b1-105">Diese URLs werden im lync 2013-Client im Chatroom im Bereich für die Erweiterbarkeit von Unterhaltungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b1-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="d51b1-106">Ein Administrator muss der Liste der registrierten Add-Ins Add-Ins hinzufügen, und Chatroommanager/-Ersteller müssen einem der registrierten Add-ins Räume zuordnen, bevor Benutzer dieses Upgrade in Ihrem lync 2013-Client sehen können.</span><span class="sxs-lookup"><span data-stu-id="d51b1-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="d51b1-107">Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d51b1-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="d51b1-108">Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung verweist, die abfängt, wenn ein Börsenticker in einen Chatroom gebucht wird, und den Verlaufs Verlauf im Erweiterungsbereich anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b1-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="d51b1-109">Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen gemeinsamen Kontext wie "Top of Mind" oder "Topic des Tages" einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="d51b1-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="d51b1-110">So konfigurieren Sie Add-ins für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="d51b1-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="d51b1-111">Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d51b1-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d51b1-112">Wählen Sie im **Startmenü** die lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein.</span><span class="sxs-lookup"><span data-stu-id="d51b1-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="d51b1-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d51b1-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d51b1-114">Sie können auch Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="d51b1-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d51b1-115">Ausführliche Informationen finden Sie unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mit Windows PowerShell-Cmdlets</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d51b1-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="d51b1-116">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.</span><span class="sxs-lookup"><span data-stu-id="d51b1-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="d51b1-117">Wählen Sie für mehrere Server Pool Bereitstellungen für beständigen Chat den entsprechenden Pool aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="d51b1-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="d51b1-118">Klicken Sie auf der Seite **Add-In** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d51b1-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="d51b1-119">Wählen Sie unter **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="d51b1-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="d51b1-120">Add-Ins können nicht von einem Pool in einen anderen Pool verschoben oder von unterschiedlichen Pools gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="d51b1-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="d51b1-121">Führen Sie unter **Neues Add-In** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d51b1-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="d51b1-122">Geben Sie unter **Name** einen Namen für das neue Add-In an.</span><span class="sxs-lookup"><span data-stu-id="d51b1-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="d51b1-p106">Geben Sie unter **URL** die URL an, die dem Add-In zugeordnet werden soll. Die URLs sind auf die Protokolle "http" und "https" beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d51b1-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="d51b1-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d51b1-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d51b1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d51b1-126">See Also</span></span>


[<span data-ttu-id="d51b1-127">Öffnen lync Server 2013 Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="d51b1-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="d51b1-128">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d51b1-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

