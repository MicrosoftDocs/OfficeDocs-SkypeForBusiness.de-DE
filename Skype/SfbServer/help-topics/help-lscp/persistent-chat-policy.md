---
title: Richtlinie für beständigen Chat
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
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Sie können die Seite "beständiger Chat" der Gruppe "beständiger Chat" verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung. Wenn der Server für beständigen Chat nach Richtlinie für einen Benutzer aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.
ms.openlocfilehash: 6692ef8314c3eb1ef38ade8cdbee26d3d76410ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822508"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="66ae7-104">Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="66ae7-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="66ae7-105">Sie können die Seite " **beständiger Chat** " der Gruppe " **beständiger Chat** " verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="66ae7-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="66ae7-106">Wenn der Server für beständigen Chat nach Richtlinie für einen Benutzer aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66ae7-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="66ae7-107">Die globale Richtlinie wird automatisch erstellt, wenn Sie den beständigen Chat Server bereitstellen, und Sie kann konfiguriert, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="66ae7-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="66ae7-108">Da die globale Richtlinie für alle Benutzer gilt, muss Sie nicht pro Benutzer eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="66ae7-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="66ae7-109">Sie können mehrere Website-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzern für beständigen Chat Server ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="66ae7-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="66ae7-110">Pool-und Website-Server Richtlinien für persistente Chats setzen die globale Richtlinie für beständigen Chats außer Kraft, allerdings nur für Benutzer dieser Website.</span><span class="sxs-lookup"><span data-stu-id="66ae7-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="66ae7-111">Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66ae7-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66ae7-112">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="66ae7-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="66ae7-113">Ausführliche Informationen finden Sie unter [Hinzufügen von beständigem Chat Server zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="66ae7-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="66ae7-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="66ae7-114">Tasks that you can perform</span></span>

<span data-ttu-id="66ae7-115">Auf der Seite **Richtlinie für den beständigen Chat** können Sie die folgenden Aufgaben ausführen: Richtlinie für den Server für beständigen Chat aktivieren, Richtlinie für den Server für beständigen Chat verwalten.</span><span class="sxs-lookup"><span data-stu-id="66ae7-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="66ae7-116">So konfigurieren Sie die globale Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="66ae7-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="66ae7-117">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66ae7-118">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="66ae7-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="66ae7-119">Klicken Sie in der Skype for Business Server-Systemsteuerung auf **beständigen Chat**und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="66ae7-120">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="66ae7-121">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="66ae7-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="66ae7-122">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="66ae7-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="66ae7-123">Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="66ae7-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="66ae7-124">Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="66ae7-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="66ae7-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="66ae7-126">So erstellen Sie eine Richtlinie für beständigen Chat für eine Website</span><span class="sxs-lookup"><span data-stu-id="66ae7-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="66ae7-127">Für jede Website, die Sie bereitgestellt haben, können Sie eine Website spezifische Richtlinie für beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="66ae7-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="66ae7-128">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="66ae7-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="66ae7-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66ae7-130">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="66ae7-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="66ae7-131">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="66ae7-132">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="66ae7-133">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="66ae7-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="66ae7-134">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="66ae7-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="66ae7-135">Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).</span><span class="sxs-lookup"><span data-stu-id="66ae7-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="66ae7-136">Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)</span><span class="sxs-lookup"><span data-stu-id="66ae7-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="66ae7-137">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="66ae7-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="66ae7-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="66ae7-139">So erstellen Sie eine Benutzerrichtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="66ae7-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="66ae7-140">In der Skype for Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern in **Benutzern**zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="66ae7-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="66ae7-141">Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66ae7-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="66ae7-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66ae7-143">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="66ae7-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="66ae7-144">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="66ae7-145">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="66ae7-146">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="66ae7-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="66ae7-147">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="66ae7-148">Geben Sie in **Beschreibung**Details zu den Benutzerrichtlinien an (beispielsweise Richtlinien für beständigen Chat für bestimmten Benutzer).</span><span class="sxs-lookup"><span data-stu-id="66ae7-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="66ae7-149">Zum Steuern des beständigen Chats für alle Benutzer, die nicht ausdrücklich über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="66ae7-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="66ae7-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="66ae7-151">So wenden Sie eine Benutzerrichtlinie für beständigen Chat auf ein Benutzerkonto an</span><span class="sxs-lookup"><span data-stu-id="66ae7-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="66ae7-152">Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie geeignete Richtlinien auf bestimmte Benutzer anwenden, um Sie für beständigen Chat Server zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="66ae7-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="66ae7-153">Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="66ae7-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="66ae7-154">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="66ae7-155">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="66ae7-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="66ae7-156">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="66ae7-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="66ae7-157">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="66ae7-158">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="66ae7-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66ae7-159">Die \*\* \<automatischen\> \*\* Einstellungen wenden die standardmäßige effektive Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="66ae7-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="66ae7-160">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="66ae7-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="66ae7-161">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66ae7-161">Click **Commit**.</span></span>
    

