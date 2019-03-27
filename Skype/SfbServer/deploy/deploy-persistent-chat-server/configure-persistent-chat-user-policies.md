---
title: Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Benutzerrichtlinien für Persistent Chat Server in Skype für Business Server 2015 zu erstellen. Mit Benutzerrichtlinien für beständigen Chat wird festgelegt, ob Benutzer Zugriff auf Chatrooms erhalten oder nicht.'
ms.openlocfilehash: e082898d92e622827e2543316b07a8be224c56c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883707"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="4ed45-104">Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4ed45-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4ed45-105">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Benutzerrichtlinien für Persistent Chat Server in Skype für Business Server 2015 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ed45-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="4ed45-106">Mit Benutzerrichtlinien für beständigen Chat wird festgelegt, ob Benutzer Zugriff auf Chatrooms erhalten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4ed45-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="4ed45-107">Persistent Chat Server Benutzerrichtlinien auf folgenden Ebenen können verwaltet werden: global, Standort oder Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4ed45-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="4ed45-108">Zunächst konfigurieren die globalen Richtlinie für beständigen Chat für alle Benutzer in Ihrer Bereitstellung zu aktivieren und anschließend weitere Benutzer und websiterichtlinien zum Steuern, ob beständigen Chat für bestimmte Benutzer und Websites aktiviert ist, klicken Sie auf erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ed45-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="4ed45-109">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="4ed45-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="4ed45-110">Konfigurieren der globalen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-110">Configure the global policy</span></span>
    
- <span data-ttu-id="4ed45-111">Erstellen einer Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-111">Create a site policy</span></span>
    
- <span data-ttu-id="4ed45-112">Erstellen einer Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-112">Create a user policy</span></span>
    
- <span data-ttu-id="4ed45-113">Anwenden einer Richtlinie auf einen Benutzer oder eine Benutzergruppe</span><span class="sxs-lookup"><span data-stu-id="4ed45-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="4ed45-114">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4ed45-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4ed45-115">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ed45-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="4ed45-116">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="4ed45-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="4ed45-117">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ed45-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="4ed45-118">Konfigurieren der globalen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-118">Configure the global policy</span></span>

<span data-ttu-id="4ed45-119">Um die globale Richtlinie zu konfigurieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4ed45-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="4ed45-120">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ed45-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ed45-121">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="4ed45-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4ed45-122">Klicken Sie auf **Beständiger Chat**in Skype Business Server-Systemsteuerung und klicken Sie dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="4ed45-123">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4ed45-124">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4ed45-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="4ed45-125">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4ed45-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="4ed45-126">Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise globale Richtlinie für die _CentralSiteName_) ist.</span><span class="sxs-lookup"><span data-stu-id="4ed45-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="4ed45-127">Oder um beständigen Chat für alle Standorte und Benutzer, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .</span><span class="sxs-lookup"><span data-stu-id="4ed45-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="4ed45-128">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="4ed45-129">Erstellen einer Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-129">Create a site policy</span></span>

<span data-ttu-id="4ed45-130">Sie können für jeden Standort, den Sie bereitstellen, eine standortspezifische Richtlinie für den beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ed45-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="4ed45-131">Die Konfiguration in der Standortrichtlinie hat Vorrang vor der globalen Richtlinie, jedoch nur für den von der Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="4ed45-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="4ed45-132">So erstellen Sie eine Standortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="4ed45-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="4ed45-133">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ed45-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ed45-134">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="4ed45-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4ed45-135">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="4ed45-136">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="4ed45-137">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4ed45-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="4ed45-138">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4ed45-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="4ed45-139">Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).</span><span class="sxs-lookup"><span data-stu-id="4ed45-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="4ed45-140">Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)</span><span class="sxs-lookup"><span data-stu-id="4ed45-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="4ed45-141">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="4ed45-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="4ed45-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="4ed45-143">Erstellen einer Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4ed45-143">Create a user policy</span></span>

<span data-ttu-id="4ed45-144">Sie können benutzerspezifische Richtlinien erstellen, die Vorrang vor der globalen Richtlinie und allen Standortrichtlinien haben, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="4ed45-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="4ed45-145">So erstellen Sie eine Benutzerrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="4ed45-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="4ed45-146">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ed45-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ed45-147">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="4ed45-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4ed45-148">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="4ed45-149">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="4ed45-150">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4ed45-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="4ed45-151">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="4ed45-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="4ed45-152">Einzelheiten Sie im Feld **Beschreibung**über den was die Benutzerrichtlinie (beispielsweise Richtlinie für beständigen Chat für bestimmte Benutzer) ist.</span><span class="sxs-lookup"><span data-stu-id="4ed45-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="4ed45-153">Klicken Sie zum beständigen Chat für alle Benutzer festlegen möchten, die nicht explizit über eine Benutzerrichtlinie gesteuert werden, aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **Aktivieren beständigen Chat** .</span><span class="sxs-lookup"><span data-stu-id="4ed45-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="4ed45-154">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="4ed45-155">Anwenden einer Benutzerrichtlinie auf ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="4ed45-155">Apply a policy to a user account</span></span>

<span data-ttu-id="4ed45-156">Nach dem Erstellen von Richtlinien können Sie diese wie folgt auf ein Benutzerkonten anwenden:</span><span class="sxs-lookup"><span data-stu-id="4ed45-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="4ed45-157">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ed45-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ed45-158">Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.</span><span class="sxs-lookup"><span data-stu-id="4ed45-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4ed45-159">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4ed45-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="4ed45-160">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4ed45-161">**Skype für Business Server-Benutzer bearbeiten** unter **Richtlinie für beständigen Chat**wählen Sie die Benutzerrichtlinie für beständigen Chat, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4ed45-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ed45-162">Die \*\* \<automatische\> \*\* Einstellungen die Standardrichtlinie für eine effektive gelten.</span><span class="sxs-lookup"><span data-stu-id="4ed45-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="4ed45-163">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="4ed45-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="4ed45-164">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4ed45-164">Click **Commit**.</span></span>
    

