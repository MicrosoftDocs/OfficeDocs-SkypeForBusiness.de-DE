---
title: Schätzen der sprach Nutzung und des Datenverkehrs für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jeder Website und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816064"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="b13b3-103">Schätzen der sprach Nutzung und des Datenverkehrs für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b13b3-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="b13b3-104">Sie können die folgende Metrik verwenden, um den Benutzerdatenverkehr an jeder Website und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b13b3-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="b13b3-105">Für **geringes Datenverkehrsaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="b13b3-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="b13b3-106">Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="b13b3-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="b13b3-107">Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.</span><span class="sxs-lookup"><span data-stu-id="b13b3-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="b13b3-108">Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b13b3-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="b13b3-109">Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 Anschlüssen bis zu 960-Ports in Frage kämen.</span><span class="sxs-lookup"><span data-stu-id="b13b3-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="b13b3-110">(Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="b13b3-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="b13b3-p102">Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="b13b3-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

