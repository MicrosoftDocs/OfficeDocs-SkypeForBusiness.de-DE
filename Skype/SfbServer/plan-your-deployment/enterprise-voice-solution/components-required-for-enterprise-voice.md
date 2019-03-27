---
title: Für Enterprise-VoIP in Skype für Business Server erforderlichen Komponenten
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype für Business Server.
ms.openlocfilehash: 870110c702c36660652fb08cff702453573349a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884160"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="8b676-103">Für Enterprise-VoIP in Skype für Business Server erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="8b676-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="8b676-104">Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="8b676-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="8b676-105">Die folgenden Komponenten sind für die Bereitstellung von Enterprise-VoIP in Ihrer Topologie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b676-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="8b676-106">Eine oder mehrere Vermittlungsserver, die Signalisierung und in einigen Konfigurationen, Medien zwischen Ihrem internen Skype für Business Server, Enterprise-VoIP-Infrastruktur und ein Gateway public switched Telephone Network, (PSTN) oder ein Session Initiation-Protokoll übersetzen Trunks (SIP).</span><span class="sxs-lookup"><span data-stu-id="8b676-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="8b676-107">Der Vermittlungsserver sind die wichtigsten Komponente in der Enterprise-VoIP-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8b676-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="8b676-108">Weitere Informationen finden Sie unter [Mediation Server Component in Skype für Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="8b676-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="8b676-109">Vermittlungsserver können mit dem Front-End-Server verbunden oder als eigenständiger Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b676-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="8b676-110">PSTN-Konnektivitätskomponenten, die SIP-Trunks oder PSTN-Gateways angeben können.</span><span class="sxs-lookup"><span data-stu-id="8b676-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="8b676-111">Weitere Informationen finden Sie unter [PSTN Connectivity Komponenten in Skype für Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8b676-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="8b676-112">Edge-Server, der die Verwendung von Enterprise-VoIP-Funktionen von den Benutzern ermöglicht, wenn sie sich außerhalb der Firewall Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="8b676-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="8b676-113">Der Zugriffs-Edgeservers Service bietet SIP-Signale für Anrufe von Skype für Unternehmensbenutzer, die sich außerhalb der Firewall Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="8b676-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="8b676-114">Der A/V-Edgedienst ermöglicht es Medien, Firewalls und NAT zu passieren.</span><span class="sxs-lookup"><span data-stu-id="8b676-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="8b676-115">Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="8b676-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="8b676-p104">Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für diesen bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="8b676-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="8b676-118">Darüber hinaus werden einige Enterprise-VoIP-Komponenten auf Front-End-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b676-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="8b676-119">Ausführliche Informationen zu diesen Komponenten finden Sie unter [Front-End-Server-VoIP-Komponenten für Skype für Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="8b676-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

