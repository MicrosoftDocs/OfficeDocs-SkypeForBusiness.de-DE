---
title: Exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server mithilfe des Skype for Business Server-Control Panels eine sprach Routing-Konfigurationsdatei exportieren oder importieren.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239915"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="15f6e-103">Exportieren oder Importieren einer sprach Routen-Konfigurationsdatei in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="15f6e-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="15f6e-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie mithilfe des Skype for Business Server-Control Panels eine sprach Routing-Konfigurationsdatei in Skype for Business Server exportieren oder importieren.</span><span class="sxs-lookup"><span data-stu-id="15f6e-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="15f6e-105">Wenn Sie Ihre VoIP-Routingkonfiguration speichern möchten, ohne sie zu veröffentlichen, führen Sie die folgenden Schritte aus, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="15f6e-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="15f6e-106">Wenn Sie eine sprach Routing-Konfigurationsdatei (. vcfg) importieren, aber in der Zwischenzeit Änderungen an der sprach Routingkonfiguration auf dem Server vorgenommen wurden, geben die Seiten in der Gruppe **VoIP-Routing** in der Skype for Business Server-Systemsteuerung an, dass es sind nicht festgeschriebene Änderungen an der sprach Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="15f6e-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="15f6e-107">Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="15f6e-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="15f6e-108">Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten sprach Konfigurationsdatei (vcfg) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="15f6e-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="15f6e-109">So können Sie während mehrerer Sitzungen Änderungen an der sprach Routingkonfiguration vornehmen, bevor Sie die Änderungen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="15f6e-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="15f6e-110">So exportieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="15f6e-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="15f6e-111">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="15f6e-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="15f6e-112">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="15f6e-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="15f6e-113">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="15f6e-114">Klicken Sie im Menü **Aktionen** auf **Konfiguration exportieren**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="15f6e-115">Geben Sie einen Speicherort und Dateinamen an und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="15f6e-116">So importieren Sie eine VoIP-Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="15f6e-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="15f6e-117">Melden Sie sich als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="15f6e-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="15f6e-118">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="15f6e-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="15f6e-119">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="15f6e-120">Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="15f6e-121">Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="15f6e-122">Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="15f6e-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15f6e-123">Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="15f6e-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="15f6e-124">Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15f6e-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

