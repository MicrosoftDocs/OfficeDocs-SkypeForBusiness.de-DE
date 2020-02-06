---
title: Planen von Edge-Server-Bereitstellungen in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Sie Ihre Skype for Business Server-Edge-Umgebung. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.'
ms.openlocfilehash: f19f00aab393ed94735f47f2e66ab0a2869d2d7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803365"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="d56f1-104">Planen von Edge-Server-Bereitstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d56f1-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="d56f1-105">**Zusammenfassung:** Planen Sie Ihre Skype for Business Server-Edge-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="d56f1-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="d56f1-106">Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="d56f1-107">Wenn Sie über eine Skype for Business Server-Umgebung verfügen, die intern gut funktioniert, besteht der nächste Schritt darin, einen Edgeserver oder einen Edge-Pool für die Umgebung einzuführen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="d56f1-108">Diese Rolle wäre von entscheidender Bedeutung, wenn Sie möchten, dass die von Skype for Business Server bereitgestellten Dienste von Personen verwendet werden, die sich außerhalb Ihres internen Netzwerks befinden.</span><span class="sxs-lookup"><span data-stu-id="d56f1-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="d56f1-109">Zu diesen können folgende gehören:</span><span class="sxs-lookup"><span data-stu-id="d56f1-109">These can potentially include:</span></span>
  
- <span data-ttu-id="d56f1-110">Remotebenutzer: Mitarbeiter, die vorübergehend oder längerfristig standortextern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d56f1-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="d56f1-111">Federated-Benutzer: Mitarbeiter Ihrer Partnerorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="d56f1-112">Mobile Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d56f1-112">Mobile Users.</span></span>
    
- <span data-ttu-id="d56f1-113">Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Meetings und Präsentationen einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="d56f1-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="d56f1-114">Der Zugriff externer Benutzer, was von Edge-Servern bereitgestellt wird, ermöglicht dies.</span><span class="sxs-lookup"><span data-stu-id="d56f1-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="d56f1-115">Ihre internen Benutzer können die folgenden Dienste nutzen, die von Ihrer Skype for Business Server-Bereitstellung gehostet werden:</span><span class="sxs-lookup"><span data-stu-id="d56f1-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="d56f1-116">Chat und Anwesenheitsinformationen für die Kommunikation: autorisierte externe Benutzer können an Chat Unterhaltungen und Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="d56f1-117">Sie können Anwesenheitsinformationen für andere Benutzer erhalten (die auch ihre Anwesenheitsinformationen erhalten).</span><span class="sxs-lookup"><span data-stu-id="d56f1-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="d56f1-118">Wenn Sie einen öffentlichen Chat-Anbieter verwenden, sind Sie nicht in der Lage, mehrteilige Konferenzen zu Unternehmen, da es sich um eine strikte Peer-to-Peer-Kommunikation handelt.</span><span class="sxs-lookup"><span data-stu-id="d56f1-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="d56f1-119">Es werden jedoch sowohl SIP-als auch XMPP-Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d56f1-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="d56f1-120">Audio/Video-Konferenzen (A/V): autorisierte externe Benutzer können an Ihren Skype for Business Server-Audio-und Videokonferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="d56f1-121">Webkonferenzen: ihre autorisierten externen Benutzer können an Ihren Skype for Business-Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="d56f1-122">Sie können auch die Teilnahme an Remotebenutzern, Verbundbenutzern und anonymen Benutzern aktivieren, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="d56f1-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="d56f1-123">Öffentliche Chat-Benutzer können nicht an Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="d56f1-124">Darüber hinaus gibt es Optionen, mit denen diese Benutzer an der Anwendungs-und Desktopfreigabe teilnehmen und sogar als Besprechungsorganisatoren oder Referenten fungieren können.</span><span class="sxs-lookup"><span data-stu-id="d56f1-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="d56f1-125">Der Zugriff auf mobile Geräte wird ebenso wie Enterprise-VoIP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d56f1-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="d56f1-126">Sie können externe Benutzer zu Besprechungen einladen, an denen diese teilnehmen sollen, und sogar anonyme Benutzer, wenn Sie diesen die Berechtigungen geben möchten.</span><span class="sxs-lookup"><span data-stu-id="d56f1-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="d56f1-p108">Wenn dies sinnvoll für Ihr Unternehmen erscheint, wird die Planung einer Edge-Umgebung eine große Hilfe für die Bereitstellung sein. Weitere Themen können Sie nachfolgend lesen.</span><span class="sxs-lookup"><span data-stu-id="d56f1-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="d56f1-129">XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d56f1-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d56f1-130">Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="d56f1-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="d56f1-131">Themen für die Planung:</span><span class="sxs-lookup"><span data-stu-id="d56f1-131">Planning topics:</span></span>

<span data-ttu-id="d56f1-132">Zu den Artikeln für die Planung gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="d56f1-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="d56f1-133">Systemanforderungen des Edgeservers in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d56f1-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="d56f1-134">Umgebungsanforderungen des Edgeservers in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d56f1-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="d56f1-135">Edgeserver-Szenarien in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d56f1-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

