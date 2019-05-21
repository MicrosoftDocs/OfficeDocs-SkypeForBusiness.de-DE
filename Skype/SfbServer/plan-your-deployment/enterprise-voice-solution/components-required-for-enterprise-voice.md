---
title: Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype for Business Server.
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277006"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="fcf7e-103">Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="fcf7e-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="fcf7e-104">Eine Zusammenfassung der Enterprise-VoIP-Komponenten in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="fcf7e-105">Zur Bereitstellung von Enterprise-VoIP sind die folgenden Komponenten in Ihrer Topologie erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="fcf7e-106">Einen oder mehrere Vermittlungsserver, die Signalübertragungen und in einigen Konfigurationen Medien zwischen Ihrem internen Skype for Business-Server, der Enterprise-VoIP-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network) oder einem Sitzungs Initiierungs Protokoll übersetzen (SIP) trunk.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="fcf7e-107">Die Vermittlungsserver sind die wichtigste Komponente in Ihrer Enterprise-VoIP-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="fcf7e-108">Weitere Informationen finden Sie unter [Vermittlungs Server Komponente in Skype for Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="fcf7e-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="fcf7e-109">Vermittlungsserver können mit Front-End-Servern oder als eigenständige Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="fcf7e-110">PSTN-Konnektivitäts-Komponenten, die SIP-Trunks oder PSTN-Gateways umfassen können.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="fcf7e-111">Weitere Informationen finden Sie unter [Komponenten der PSTN-Konnektivität in Skype for Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="fcf7e-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="fcf7e-112">Edgeserver, der die Verwendung von Enterprise-VoIP-Features durch Ihre Benutzer ermöglicht, wenn diese sich außerhalb der Firewall Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="fcf7e-113">Der Zugriffs-Edgedienst bietet SIP-Signalisierungen für Anrufe von Skype for Business-Benutzern, die sich außerhalb der Firewall Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="fcf7e-114">Der A/V-Edgedienst ermöglicht es Medien, Firewalls und NAT zu passieren.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="fcf7e-115">Anrufer, die einen Unified Communications-Client (UC) außerhalb der Unternehmensfirewall verwenden, benötigen den A/V-Edgedienst für Einzelgespräche und Telefonkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="fcf7e-p104">Der A/V-Authentifizierungsdienst ist mit dem A/V-Edgedienst verknüpft und stellt Authentifizierungsdienste für diesen bereit. Externe Benutzer, die versuchen, eine Verbindung mit dem A/V-Edgedienst herzustellen, benötigen ein vom A/V-Authentifizierungsdienst bereitgestelltes Authentifizierungstoken, damit ihre Anrufe durchgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="fcf7e-118">Darüber hinaus werden einige Enterprise-VoIP-Komponenten auf Front-End-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fcf7e-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="fcf7e-119">Details zu diesen Komponenten finden Sie unter [VoIP-Komponenten für den Front-End-Server für Skype for Business Server](front-end-server-voip.md) .</span><span class="sxs-lookup"><span data-stu-id="fcf7e-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

