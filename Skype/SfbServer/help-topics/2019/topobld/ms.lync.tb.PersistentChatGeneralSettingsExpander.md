---
title: Allgemeine Einstellungen für den beständigen Chat - Erweiterung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Bearbeiten Sie die allgemeinen Einstellungen für den beständigen Chat-Server oder Persistent Chat Server Pool, indem konfigurieren diese Eigenschaften definieren:'
ms.openlocfilehash: 84d6600c6ff99d55233ad40c7238fbb2c0480c98
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="b0f0f-103">Allgemeine Einstellungen für den beständigen Chat - Erweiterung</span><span class="sxs-lookup"><span data-stu-id="b0f0f-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="b0f0f-104">Bearbeiten Sie die **allgemeinen** Einstellungen für den beständigen Chat-Server oder Persistent Chat Server Pool, indem konfigurieren diese Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="b0f0f-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b0f0f-105">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-105">**General**</span></span>
  
- <span data-ttu-id="b0f0f-106">**FQDN**: Bearbeiten Sie diese Einstellung, um den vollqualifizierten Domänennamen Ihres Persistent Chat Server oder Pool Persistent Chat Server definieren</span><span class="sxs-lookup"><span data-stu-id="b0f0f-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="b0f0f-107">**Anzeigename des Pools für den beständigen Chat**: Definieren Sie diese Einstellung, um eine benutzerfreundliche und aussagekräftige Einstellung für den Server oder Pool bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="b0f0f-108">Diese Einstellung wird der Benutzer mit einer bestimmten Persistent Chat Server oder basierend auf den Anzeigenamen anstelle einer schwieriger zu verstehen, vollständig qualifizierten Domänennamen Persistent Chat Server Pool zuzuordnen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="b0f0f-109">**Port für den beständigen Chat**: Geben Sie den Port an, der für den beständigen Chat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="b0f0f-110">Bearbeiten Sie die Einstellungen unter **Zuordnungen** für den beständigen Chat-Server oder Persistent Chat Server Pool, indem konfigurieren diese Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="b0f0f-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b0f0f-111">**Zuordnungen**</span><span class="sxs-lookup"><span data-stu-id="b0f0f-111">**Associations**</span></span>
  
- <span data-ttu-id="b0f0f-112">**SQL Server-Speicher**: Wählen Sie den SQL Server-Speicher und die optionale benannte Instanz in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="b0f0f-113">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-114">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** aus, wenn Sie die Spiegelung für den primären SQL Server-Speicher aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-115">Wenn Sie SQL Server-speicherspiegelung aktiviert haben, wählen Sie den Speicher und die Instanz in der Liste **SQL Server-Spiegelung Speicher**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="b0f0f-116">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-117">Wählen Sie das Kontrollkästchen **mithilfe von SQL Server-spiegelungszeugen, um die Aktivierung des automatischen Failovers** Wunsch Automatisches Failover für den primären SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-118">Wenn Sie SQL Server-Speicher-spiegelungszeugen zur Aktivierung des automatischen Failovers aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0f0f-119">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz für den Zeugenspeicher zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0f0f-120">Aktivieren Sie das Kontrollkästchen **backup SQL Server-Speicher zum Aktivieren der Wiederherstellung verwenden** , wenn Sie die Verwendung von SQL Server-Wiederherstellung aktivieren möchten</span><span class="sxs-lookup"><span data-stu-id="b0f0f-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="b0f0f-121">Wenn Sie die Notfallwiederherstellung aktiviert haben, wählen Sie den Speicher und die Instanz in der Liste **SQL Server-Speicher für Sicherung** aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0f0f-122">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-123">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** aus, wenn Sie die Spiegelung für die Sicherung SQL Server-Spiegelung Store aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="b0f0f-124">Wenn Sie Sicherung SQL Server-speicherspiegelung aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste **SQL Server-Sicherungsinstanz Speicher für Spiegelung**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0f0f-125">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-126">Aktivieren Sie das Kontrollkästchen **mithilfe von SQL Server-spiegelungszeugen um Automatisches Failover zu aktivieren** , wenn Sie Automatisches Failover des backup SQL Server-Speichers möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-127">Wenn Sie SQL Server-Speicher-spiegelungszeugen zur Aktivierung des automatischen Failovers aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0f0f-128">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz für den Zeugenspeicher zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0f0f-129">Aktivieren Sie das Kontrollkästchen **Konformität aktivieren**, wenn Sie die Verwendung einer Konformitätsdatenbank ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="b0f0f-130">Wenn Sie die Konformität aktiviert haben, wählen Sie den Speicher und die Instanz in der Liste **SQL Server-Speicher für Konformität** aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0f0f-131">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-132">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** aus, wenn Sie die Spiegelung für die Einhaltung von Bestimmungen SQL Server-Speicher aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-133">Wenn Sie Compliance SQL Server-speicherspiegelung aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste **Compliance SQL Server-Speicher für Spiegelung**aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0f0f-134">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-135">Aktivieren Sie das Kontrollkästchen **mithilfe von SQL Server-spiegelungszeugen um Automatisches Failover zu aktivieren** , wenn Sie Automatisches Failover von SQL Server-Speichers Compliance möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-136">Wenn Sie SQL Server-Speicher-spiegelungszeugen zur Aktivierung des automatischen Failovers aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0f0f-137">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz für den Zeugenspeicher zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0f0f-138">Wenn Sie die Konformität aktiviert haben, wählen Sie den Speicher und die Instanz in der Liste **SQL Server-Speicher für Sicherungskonformität** aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0f0f-139">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-140">Aktivieren Sie das Kontrollkästchen **Aktivieren SQL Server-Speicher für Spiegelung** aus, wenn Sie die Spiegelung für die Einhaltung von Bestimmungen SQL Server-Speicher aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-141">Wenn Sie Compliance SQL Server-speicherspiegelung aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste **SQL Server-Sicherung konformitätsinstanz Speicher für Spiegelung**.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0f0f-142">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0f0f-143">Aktivieren Sie das Kontrollkästchen **mithilfe von SQL Server-spiegelungszeugen um Automatisches Failover zu aktivieren** , wenn Sie Automatisches Failover von SQL Server-Speichers für Konformität möchten.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0f0f-144">Wenn Sie SQL Server-Speicher-spiegelungszeugen zur Aktivierung des automatischen Failovers aktiviert haben, wählen Sie den Speicher und die Instanz aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0f0f-145">Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher und eine optionale Instanz für den Zeugenspeicher zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0f0f-146">**Datei speichern** Wählen Sie aus der Liste einen Dateispeicherort aus, oder klicken Sie auf **neu** , um einen neuen Dateispeicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
 <span data-ttu-id="b0f0f-147">**OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="b0f0f-148">**Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="b0f0f-149">**Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.</span><span class="sxs-lookup"><span data-stu-id="b0f0f-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0f0f-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0f0f-150">See also</span></span>

#### 

[<span data-ttu-id="b0f0f-151">Planen Sie für Persistent Chatserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0f0f-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b0f0f-152">Hinzufügen von Persistent Chat Server zu Ihrer Skype für Business Server 2015 Topologie</span><span class="sxs-lookup"><span data-stu-id="b0f0f-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="b0f0f-153">Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0f0f-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

