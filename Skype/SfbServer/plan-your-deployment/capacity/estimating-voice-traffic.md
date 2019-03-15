---
title: Schätzen von VoIP-Nutzung und-Datenverkehr für Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Die folgenden Metrik können Sie die Schätzung des Benutzerdatenverkehrs an jedem Standort und die Anzahl der Ports, die zur Unterstützung dieser Datenverkehr erforderlich sind.
ms.openlocfilehash: e69c559c4ed56010dac3a81a97837f1131e62a2e
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "25376007"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="717b1-103">Schätzen von VoIP-Nutzung und-Datenverkehr für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="717b1-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="717b1-104">Die folgenden Metrik können Sie die Schätzung des Benutzerdatenverkehrs an jedem Standort und die Anzahl der Ports, die zur Unterstützung dieser Datenverkehr erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="717b1-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="717b1-105">Für **geringes Datenverkehrsaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="717b1-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="717b1-106">Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="717b1-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="717b1-107">Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="717b1-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="717b1-108">Die Anzahl von Ports bestimmt wiederum die Anzahl der Vermittlungsserver und Gateways, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="717b1-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="717b1-109">Die Gateways public switched Telephone Network, (PSTN), dass die meisten Organisationen erwägen, Bereich Größe 2 Ports bis 960 Ports.</span><span class="sxs-lookup"><span data-stu-id="717b1-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="717b1-110">(Es gibt sogar größere Gateways, aber diese werden hauptsächlich von Telefoniedienstanbieter verwendet.)</span><span class="sxs-lookup"><span data-stu-id="717b1-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="717b1-p102">Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="717b1-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

