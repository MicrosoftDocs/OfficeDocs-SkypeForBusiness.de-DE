---
title: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Zusammenfassung: Informationen Sie zum Überprüfen, veröffentlichen oder verwerfen routing Änderungen VoIP-Konfiguration in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 9878e719234a5d7eff2e7321fa71e30c094d489a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897706"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="f2e31-103">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="f2e31-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="f2e31-104">**Zusammenfassung:** Informationen Sie zum Überprüfen, veröffentlichen oder verwerfen routing Änderungen VoIP-Konfiguration in Skype für Business Server mithilfe der Skype für Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f2e31-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="f2e31-105">Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="f2e31-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f2e31-106">Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt.</span><span class="sxs-lookup"><span data-stu-id="f2e31-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f2e31-p101">Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl **Commit für alle Element ausführen** veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl **Noch nicht übernommene Änderungen überprüfen** aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2e31-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2e31-110">Wenn Sie die Seiten in der Gruppe **VoIP-Routing** verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="f2e31-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="f2e31-111">Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f2e31-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="f2e31-112">Weitere Informationen hierzu finden Sie unter [Exportieren oder importieren eine VoIP-Routenkonfiguration Wiederherstellungsdatei Skype für Unternehmen](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="f2e31-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="f2e31-113">So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="f2e31-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="f2e31-114">Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder CsAdministrator beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="f2e31-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f2e31-115">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f2e31-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f2e31-116">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="f2e31-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f2e31-117">Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.</span><span class="sxs-lookup"><span data-stu-id="f2e31-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="f2e31-118">Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f2e31-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="f2e31-119">Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="f2e31-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="f2e31-120">Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.</span><span class="sxs-lookup"><span data-stu-id="f2e31-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="f2e31-121">Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.</span><span class="sxs-lookup"><span data-stu-id="f2e31-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="f2e31-122">Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2e31-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="f2e31-123">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2e31-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="f2e31-124">Wenn Skype Business Server-Systemsteuerung Änderungen verpflichtet hat, wird die Meldung **VoIP-Routingkonfiguration erfolgreich veröffentlicht** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2e31-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

