---
title: Konfigurieren von Archivierungsrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die anfänglichen Archivierungsrichtlinien für Skype for Business Server-Benutzer konfigurieren.'
ms.openlocfilehash: ff946fe2fde2fcd8aae842e809a89bffb7852bca
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769208"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="dd65f-103">Konfigurieren von Archivierungsrichtlinien für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd65f-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="dd65f-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die anfänglichen Archivierungsrichtlinien für Skype for Business Server-Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dd65f-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="dd65f-105">In Skype for Business Server verwenden Sie Richtlinien, um die Archivierung für interne Kommunikation und externe Kommunikation für Benutzer zu aktivieren und zu deaktivieren, die in Skype for Business Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="dd65f-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="dd65f-106">Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dd65f-106">This includes the following:</span></span>
  
- <span data-ttu-id="dd65f-107">Eine globale Richtlinie, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird</span><span class="sxs-lookup"><span data-stu-id="dd65f-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="dd65f-108">Optionale Richtlinien auf Standortebene, die festlegen, wie die Archivierung für einen bestimmten Standort implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="dd65f-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="dd65f-109">Optionale Richtlinien auf Benutzerebene, die angeben, wie die Archivierung für bestimmte Benutzer implementiert wird</span><span class="sxs-lookup"><span data-stu-id="dd65f-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="dd65f-110">Sie haben zunächst Archivierungsrichtlinien eingerichtet, wenn Sie die Archivierung bereitstellen, Sie können aber nach der Bereitstellung Richtlinien ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="dd65f-111">In der Skype for Business Server-Systemsteuerung können Sie die Seite **Archivierungsrichtlinie** der Gruppe **Archivierung und Überwachung** verwenden, um Richtlinien auf globaler, Website-und Benutzerebene zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="dd65f-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd65f-112">Um die Implementierung der Archivierung zu steuern, müssen Sie Optionen angeben, beispielsweise ob Sie Chatnachrichten oder Konferenzen archivieren, die Verwendung des kritischen Modus und Bereinigungsoptionen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dd65f-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="dd65f-113">Standardmäßig sind keine Optionen in der globalen Archivierungskonfiguration oder einer Standort-oder Pool Archivierungskonfiguration aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd65f-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="dd65f-114">Sie sollten alle geeigneten Optionen angeben, bevor Sie die Archivierung für die interne oder externe Kommunikation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd65f-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="dd65f-115">Ausführliche Informationen finden Sie unter [Konfigurieren von Archivierungsoptionen für Skype for Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="dd65f-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dd65f-116">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd65f-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="dd65f-117">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="dd65f-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="dd65f-118">Details zum Verwalten von Richtlinien nach der Bereitstellung finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="dd65f-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="dd65f-119">Globale Richtlinie</span><span class="sxs-lookup"><span data-stu-id="dd65f-119">Global policy</span></span>

<span data-ttu-id="dd65f-120">Wenn Sie Ihre Front-End-Server bereitstellen, erstellt Skype for Business Server eine globale Richtlinie für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="dd65f-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="dd65f-121">Standardmäßig ist die Archivierung in der globalen Richtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd65f-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="dd65f-122">Mit der globalen Richtlinie wird gesteuert, ob die Archivierung für die interne und externe Kommunikation für Ihre gesamte Bereitstellung aktiviert ist, es sei denn, Sie richten Website-oder Benutzerrichtlinien ein, die die globale Richtlinie außer Kraft setzen, oder wenn Sie die Microsoft Exchange-Integration für einige oder alle von Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dd65f-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="dd65f-123">Wenn Sie die Microsoft Exchange-Integration verwenden, gilt die globale Richtlinie nicht für alle Benutzer, die sich in Exchange befinden und die Postfächer in-situ-Speicherplatz gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="dd65f-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="dd65f-124">Konfigurieren der globalen Richtlinie für die Archivierung von Skype for Business Server-Archivierungsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="dd65f-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="dd65f-125">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dd65f-126">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dd65f-127">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="dd65f-128">Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dd65f-129">Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="dd65f-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="dd65f-130">Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen „Global“ nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dd65f-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="dd65f-131">Geben Sie in **Beschreibung**Informationen zu den Richtlinien an (beispielsweise globale Richtlinie für *divisionname* .</span><span class="sxs-lookup"><span data-stu-id="dd65f-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="dd65f-132">Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="dd65f-133">Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="dd65f-134">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="dd65f-135">Standortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dd65f-135">Site policies</span></span>

<span data-ttu-id="dd65f-136">Sie können die Archivierung für bestimmte Websites aktivieren oder deaktivieren, indem Sie für jede dieser Websites eine Archivierungsrichtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="dd65f-137">Eine Website Richtlinie überschreibt die globale Richtlinie, aber Benutzerrichtlinien überschreiben Website Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="dd65f-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="dd65f-138">Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange gespeichert sind und deren Postfächer in einem Speicherplatz abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd65f-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="dd65f-139">Erstellen einer Archivierungsrichtlinie für einen Standort</span><span class="sxs-lookup"><span data-stu-id="dd65f-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="dd65f-140">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dd65f-141">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="dd65f-142">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="dd65f-143">Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="dd65f-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="dd65f-144">Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="dd65f-145">Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dd65f-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="dd65f-146">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="dd65f-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="dd65f-147">Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="dd65f-148">Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).</span><span class="sxs-lookup"><span data-stu-id="dd65f-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="dd65f-149">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd65f-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="dd65f-150">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd65f-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="dd65f-151">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="dd65f-152">Benutzerrichtlinien</span><span class="sxs-lookup"><span data-stu-id="dd65f-152">User policies</span></span>

<span data-ttu-id="dd65f-153">Sie können die Archivierung für bestimmte Benutzer aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie für Benutzer erstellen und konfigurieren und dann die Richtlinie auf bestimmte Benutzer oder Benutzergruppen anwenden.</span><span class="sxs-lookup"><span data-stu-id="dd65f-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="dd65f-154">Benutzerrichtlinien überschreiben alle globalen Richtlinien oder Website Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="dd65f-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="dd65f-155">Archivierungsrichtlinien gelten nur, wenn Sie die Microsoft Exchange-Integration nicht verwenden, oder wenn Sie die Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange gespeichert sind und deren Postfächer in einem Speicherplatz abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="dd65f-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="dd65f-156">Konfigurieren einer Archivierungsrichtlinie für Benutzer, die in Skype for Business Server verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="dd65f-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="dd65f-157">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dd65f-158">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dd65f-159">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="dd65f-160">Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="dd65f-161">Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="dd65f-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="dd65f-162">Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="dd65f-163">Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).</span><span class="sxs-lookup"><span data-stu-id="dd65f-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="dd65f-164">Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="dd65f-165">Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="dd65f-166">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-166">Click **Commit**.</span></span>
    
<span data-ttu-id="dd65f-167">Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="dd65f-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="dd65f-168">Anwenden einer Skype for Business Server-Archivierungsrichtlinie auf einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="dd65f-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="dd65f-169">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dd65f-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="dd65f-170">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dd65f-171">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dd65f-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="dd65f-172">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dd65f-173">Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dd65f-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dd65f-174">Die \*\* \<automatischen\> \*\* Einstellungen gelten für die standardmäßigen Server Installationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="dd65f-175">Diese Einstellungen werden vom Server automatisch übernommen.</span><span class="sxs-lookup"><span data-stu-id="dd65f-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="dd65f-176">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dd65f-176">Click **Commit**.</span></span>
    

