---
title: Skype for Business Server 2015 Planungs Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Anleitung zur Verwendung des Skype for Business Server 2015 Planungstools.
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050097"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="34f60-103">Skype for Business Server 2015 Planungs Tool</span><span class="sxs-lookup"><span data-stu-id="34f60-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="34f60-104">Anleitung zur Verwendung des Skype for Business Server 2015 Planungstools.</span><span class="sxs-lookup"><span data-stu-id="34f60-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="34f60-105">Das Skype for Business Server 2015 Planungstool ist ein Assistenten gesteuertes, Interview artiges Tool, das Fragen zur Skype for Business Server 2015 Topologie stellt, die Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="34f60-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="34f60-106">Das Planungs Tool verwendet die bereitgestellten Informationen in Verbindung mit bevorzugten Methoden für den Entwurf und die Kapazität der Topologie, um eine empfohlene Topologie basierend auf den bereitgestellten Antworten zu präsentieren.</span><span class="sxs-lookup"><span data-stu-id="34f60-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="34f60-107">Sie können das Planungstool über das [Skype for Business Server 2015 Planungstool](https://go.microsoft.com/fwlink/p/?LinkID=282725)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="34f60-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="34f60-108">Letztendlich besteht das Ziel des Planungstools darin, die potenzielle Komplexität beim Entwurf einer vollständigen Skype for Business Server 2015 Topologie zu verringern.</span><span class="sxs-lookup"><span data-stu-id="34f60-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="34f60-109">Das Tool stellt auch kontextbezogene Verweise auf die Planungs-und Bereitstellungsdokumentation innerhalb des Tools bereit, vorausgesetzt, dass eine Internet Verbindung zum Herstellen einer Verbindung mit der Microsoft-Website verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34f60-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="34f60-110">Nach dem Anpassen der Topologie mit den TCP/IP-Adressen der Infrastruktur und den vollqualifizierten Domänennamen (FQDNs) stellt das Planungs Tool eine Reihe von Berichten zur Verfügung, die Domain Name System (DNS) Benennung, Firewallregeln, Zertifikate und vieles mehr abdecken.</span><span class="sxs-lookup"><span data-stu-id="34f60-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="34f60-111">Die Verwendung dieses Tools ist der erste Schritt bei der Planung Ihrer Implementierung.</span><span class="sxs-lookup"><span data-stu-id="34f60-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="34f60-112">Der nächste Schritt besteht darin, Ihre Website Informationen in den [Skype for Business Server 2015 Kapazitäts Rechner](https://www.microsoft.com/download/details.aspx?id=51196)einzugeben, nach Bedarf anzupassen, dann das [Tool Skype for Business Server 2015 Stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367) zu verwenden, um zu simulieren und zu überprüfen, ob die Implementierung Ihren Anforderungen dient.</span><span class="sxs-lookup"><span data-stu-id="34f60-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="34f60-113">Das Planungs Tool bietet außerdem die Möglichkeit, Informationen in zwei Formaten zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="34f60-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="34f60-114">Microsoft Excel (. XML-Kalkulationstabelle)</span><span class="sxs-lookup"><span data-stu-id="34f60-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="34f60-115">Microsoft Visio (. vdx)</span><span class="sxs-lookup"><span data-stu-id="34f60-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="34f60-116">In den folgenden Themen wird das Planungs Tool vorgestellt und detailliert beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34f60-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="34f60-117">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="34f60-117">In this section</span></span>

- [<span data-ttu-id="34f60-118">Installieren des Planungstools in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="34f60-119">Optionale Software</span><span class="sxs-lookup"><span data-stu-id="34f60-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="34f60-120">Navigieren im Planungs Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="34f60-121">Erstellen des anfänglichen Topologie Designs für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="34f60-122">Bearbeiten der Topologie in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="34f60-123">Bearbeiten des Netzwerk Konfigurations Diagramms</span><span class="sxs-lookup"><span data-stu-id="34f60-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="34f60-124">Überprüfen der Administrator Berichte in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="34f60-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34f60-125">See also</span></span>

[<span data-ttu-id="34f60-126">Installieren von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="34f60-127">Planen von Chatnachrichten und Anwesenheitsinformationen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34f60-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
