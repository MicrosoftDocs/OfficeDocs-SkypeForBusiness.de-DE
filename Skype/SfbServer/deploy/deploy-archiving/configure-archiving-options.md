---
title: Konfigurieren von Archivierungsoptionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die anfänglichen Archivierungsoptionen für Skype for Business Server konfigurieren. Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.'
ms.openlocfilehash: 33438bb56c1ce55b0b449b9ee4124e27ae8638cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286601"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="c222a-104">Konfigurieren von Archivierungsoptionen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c222a-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="c222a-105">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die anfänglichen Archivierungsoptionen für Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c222a-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="c222a-106">Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="c222a-107">Zum Konfigurieren der anfänglichen Archivierungs Konfigurationen verwenden Sie die Skype for Business Server-Systemsteuerung, um Folgendes anzugeben:</span><span class="sxs-lookup"><span data-stu-id="c222a-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="c222a-108">Konfiguration auf globaler Ebene, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird</span><span class="sxs-lookup"><span data-stu-id="c222a-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="c222a-109">Optionale Konfigurationen auf Standortebene, um anzugeben, wie die Archivierung für einen bestimmten Standort implementiert wird</span><span class="sxs-lookup"><span data-stu-id="c222a-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="c222a-110">Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird</span><span class="sxs-lookup"><span data-stu-id="c222a-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="c222a-111">Sie müssen Optionen für Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c222a-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="c222a-112">Ob die Archivierung aktiviert oder deaktiviert werden soll</span><span class="sxs-lookup"><span data-stu-id="c222a-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="c222a-113">Ob Chatsitzungen archiviert werden sollen</span><span class="sxs-lookup"><span data-stu-id="c222a-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="c222a-114">Ob Webkonferenzsitzungen archiviert werden sollen</span><span class="sxs-lookup"><span data-stu-id="c222a-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c222a-115">Ob Aktivitäten blockiert werden sollen, wenn die Archivierung nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="c222a-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c222a-116">Ob die Exchange-Integration verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="c222a-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="c222a-117">Wie das Bereinigen und Exportieren von Daten eingerichtet werden soll</span><span class="sxs-lookup"><span data-stu-id="c222a-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="c222a-118">Sie sollten alle entsprechenden Optionen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c222a-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="c222a-119">Einzelheiten zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c222a-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="c222a-120">Details zum Verwalten von Konfigurationen nach der Bereitstellung mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell finden Sie unter [Verwalten von Archivierungsoptionen in Skype for Business Server](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="c222a-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="c222a-121">Konfigurieren von Archivierungsoptionen auf globaler Ebene</span><span class="sxs-lookup"><span data-stu-id="c222a-121">Configure global level archiving options</span></span>

<span data-ttu-id="c222a-122">Wenn Sie Ihrer Topologie Archivierungsvorgänge hinzufügen und die Topologie veröffentlichen, erstellt Skype for Business Server eine globale Konfiguration für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="c222a-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="c222a-123">Standardmäßig sind für die globale Konfiguration keine Archivierungsoptionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c222a-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="c222a-124">Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="c222a-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="c222a-125">So konfigurieren Sie Archivierungsoptionen auf globaler Ebene:</span><span class="sxs-lookup"><span data-stu-id="c222a-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="c222a-126">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c222a-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c222a-127">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c222a-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c222a-128">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c222a-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c222a-129">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="c222a-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c222a-130">Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="c222a-131">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="c222a-132">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="c222a-133">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="c222a-134">Gehen Sie auch auf der Seite **Archivierungseinstellungen bearbeiten – Global** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c222a-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="c222a-135">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c222a-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c222a-136">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="c222a-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c222a-137">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c222a-138">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c222a-139">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="c222a-140">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c222a-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="c222a-141">Konfigurieren von Archivierungsoptionen auf Standortebene</span><span class="sxs-lookup"><span data-stu-id="c222a-141">Configure site level archiving options</span></span>

<span data-ttu-id="c222a-142">Sie können Archivierungsoptionen für einen bestimmten Standort festlegen.</span><span class="sxs-lookup"><span data-stu-id="c222a-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="c222a-143">Eine Standortkonfiguration überschreibt die globale Konfiguration, aber nur für den in der Standortkonfiguration angegebenen Standort.</span><span class="sxs-lookup"><span data-stu-id="c222a-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="c222a-144">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c222a-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c222a-145">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c222a-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c222a-146">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c222a-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c222a-147">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c222a-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="c222a-148">Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c222a-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="c222a-149">Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="c222a-150">Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c222a-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="c222a-151">Um sowohl Chatsitzungen als auch Konferenzen zu archivieren, klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**.</span><span class="sxs-lookup"><span data-stu-id="c222a-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="c222a-152">Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c222a-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="c222a-153">Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="c222a-154">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c222a-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c222a-155">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="c222a-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c222a-156">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c222a-157">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c222a-158">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="c222a-159">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c222a-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="c222a-160">Konfigurieren von Archivierungsoptionen auf Poolebene</span><span class="sxs-lookup"><span data-stu-id="c222a-160">Configure pool level archiving options</span></span>

<span data-ttu-id="c222a-p106">Sie können Archivierungsoptionen für einen bestimmten Pool festlegen. Eine Poolkonfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, aber nur für den in der Poolkonfiguration angegebenen Pool.</span><span class="sxs-lookup"><span data-stu-id="c222a-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="c222a-163">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c222a-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c222a-164">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c222a-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c222a-165">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c222a-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c222a-166">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c222a-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="c222a-167">Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c222a-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="c222a-168">Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="c222a-169">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="c222a-170">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="c222a-171">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="c222a-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="c222a-172">Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="c222a-173">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c222a-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c222a-174">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="c222a-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c222a-175">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c222a-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c222a-176">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c222a-177">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c222a-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="c222a-178">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c222a-178">Click **Commit**.</span></span>
    

