---
title: Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server mithilfe des Skype for Business Server-Control Panels Änderungen an der sprach Routing-Konfiguration überprüfen, veröffentlichen oder stornieren können.'
ms.openlocfilehash: 12cf80c2a14d3bad532aaf21a942536f44537300
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766958"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="d35d9-103">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d35d9-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="d35d9-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Änderungen an der sprach Routingkonfiguration in Skype for Business Server über die Skype for Business Server-Systemsteuerung überprüfen, veröffentlichen oder stornieren können.</span><span class="sxs-lookup"><span data-stu-id="d35d9-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="d35d9-105">Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d35d9-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d35d9-106">Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt.</span><span class="sxs-lookup"><span data-stu-id="d35d9-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d35d9-p101">Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl **Commit für alle Element ausführen** veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl **Noch nicht übernommene Änderungen überprüfen** aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d35d9-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d35d9-110">Wenn Sie die Seiten in der Gruppe **VoIP-Routing** verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="d35d9-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="d35d9-111">Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d35d9-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="d35d9-112">Ausführliche Informationen finden Sie unter [exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="d35d9-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="d35d9-113">So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="d35d9-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="d35d9-114">Melden Sie sich als Mitglied der Gruppe **RTCUniversalServerAdmins** oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder CsAdministrator beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="d35d9-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="d35d9-115">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d35d9-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d35d9-116">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="d35d9-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="d35d9-117">Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.</span><span class="sxs-lookup"><span data-stu-id="d35d9-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="d35d9-118">Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="d35d9-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="d35d9-119">Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="d35d9-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="d35d9-120">Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.</span><span class="sxs-lookup"><span data-stu-id="d35d9-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="d35d9-121">Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.</span><span class="sxs-lookup"><span data-stu-id="d35d9-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="d35d9-122">Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d35d9-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="d35d9-123">Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d35d9-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="d35d9-124">Wenn die Änderungen von der Skype for Business Server-Systemsteuerung übernommen wurden, wird die Meldung **erfolgreich veröffentlichte sprach Routingkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d35d9-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

