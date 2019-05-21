---
title: Einstellungen der Anrufsteuerung – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Netzwerks für die Anrufsteuerung müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.
ms.openlocfilehash: 7f5da16b1f3854f676f550c4f2484e950adf86fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305976"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="01e88-104">Einstellungen der Anrufsteuerung – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="01e88-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="01e88-p102">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Netzwerks für die Anrufsteuerung müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="01e88-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="01e88-107">Sie können die Anrufsteuerung auch über die Systemsteuerung oder die Verwaltungsshell-Cmdlets aktivieren.</span><span class="sxs-lookup"><span data-stu-id="01e88-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="01e88-108">Im Abschnitt **Einstellung für Anrufsteuerung** des Dialogfelds **Eigenschaften bearbeiten** Ihres Standorts können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="01e88-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="01e88-109">**Aktivieren der Anrufsteuerung** Wählen Sie diese Einstellung aus, um CAC zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="01e88-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="01e88-110">Deaktivieren Sie diese Einstellung, um die Anrufsteuerung für das gesamte Netzwerk zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="01e88-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="01e88-111">Zum Aktivieren der Anrufsteuerung muss das Netzwerk für die Anrufsteuerung konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="01e88-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="01e88-112">Ausführliche Informationen finden Sie unter [Bereitstellen der Anruf Zulassungs Steuerung in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="01e88-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="01e88-113">**Front-End-Pool zum Ausführen der Anrufsteuerung** Wenn Sie CAC aktiviert haben, können Sie den Pool ändern, der ihn ausführt.</span><span class="sxs-lookup"><span data-stu-id="01e88-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="01e88-114">Wählen Sie den Pool in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="01e88-114">Select the pool from the drop-down list.</span></span>
    

