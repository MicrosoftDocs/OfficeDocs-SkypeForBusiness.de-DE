---
title: Konfigurieren von Archivierungsrichtlinien für Skype Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsrichtlinien für Skype für Business Server-Benutzer konfigurieren.'
ms.openlocfilehash: 83b929a01013fa96dbec9742d36d3cec0387d4ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895910"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="7f729-103">Konfigurieren von Archivierungsrichtlinien für Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="7f729-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="7f729-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die ursprüngliche Archivierungsrichtlinien für Skype für Business Server-Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="7f729-105">In Skype für Business Server verwenden Sie Richtlinien zum Aktivieren und Deaktivieren der Archivierung für interne Kommunikation und externen Kommunikation für Benutzer, die auf Skype für Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="7f729-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="7f729-106">Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f729-106">This includes the following:</span></span>
  
- <span data-ttu-id="7f729-107">Eine globale Richtlinie, die standardmäßig erstellt wird, bei der Bereitstellung von Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="7f729-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="7f729-108">Optionale Richtlinien auf Standortebene, die festlegen, wie die Archivierung für einen bestimmten Standort implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="7f729-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="7f729-109">Optionale Richtlinien auf Benutzerebene, die angeben, wie die Archivierung für bestimmte Benutzer implementiert wird</span><span class="sxs-lookup"><span data-stu-id="7f729-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="7f729-110">Zunächst eingerichtet werden Archivierungsrichtlinien, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Benutzerrichtlinien nach der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="7f729-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="7f729-111">Die Seite **Archivierungsrichtlinie** der Gruppe der **Archivierung und Überwachung** können Sie in Skype Business Server-Systemsteuerung Richtlinien auf globaler, Standort- und Benutzerebene verwalten.</span><span class="sxs-lookup"><span data-stu-id="7f729-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f729-112">Um die Implementierung der Archivierung zu steuern, müssen Sie die Optionen, z. B., ob archiviert Sofortnachrichten oder Konferenzen, die Verwendung des kritischen Modus und Löschung Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="7f729-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="7f729-113">Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder jede Website oder poolarchivierungskonfiguration aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f729-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="7f729-114">Sie sollten alle entsprechende Optionen angeben, vor dem Aktivieren der Archivierung für interne oder externe Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="7f729-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="7f729-115">Weitere Informationen hierzu finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype für Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="7f729-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7f729-116">Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange In-Place Hold Policies Steuerelement aktivieren, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="7f729-117">Ausführliche Informationen zu wie Archivierungsrichtlinien arbeiten, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7f729-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="7f729-118">Ausführliche Informationen zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype für Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="7f729-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="7f729-119">Globale Richtlinie</span><span class="sxs-lookup"><span data-stu-id="7f729-119">Global policy</span></span>

<span data-ttu-id="7f729-120">Wenn Sie die Front-End-Server bereitstellen, erstellt Skype für Business Server eine globale Richtlinie für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="7f729-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="7f729-121">Archivierung ist standardmäßig in der globalen Richtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f729-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="7f729-122">Die globale Richtlinie steuert, ob Archivierung für die internen und externen Kommunikation für die gesamte Bereitstellung aktiviert ist, es sei denn, Sie von Standort- oder Richtlinien festgelegt, die die globale Richtlinie außer Kraft setzen, oder wenn Sie Microsoft Exchange-Integration für einige oder alle verwenden Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7f729-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="7f729-123">Wenn Sie Microsoft Exchange-Integration verwenden, die globale Richtlinie gilt nicht für alle Benutzer, die in Exchange verwaltet werden, und haben die Postfächer, die Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="7f729-124">Konfigurieren der globalen Richtlinie für die Archivierung für Skype für Business Server-Archivierungsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="7f729-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="7f729-125">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f729-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f729-126">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f729-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7f729-127">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7f729-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="7f729-128">Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7f729-129">Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7f729-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="7f729-130">Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f729-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="7f729-131">Geben Sie im Feld **Beschreibung**Informationen dazu, was die Richtlinie (z. B. globale Richtlinie für die *DivisionName* .</span><span class="sxs-lookup"><span data-stu-id="7f729-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="7f729-132">Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7f729-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="7f729-133">Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7f729-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="7f729-134">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="7f729-135">Standortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7f729-135">Site policies</span></span>

<span data-ttu-id="7f729-136">Sie können aktivieren oder Deaktivieren der Archivierung für bestimmte Standorte, indem Sie eine Archivierungsrichtlinie für die einzelnen Websites erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f729-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="7f729-137">Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch Benutzerrichtlinien überschreiben Standortrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7f729-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="7f729-138">Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange-Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber haben einige Benutzer befinden sich nicht auf Exchange-haben ihren Postfächern Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="7f729-139">Erstellen einer Archivierungsrichtlinie für einen Standort</span><span class="sxs-lookup"><span data-stu-id="7f729-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="7f729-140">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f729-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f729-141">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f729-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7f729-142">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7f729-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="7f729-143">Ausführliche Informationen zu wie Archivierungsrichtlinien arbeiten, einschließlich der Hierarchie für globale, Standort- und Benutzerrichtlinien, finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="7f729-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="7f729-144">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7f729-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="7f729-145">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f729-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="7f729-146">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7f729-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="7f729-147">Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="7f729-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="7f729-148">Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).</span><span class="sxs-lookup"><span data-stu-id="7f729-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="7f729-149">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="7f729-150">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="7f729-151">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="7f729-152">Benutzerrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7f729-152">User policies</span></span>

<span data-ttu-id="7f729-153">Sie können aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer durch Erstellen und konfigurieren eine Archivierungsrichtlinie für Benutzer, und wenden Sie dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen.</span><span class="sxs-lookup"><span data-stu-id="7f729-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="7f729-154">Richtlinien für Benutzer außer Kraft setzen globale Richtlinie oder websiterichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7f729-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="7f729-155">Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange-Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber haben einige Benutzer befinden sich nicht auf Exchange-haben ihren Postfächern Compliance-Archiv platzieren.</span><span class="sxs-lookup"><span data-stu-id="7f729-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="7f729-156">Konfigurieren Sie eine Archivierungsrichtlinie für Benutzer in Skype für Business Server verwaltet</span><span class="sxs-lookup"><span data-stu-id="7f729-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="7f729-157">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f729-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f729-158">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f729-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7f729-159">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7f729-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="7f729-160">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7f729-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="7f729-161">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7f729-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="7f729-162">Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="7f729-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="7f729-163">Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).</span><span class="sxs-lookup"><span data-stu-id="7f729-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="7f729-164">Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7f729-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="7f729-165">Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="7f729-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="7f729-166">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-166">Click **Commit**.</span></span>
    
<span data-ttu-id="7f729-167">Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7f729-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="7f729-168">Anwenden einer Skype für Business Server Archivierungsrichtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="7f729-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="7f729-169">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f729-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f729-170">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f729-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7f729-171">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7f729-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="7f729-172">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7f729-173">Wählen Sie in **Skype für Business Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**Benutzerrichtlinie, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f729-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f729-174">Die \*\* \<automatische\> \*\* Einstellungen gelten die Standardeinstellungen für Server-Installation.</span><span class="sxs-lookup"><span data-stu-id="7f729-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="7f729-175">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="7f729-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="7f729-176">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7f729-176">Click **Commit**.</span></span>
    

