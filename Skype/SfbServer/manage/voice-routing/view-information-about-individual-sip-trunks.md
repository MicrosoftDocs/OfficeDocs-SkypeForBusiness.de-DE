---
title: Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype für Business Server können mehrere Trunks mit einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht ein und dieselbe sind und Administratoren das Cmdlet "Get-CsTrunk" verwenden müssen, um Informationen zu einer einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: c8463fb23ea09167d760a1b9068235da871792c2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222793"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="69958-103">Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="69958-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="69958-104">In Skype für Business Server können mehrere Trunks mit einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht ein und dieselbe sind und Administratoren das Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) " verwendet werden müssen, um Informationen zu einer einzelnen SIP-Trunk anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69958-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="69958-105">Das Cmdlet "Get-CsTrunk" kann die Skype für Business Server-Verwaltungsshell oder von einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69958-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="69958-106">**Anzeigen von Informationen für alle SIP-Trunks**</span><span class="sxs-lookup"><span data-stu-id="69958-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="69958-107">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="69958-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="69958-108">**Anzeigen von Informationen für einen bestimmten SIP-Trunk**</span><span class="sxs-lookup"><span data-stu-id="69958-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="69958-109">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="69958-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="69958-110">**Anzeigen von Informationen für alle einem Pool zugewiesenen SIP-Trunks**</span><span class="sxs-lookup"><span data-stu-id="69958-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="69958-111">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="69958-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`