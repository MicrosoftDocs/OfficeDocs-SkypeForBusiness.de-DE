---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server können mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht identisch sind, und Administratoren müssen das Cmdlet Get-cstrunk "verwenden, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048178"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="f226c-103">Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f226c-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="f226c-104">In Skype for Business Server können mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht identisch sind und dass Administratoren das Cmdlet [Get-cstrunk "](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f226c-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="f226c-105">Das Cmdlet Get-cstrunk "kann entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f226c-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="f226c-106">**So zeigen Sie Informationen für alle SIP-Trunks an**</span><span class="sxs-lookup"><span data-stu-id="f226c-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="f226c-107">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="f226c-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="f226c-108">**So zeigen Sie Informationen für einen bestimmten SIP-Trunk an**</span><span class="sxs-lookup"><span data-stu-id="f226c-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="f226c-109">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="f226c-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="f226c-110">**Anzeigen von Informationen für alle einem Pool zugeordneten SIP-Trunks**</span><span class="sxs-lookup"><span data-stu-id="f226c-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="f226c-111">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="f226c-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
