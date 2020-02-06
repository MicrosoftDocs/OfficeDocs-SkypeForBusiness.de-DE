---
title: Trunkeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:'
ms.openlocfilehash: 97c1578418fdf46ad39256312d7aa15abd44ff84
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797406"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="30937-103">Trunkeinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="30937-103">Trunk Settings Expander</span></span>

<span data-ttu-id="30937-104">Führen Sie zum Bearbeiten oder Ändern der Einstellungen für einen SIP-Trunk die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="30937-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="30937-105">**Trunkname** ist eine erforderliche Angabe, mit der der SIP-Trunk in der Bereitstellung eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="30937-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="30937-106">**Zugeordnetes PSTN-Gateway**: Wählen Sie ein vorhandenes PSTN-Gateway aus, das in der Bereitstellung definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="30937-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="30937-p101">**Überwachungsport für IP/PSTN-Gateway**: Gibt an, über welchen TCP/IP-Port das Gateway das System auf Anforderungen überwacht. Der erforderliche Wert kann abhängig vom Gatewayhersteller variieren, der Standardwert lautet jedoch Port 5067.</span><span class="sxs-lookup"><span data-stu-id="30937-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="30937-p102">**SIP-Transportprotokoll**: Als Protokoll wird entweder TCP oder TLS verwendet. Als Standardeinstellung ist TLS festgelegt. In der Dokumentation des Gatewayherstellers finden Sie die von Ihrem Gateway unterstützten Protokolle. Wenn das Gateway TLS unterstützt, ist die Standardeinstellung „TLS“ die Option mit höherer Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="30937-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="30937-113">**Zugeordneter Vermittlungsserver**: Wählen Sie einen vorhandenen Vermittlungsserver aus der Bereitstellung aus, der dem SIP-Stamm zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30937-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="30937-114">Nur der Stamm Stamm kann einem Vermittlungs Server zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="30937-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="30937-115">**Zugeordneter Vermittlungsserver-Port**: ein erforderlicher Wert, der auf den Wert festgelegt ist, den der Vermittlungsserver für die Überwachung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="30937-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Trunkeinstellungen – Erweiterung](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="30937-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30937-117">See also</span></span>

[<span data-ttu-id="30937-118">Checkliste für SIP-Trunking-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="30937-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="30937-119">Komponenten und Topologien für SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="30937-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
