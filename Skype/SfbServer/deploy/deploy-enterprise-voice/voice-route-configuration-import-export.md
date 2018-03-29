---
title: Exportieren oder Importieren einer VoIP-Routenkonfigurationsdatei in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Zusammenfassung: Informationen Sie zum Exportieren oder importieren eine Konfigurationsdatei VoIP routing in Skype für Business Server 2015 mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 8b676ac6417c172402c231401ea9284fccbb8d97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a><span data-ttu-id="a5c89-103">Exportieren oder Importieren einer VoIP-Routenkonfigurationsdatei in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="a5c89-103">Export or import a voice route configuration file in Skype for Business 2015</span></span>
 
<span data-ttu-id="a5c89-104">**Zusammenfassung:** Informationen Sie zum Exportieren oder importieren eine Konfigurationsdatei VoIP routing in Skype für Business Server 2015 mithilfe der Skype für Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a5c89-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="a5c89-105">Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a5c89-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="a5c89-106">Wenn Sie eine VoIP-routing Konfigurationsdatei (.vcfg) importieren, aber die VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit Änderungen vorgenommen wurden, werden die Seiten in der Gruppe **VoIP-Routing** in Skype Business Server-Systemsteuerung anzugeben, dass es VoIP-routing ohne Commit geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="a5c89-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="a5c89-107">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="a5c89-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="a5c89-108">Wenn Sie an den Einstellungen auf eine beliebige Seite innerhalb der Gruppe ohne Commit Änderungen vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (.vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a5c89-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="a5c89-109">So können Sie VoIP-routing konfigurationsänderungen während mehrerer Sitzungen vor dem Veröffentlichen der Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a5c89-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="a5c89-110">So exportieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a5c89-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="a5c89-111">Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="a5c89-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="a5c89-112">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a5c89-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a5c89-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="a5c89-114">Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="a5c89-115">Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="a5c89-116">So importieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a5c89-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="a5c89-117">Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="a5c89-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="a5c89-118">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a5c89-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a5c89-119">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="a5c89-120">Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="a5c89-121">Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="a5c89-122">Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a5c89-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5c89-123">Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a5c89-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a5c89-124">Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Business 2015](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a5c89-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

