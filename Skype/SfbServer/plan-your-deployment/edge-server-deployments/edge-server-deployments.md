---
title: Planen der Edgeserverbereitstellungen in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Sie für Ihre Skype für Business Server 2015 Server Edge-Umgebung. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="44257-104">Planen der Edgeserverbereitstellungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="44257-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="44257-p102">**Zusammenfassung:** Planen Sie Ihre Server-Edge-Umgebung Skype for Business Server 2015. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.</span><span class="sxs-lookup"><span data-stu-id="44257-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="44257-107">Wenn Sie einen Skype für Business Server 2015 Umgebung, die auch intern funktionsfähig ist können Sie, möglicherweise für Sie im nächsten Schritt ein Edge-Server oder einem edgepool für die Umgebung einführen.</span><span class="sxs-lookup"><span data-stu-id="44257-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="44257-108">Diese Rolle wäre wichtiger, wenn der Dienste von Skype für Business Server 2015 von Personen, die sich außerhalb des internen Netzwerks befinden, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="44257-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="44257-109">Zu diesen können folgende gehören:</span><span class="sxs-lookup"><span data-stu-id="44257-109">These can potentially include:</span></span>
  
- <span data-ttu-id="44257-110">Remotebenutzer: Mitarbeiter, die vorübergehend oder längerfristig standortextern arbeiten.</span><span class="sxs-lookup"><span data-stu-id="44257-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="44257-111">Partnerbenutzer: Der Partnerorganisation Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="44257-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="44257-112">Mobile Benutzer.</span><span class="sxs-lookup"><span data-stu-id="44257-112">Mobile Users.</span></span>
    
- <span data-ttu-id="44257-113">Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Meetings und Präsentationen einladen möchten.</span><span class="sxs-lookup"><span data-stu-id="44257-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="44257-114">Zugriff durch externe Benutzer, die ist, was Edge-Server bereitstellen, können all dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="44257-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="44257-115">Internen Benutzern werden die folgenden Dienste nutzen zu können, die von Ihrer Skype für Business Server 2015 Bereitstellung gehostet werden:</span><span class="sxs-lookup"><span data-stu-id="44257-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="44257-116">Instant Messaging und Anwesenheit für die Kommunikation: autorisierte externe Benutzer können in Sofortnachrichtenunterhaltungen und Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="44257-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="44257-117">Sie können Anwesenheitsinformationen für andere Benutzer abrufen (, wer ihre Anwesenheitsinformationen zu abrufen).</span><span class="sxs-lookup"><span data-stu-id="44257-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="44257-118">Nicht möglich, Konferenzen mit mehreren Teilnehmern ist, wenn Sie einen öffentlichen IM-Dienstanbieter verwenden, der streng Peer-zu-Peer-Kommunikation ist.</span><span class="sxs-lookup"><span data-stu-id="44257-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="44257-119">Aber SIP- und XMPP-Protokolle werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="44257-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="44257-120">Audio/Video (A / V) Konferenzen: autorisierte externe Benutzer in Ihrer Skype für Business Server 2015 audio und video-Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="44257-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="44257-121">Webkonferenzen: Ihre autorisierte externe Benutzer in Ihrer Skype für Business-Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="44257-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="44257-122">Wenn Sie möchten, können Sie auch Teilnahme für Remotebenutzer, Verbundbenutzer und anonyme Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44257-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="44257-123">Öffentliche Instant Messaging-Benutzer können nicht an Konferenzen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="44257-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="44257-124">Es gibt auch Optionen, um Benutzern Anwendungs- und Desktopfreigabe teilnehmen, und auch als Besprechungsorganisatoren oder Referenten fungieren.</span><span class="sxs-lookup"><span data-stu-id="44257-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="44257-125">Wie Enterprise-VoIP ist wird, den Zugriff durch Mobile Geräte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="44257-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="44257-126">Sie können externe Benutzer zu Besprechungen einladen, an denen diese teilnehmen sollen, und sogar anonyme Benutzer, wenn Sie diesen die Berechtigungen geben möchten.</span><span class="sxs-lookup"><span data-stu-id="44257-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="44257-p108">Wenn dies sinnvoll für Ihr Unternehmen erscheint, wird die Planung einer Edge-Umgebung eine große Hilfe für die Bereitstellung sein. Weitere Themen können Sie nachfolgend lesen.</span><span class="sxs-lookup"><span data-stu-id="44257-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="44257-129">Themen für die Planung:</span><span class="sxs-lookup"><span data-stu-id="44257-129">Planning topics:</span></span>

<span data-ttu-id="44257-130">Zu den Artikeln für die Planung gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="44257-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="44257-131">Edge-Server System Requirements for Business Server 2015 in Skype</span><span class="sxs-lookup"><span data-stu-id="44257-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="44257-132">Edge-Server-umgebungsanforderungen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="44257-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="44257-133">Edge-Server-Szenarien in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="44257-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

