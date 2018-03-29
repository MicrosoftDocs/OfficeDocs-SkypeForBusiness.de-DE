---
title: Richtlinie für beständigen Chat
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Die Seite Richtlinie für beständigen Chat, der Gruppe der beständigen Chat können Sie Richtlinien auf globaler Ebene sowie Pool, Standort oder Benutzer Ebene, einschließlich der Konfiguration der globale Richtlinie, und erstellen eine oder mehrere zusätzliche Benutzer- und Website Richtlinien für die Bereitstellung verwalten. Wenn Persistent Chat Server durch eine Richtlinie für einen Benutzer aktiviert ist, wird die Persistent Chat Server-Umgebung in ihrem Client angezeigt.
ms.openlocfilehash: 13f06436f3339da46e32557dff5290d5ad5541fd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="64489-104">Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="64489-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="64489-105">Sie können die Seite **Richtlinie für beständigen Chat** , der Gruppe der **Beständigen Chat** zum Verwalten von Richtlinien auf globaler Ebene sowie Pool, Standort oder Benutzer Ebene, einschließlich der Konfiguration der globale Richtlinie, und erstellen eine oder mehrere zusätzliche Benutzer- und Website Richtlinien für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="64489-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="64489-106">Wenn Persistent Chat Server durch eine Richtlinie für einen Benutzer aktiviert ist, wird die Persistent Chat Server-Umgebung in ihrem Client angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64489-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="64489-107">Die globale Richtlinie wird automatisch erstellt, wenn Sie Persistent Chat Server bereitstellen, und es kann so konfiguriert, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="64489-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="64489-108">Da die globale Richtlinie für alle Benutzer gilt, muss es keinen pro Benutzer festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="64489-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="64489-109">Sie können erstellen und konfigurieren mehrere Standort- und Benutzerrichtlinien, die Benutzer zusammen mit der globalen Richtlinie für Persistent Chat Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="64489-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="64489-110">Pools und der Website Persistent Chat Server-Richtlinien außer Kraft setzen die globale Richtlinie ein Persistent Chat Server, jedoch nur für Benutzer dieser Website.</span><span class="sxs-lookup"><span data-stu-id="64489-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="64489-111">Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64489-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64489-112">Zum Konfigurieren und Verwenden von Persistent Chat Server, müssen Sie zunächst mit dem Topologie-Generator Persistent Chat Server Support zur Topologie hinzugefügt werden, und die Topologie anschließend veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="64489-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="64489-113">Weitere Informationen hierzu finden Sie unter [Persistent Chat Server hinzufügen, um Ihre Skype für Business Server 2015 Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="64489-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="64489-114">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="64489-114">Tasks that you can perform</span></span>

<span data-ttu-id="64489-115">Auf der Seite **Richtlinie für den beständigen Chat** können Sie die folgenden Aufgaben ausführen: Richtlinie für den Server für beständigen Chat aktivieren, Richtlinie für den Server für beständigen Chat verwalten.</span><span class="sxs-lookup"><span data-stu-id="64489-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="64489-116">So konfigurieren Sie die globale Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="64489-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="64489-117">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="64489-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64489-118">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="64489-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64489-119">Klicken Sie auf **Beständiger Chat**in Skype Business Server-Systemsteuerung und klicken Sie dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="64489-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="64489-120">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="64489-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="64489-121">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="64489-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
  - <span data-ttu-id="64489-122">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64489-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
  - <span data-ttu-id="64489-123">Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise globale Richtlinie für die _CentralSiteName_) ist.</span><span class="sxs-lookup"><span data-stu-id="64489-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
  - <span data-ttu-id="64489-124">Oder um beständigen Chat für alle Standorte und Benutzer, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .</span><span class="sxs-lookup"><span data-stu-id="64489-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="64489-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="64489-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="64489-126">Erstellen Sie eine Richtlinie für beständigen Chat für eine Website</span><span class="sxs-lookup"><span data-stu-id="64489-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="64489-127">Für jeden Standort, den Sie bereitgestellt haben, können Sie eine standortspezifische Richtlinie für beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="64489-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="64489-128">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="64489-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="64489-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="64489-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64489-130">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="64489-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64489-131">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="64489-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="64489-132">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="64489-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="64489-133">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="64489-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="64489-134">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="64489-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="64489-135">Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).</span><span class="sxs-lookup"><span data-stu-id="64489-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
  - <span data-ttu-id="64489-136">Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)</span><span class="sxs-lookup"><span data-stu-id="64489-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
  - <span data-ttu-id="64489-137">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="64489-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="64489-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="64489-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="64489-139">Erstellen Sie eine Benutzerrichtlinie für den beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="64489-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="64489-140">In der Skype Business Server-Systemsteuerung definieren Sie Benutzerrichtlinien, die Benutzern unter **Benutzer**zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="64489-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="64489-141">Die Benutzerrichtlinie setzt die Richtlinien auf globaler und Standortebene außer Kraft. Dies gilt jedoch nur für die Benutzer, denen die Benutzerrichtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64489-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="64489-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="64489-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64489-143">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="64489-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64489-144">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="64489-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="64489-145">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="64489-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="64489-146">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="64489-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="64489-147">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="64489-147">In **Name**, specify a name for the new user policy.</span></span>
    
  - <span data-ttu-id="64489-148">Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise Richtlinie für beständigen Chat für bestimmte Benutzer) ist.</span><span class="sxs-lookup"><span data-stu-id="64489-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
  - <span data-ttu-id="64489-149">Klicken Sie zum beständigen Chat für alle Benutzer festlegen möchten, die nicht explizit über eine Benutzerrichtlinie gesteuert werden, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .</span><span class="sxs-lookup"><span data-stu-id="64489-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="64489-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="64489-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="64489-151">Anwenden eine Richtlinie für beständigen Chat Benutzer auf ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="64489-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="64489-152">Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie geeignete Richtlinien auf bestimmte Benutzer zu aktivieren oder deaktivieren sie für Persistent Chat Server anwenden.</span><span class="sxs-lookup"><span data-stu-id="64489-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="64489-153">Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Benutzerrichtlinie für beständigen Chat auf einen oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="64489-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="64489-154">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="64489-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64489-155">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="64489-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="64489-156">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="64489-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="64489-157">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="64489-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="64489-158">Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**die Benutzerrichtlinie beständigen Chat, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64489-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64489-159">Die ** \<automatische\> ** Einstellungen die Standardrichtlinie für eine effektive gelten.</span><span class="sxs-lookup"><span data-stu-id="64489-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="64489-160">Diese Einstellungen werden automatisch vom Server angewendet.</span><span class="sxs-lookup"><span data-stu-id="64489-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="64489-161">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="64489-161">Click **Commit**.</span></span>
    

