---
title: Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 erste Benutzerrichtlinien für den Server für beständigen Chat erstellen. Mit Benutzerrichtlinien für beständigen Chat wird festgelegt, ob Benutzer Zugriff auf Chatrooms erhalten oder nicht.'
ms.openlocfilehash: 7c73b34f418946dda76302c0ee2abb18125e6f07
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273854"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="cb058-104">Konfigurieren von Benutzerrichtlinien für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cb058-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cb058-105">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie in Skype for Business Server 2015 erste Benutzerrichtlinien für den Server für beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb058-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="cb058-106">Mit Benutzerrichtlinien für beständigen Chat wird festgelegt, ob Benutzer Zugriff auf Chatrooms erhalten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="cb058-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="cb058-107">Sie können die Benutzerrichtlinien für beständigen Chat Server auf den folgenden Ebenen verwalten: Global, Site oder User.</span><span class="sxs-lookup"><span data-stu-id="cb058-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="cb058-108">Zunächst konfigurieren Sie die globale Richtlinie so, dass beständige Chat Einstellungen für alle Benutzer in Ihrer Bereitstellung aktiviert werden, und erstellen dann zusätzliche Benutzer-und Website Richtlinien, um zu steuern, ob der beständige Chat für bestimmte Benutzer und Websites aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb058-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="cb058-109">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="cb058-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="cb058-110">Konfigurieren der globalen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-110">Configure the global policy</span></span>
    
- <span data-ttu-id="cb058-111">Erstellen einer Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-111">Create a site policy</span></span>
    
- <span data-ttu-id="cb058-112">Erstellen einer Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-112">Create a user policy</span></span>
    
- <span data-ttu-id="cb058-113">Anwenden einer Richtlinie auf einen Benutzer oder eine Benutzergruppe</span><span class="sxs-lookup"><span data-stu-id="cb058-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="cb058-114">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb058-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cb058-115">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb058-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="cb058-116">Weitere Informationen finden Sie unter [Reise von Skype for Business zu Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="cb058-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="cb058-117">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="cb058-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="cb058-118">Konfigurieren der globalen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-118">Configure the global policy</span></span>

<span data-ttu-id="cb058-119">Um die globale Richtlinie zu konfigurieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="cb058-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="cb058-120">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cb058-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cb058-121">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cb058-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cb058-122">Klicken Sie in der Skype for Business Server-Systemsteuerung auf beständigen **Chat**und dann auf **Richtlinie**für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cb058-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cb058-123">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cb058-124">Führen Sie im Abschnitt **Richtlinie für beständigen Chat bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cb058-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="cb058-125">Geben Sie unter **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardwert „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cb058-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="cb058-126">Geben Sie in **Beschreibung**Details zu den Richtlinien für Benutzer an (beispielsweise globale Richtlinie für _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="cb058-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="cb058-127">Zum Steuern des beständigen Chats für alle Websites und Benutzer, die nicht explizit über eine Website Richtlinie oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen beständigen **Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="cb058-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="cb058-128">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="cb058-129">Erstellen einer Standortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-129">Create a site policy</span></span>

<span data-ttu-id="cb058-130">Sie können für jeden Standort, den Sie bereitstellen, eine standortspezifische Richtlinie für den beständigen Chat erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb058-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="cb058-131">Die Konfiguration in der Standortrichtlinie hat Vorrang vor der globalen Richtlinie, jedoch nur für den von der Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="cb058-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="cb058-132">So erstellen Sie eine Standortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="cb058-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="cb058-133">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cb058-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cb058-134">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cb058-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cb058-135">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="cb058-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cb058-136">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cb058-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="cb058-137">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb058-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="cb058-138">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cb058-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="cb058-139">Geben Sie unter **Name** einen Namen für die neue Standortrichtlinie an (z. B. „Redmond“).</span><span class="sxs-lookup"><span data-stu-id="cb058-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="cb058-140">Geben Sie unter **Beschreibung** Einzelheiten zum Zweck der Standortrichtlinie an (z. B. Chatroomrichtlinie für Redmond)</span><span class="sxs-lookup"><span data-stu-id="cb058-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="cb058-141">Aktivieren bzw. deaktivieren Sie das Kontrollkästchen **Beständigen Chat aktivieren**, um den beständigen Chat für alle Standorte zu steuern, die nicht gesondert über eine Standortrichtlinie gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="cb058-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="cb058-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="cb058-143">Erstellen einer Benutzerrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cb058-143">Create a user policy</span></span>

<span data-ttu-id="cb058-144">Sie können benutzerspezifische Richtlinien erstellen, die Vorrang vor der globalen Richtlinie und allen Standortrichtlinien haben, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="cb058-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="cb058-145">So erstellen Sie eine Benutzerrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="cb058-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="cb058-146">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cb058-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cb058-147">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cb058-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cb058-148">Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Richtlinie für beständigen Chat**.</span><span class="sxs-lookup"><span data-stu-id="cb058-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="cb058-149">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cb058-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="cb058-150">Führen Sie unter **Neue Richtlinie für beständigen Chat** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="cb058-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="cb058-151">Geben Sie unter **Name** einen Namen für die neue Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="cb058-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="cb058-152">Geben Sie in **Beschreibung**Details zu den Benutzerrichtlinien an (beispielsweise Richtlinien für beständigen Chat für bestimmten Benutzer).</span><span class="sxs-lookup"><span data-stu-id="cb058-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="cb058-153">Zum Steuern des beständigen Chats für alle Benutzer, die nicht ausdrücklich über eine Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen beständigen **Chat aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="cb058-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="cb058-154">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="cb058-155">Anwenden einer Benutzerrichtlinie auf ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="cb058-155">Apply a policy to a user account</span></span>

<span data-ttu-id="cb058-156">Nach dem Erstellen von Richtlinien können Sie diese wie folgt auf ein Benutzerkonten anwenden:</span><span class="sxs-lookup"><span data-stu-id="cb058-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="cb058-157">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsPersistentChatAdministrator“, „CsAdministrator“ oder „CsUserAdministrator“ zugewiesen ist, auf einem beliebigen Computer in der internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="cb058-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cb058-158">Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.</span><span class="sxs-lookup"><span data-stu-id="cb058-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cb058-159">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cb058-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="cb058-160">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cb058-161">Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **Richtlinie**für beständigen Chat die Benutzerrichtlinie für beständigen Chat aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cb058-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb058-162">Die \*\* \<automatischen\> \*\* Einstellungen wenden die standardmäßige effektive Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="cb058-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="cb058-163">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="cb058-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="cb058-164">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb058-164">Click **Commit**.</span></span>
    

