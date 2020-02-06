---
title: Richtlinie für beständigen Chat – Hauptseite
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
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Sie können die Seite "beständiger Chat" der Gruppe "beständiger Chat" verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung. Wenn ein Benutzer nach Richtlinie für beständigen Chat Server aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.
ms.openlocfilehash: 053e7fb4f03f7e152a238a3b155eac161433c141
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822518"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="cc23c-104">Richtlinie für beständigen Chat – Hauptseite</span><span class="sxs-lookup"><span data-stu-id="cc23c-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="cc23c-105">Sie können die Seite " **beständiger Chat** " der Gruppe " **beständiger Chat** " verwenden, um Richtlinien auf globaler, Pool-, Website-oder Benutzerebene zu verwalten, einschließlich der Konfiguration der globalen Standardrichtlinie und dem Erstellen einer oder mehrerer zusätzlicher Benutzer-und Website Richtlinien für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="cc23c-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="cc23c-106">Wenn ein Benutzer nach Richtlinie für beständigen Chat Server aktiviert ist, wird die Server Umgebung für beständigen Chat in seinem Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc23c-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc23c-107">In der Topologie gelten Website Richtlinien für beständigen Chat Server global, pro Benutzerpool oder pro Benutzer Website oder pro Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cc23c-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="cc23c-108">Die globale Richtlinie wird automatisch erstellt, wenn Sie den beständigen Chat Server bereitstellen, und Sie kann konfiguriert, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cc23c-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="cc23c-109">Da die globale Richtlinie für alle Benutzer gilt, muss Sie nicht pro Benutzer eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cc23c-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="cc23c-110">Sie können mehrere Website-und Benutzerrichtlinien erstellen und konfigurieren, die zusammen mit der globalen Richtlinie Benutzern für beständigen Chat Server ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cc23c-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="cc23c-111">Pool-und Website-Server Richtlinien für persistente Chats setzen die globale Richtlinie für beständigen Chats außer Kraft, allerdings nur für Benutzer dieser Website.</span><span class="sxs-lookup"><span data-stu-id="cc23c-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="cc23c-112">Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cc23c-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc23c-113">Um den Server für beständigen Chat zu konfigurieren und zu verwenden, müssen Sie zuerst den Topologie-Generator verwenden, um der Topologie Unterstützung für beständigen Chat Server hinzuzufügen und dann die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="cc23c-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="cc23c-114">Ausführliche Informationen finden Sie unter [Hinzufügen von beständigem Chat Server zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc23c-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="cc23c-115">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cc23c-115">Tasks that you can perform</span></span>

<span data-ttu-id="cc23c-116">Auf der Seite **Richtlinie für beständigen Chat** können Sie die folgenden Aufgaben ausführen: Aktivieren und Verwalten der Richtlinie für den Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cc23c-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="cc23c-117">So konfigurieren Sie die globale Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="cc23c-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="cc23c-118">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cc23c-119">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cc23c-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cc23c-120">Klicken Sie in der Skype for Business Server-Systemsteuerung auf **beständigen Chat**und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cc23c-121">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cc23c-122">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cc23c-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="cc23c-123">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cc23c-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="cc23c-124">Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="cc23c-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="cc23c-125">Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="cc23c-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="cc23c-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="cc23c-127">So erstellen Sie eine Richtlinie für beständigen Chat für eine Website</span><span class="sxs-lookup"><span data-stu-id="cc23c-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="cc23c-128">Für jede Website, die Sie bereitgestellt haben, können Sie eine Website spezifische Richtlinie für beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc23c-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="cc23c-129">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="cc23c-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="cc23c-130">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cc23c-131">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cc23c-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cc23c-132">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cc23c-133">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="cc23c-134">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc23c-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="cc23c-135">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cc23c-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="cc23c-136">Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).</span><span class="sxs-lookup"><span data-stu-id="cc23c-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="cc23c-137">Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)</span><span class="sxs-lookup"><span data-stu-id="cc23c-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="cc23c-138">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="cc23c-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="cc23c-139">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="cc23c-140">So erstellen Sie eine Benutzerrichtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="cc23c-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="cc23c-141">In der Skype for Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern in **Benutzern**zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="cc23c-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="cc23c-142">Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cc23c-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="cc23c-143">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cc23c-144">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cc23c-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cc23c-145">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cc23c-146">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="cc23c-147">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cc23c-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="cc23c-148">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="cc23c-149">Geben Sie in **Beschreibung**Details zu den Benutzerrichtlinien an (beispielsweise Richtlinien für beständigen Chat für bestimmten Benutzer).</span><span class="sxs-lookup"><span data-stu-id="cc23c-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="cc23c-150">Zum Steuern des beständigen Chats für alle Benutzer, die nicht ausdrücklich über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **beständigen Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="cc23c-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="cc23c-151">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="cc23c-152">So wenden Sie eine Benutzerrichtlinie für beständigen Chat auf ein Benutzerkonto an</span><span class="sxs-lookup"><span data-stu-id="cc23c-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="cc23c-153">Wenn ein Benutzer für Skype for Business aktiviert wurde, können Sie geeignete Richtlinien auf bestimmte Benutzer anwenden, um Sie für beständigen Chat Server zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc23c-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="cc23c-154">Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="cc23c-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="cc23c-155">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cc23c-156">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cc23c-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cc23c-157">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cc23c-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="cc23c-158">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cc23c-159">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cc23c-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cc23c-160">Die \*\* \<automatischen\> \*\* Einstellungen wenden die standardmäßige effektive Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="cc23c-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="cc23c-161">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="cc23c-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="cc23c-162">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cc23c-162">Click **Commit**.</span></span>
    

