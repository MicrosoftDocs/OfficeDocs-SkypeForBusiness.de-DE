---
title: Einstellungen der Anrufsteuerung – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Netzwerks für die Anrufsteuerung müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.
ms.openlocfilehash: b555b7415d96ec99e827ac20a8055fabca3b0a0b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976611"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="1c33e-104">Einstellungen der Anrufsteuerung – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="1c33e-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="1c33e-p102">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können. Nach der Konfiguration des Netzwerks für die Anrufsteuerung müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1c33e-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1c33e-107">Sie können die Anrufsteuerung auch über die Systemsteuerung oder die Verwaltungsshell-Cmdlets aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c33e-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="1c33e-108">Im Abschnitt **Einstellung für Anrufsteuerung** des Dialogfelds **Eigenschaften bearbeiten** Ihres Standorts können Sie die folgenden Einstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="1c33e-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="1c33e-109">**Aktivieren der Anrufsteuerung** Wählen Sie diese Einstellung, um die Anrufsteuerung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c33e-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="1c33e-110">Deaktivieren Sie diese Einstellung, um die Anrufsteuerung für das gesamte Netzwerk zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c33e-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="1c33e-111">Zum Aktivieren der Anrufsteuerung muss das Netzwerk für die Anrufsteuerung konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="1c33e-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="1c33e-112">Weitere Informationen hierzu finden Sie unter [Deploy call Admission Control in Skype für Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1c33e-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="1c33e-113">**Front-End-Pool Call Admission Control ausführen** Wenn Sie die Anrufsteuerung aktiviert haben, können Sie den Pool ändern, der sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c33e-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="1c33e-114">Wählen Sie den Pool in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="1c33e-114">Select the pool from the drop-down list.</span></span>
    

