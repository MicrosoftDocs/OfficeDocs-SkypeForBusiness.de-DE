---
title: Trunkeinstellungen – Erweiterung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="7fae4-103">Trunkeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="7fae4-103">Trunk Settings Expander</span></span>
 
<span data-ttu-id="7fae4-104">Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7fae4-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>
  
 <span data-ttu-id="7fae4-105">**Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7fae4-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>
  
 <span data-ttu-id="7fae4-106">**Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7fae4-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>
  
 <span data-ttu-id="7fae4-p101">**Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.</span><span class="sxs-lookup"><span data-stu-id="7fae4-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>
  
 <span data-ttu-id="7fae4-p102">**SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung „TLS“ die Option mit höherer Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7fae4-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
 <span data-ttu-id="7fae4-113">**Zugeordneter Vermittlungsserver**: Wählen Sie eine vorhandene Vermittlungsserver aus der Bereitstellung der SIP-Trunk zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7fae4-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7fae4-114">Nur der stammtrunk kann mit einem Lync Server 2010 oder Lync Server 2013-Vermittlungsservers zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7fae4-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span> 
  
 <span data-ttu-id="7fae4-115">**Zugeordneter Vermittlungsserver Port**: ein erforderlicher Wert, dies ist festgelegt auf den Wert, der den Vermittlungsserver konfiguriert ist lauschen.</span><span class="sxs-lookup"><span data-stu-id="7fae4-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>
  
![Trunkeinstellungen – Erweiterung](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a><span data-ttu-id="7fae4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fae4-117">See also</span></span>

#### 

[<span data-ttu-id="7fae4-118">Prüfliste für die Bereitstellung von SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="7fae4-118">SIP Trunking Deployment Checklist</span></span>](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[<span data-ttu-id="7fae4-119">Komponenten und Topologien für SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="7fae4-119">Components and Topologies for SIP Trunking</span></span>](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

