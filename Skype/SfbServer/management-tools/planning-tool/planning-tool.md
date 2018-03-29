---
title: Skype for Business Server 2015 – Planungstool
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Anleitung zur Verwendung der Skype für Business Server 2015-Planungstool.
ms.openlocfilehash: 9995b17274377025f2531ca53966859d1ca716b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="cc0d8-103">Skype for Business Server 2015 – Planungstool</span><span class="sxs-lookup"><span data-stu-id="cc0d8-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="cc0d8-104">Anleitung zur Verwendung der Skype für Business Server 2015-Planungstool.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="cc0d8-105">Die Skype für Business Server 2015 Planungstool ist ein Assistent gesteuerte, Interview-ähnlichen Tool, das Fragen zu den Skype für Business Server 2015 Topologie gefragt werden, den Sie entwerfen.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="cc0d8-106">Das Planungstool verwendet die Informationen bereitgestellt, gekoppelt mit bevorzugten Methoden für das Entwerfen der Topologie und Kapazität ist eine empfohlene Topologie basierend auf der angegebenen Antworten präsentieren.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="cc0d8-107">Sie können das Planungstool aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkID=282725)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-107">You can download the Planning Tool from the [Microsoft Downloads Center](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="cc0d8-108">Schließlich wird das Ziel des Planungstool zur Vereinfachung der potenziellen Komplexität einer vollständigen Skype für Business Server 2015 Topologie zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="cc0d8-109">Das Tool stellt außerdem kontextbezogene Verweise auf die im Tool enthaltene Planungs- und Bereitstellungsdokumentation bereit, sofern eine Internetverbindung zur Microsoft TechNet-Website verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>
  
<span data-ttu-id="cc0d8-110">Nach der Anpassung der Topologie an die Infrastruktur TCP/IP-Adressen und vollständig qualifizierten Domänennamen (FQDNs) zur Verfügung Planungstool eine Reihe von Berichten, die Benennung Domain Name System (DNS), Firewall-Regeln, Zertifikate und vieles mehr zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="cc0d8-111">Die Verwendung dieses Tools stellt den ersten Schritt bei der Planung Ihrer Implementierung dar.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="cc0d8-112">Im nächste Schritt würde werden Einzelheiten Ihrer Website-Informationen in der [Skype für Business Server 2015 Kapazitätsrechner](https://www.microsoft.com/en-us/download/details.aspx?id=51196)eingeben, die Sie nach Bedarf anpassen, verwenden Sie die [Skype für Business Server 2015 Stress and Performance-Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) simulieren und Überprüfen der Implementierung Bedürfnisse Ihre.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="cc0d8-113">Das Planungstool bietet auch die Möglichkeit, Informationen in zwei Formaten exportieren:</span><span class="sxs-lookup"><span data-stu-id="cc0d8-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="cc0d8-114">Microsoft Excel (.xml-Arbeitsblatt)</span><span class="sxs-lookup"><span data-stu-id="cc0d8-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="cc0d8-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="cc0d8-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="cc0d8-116">In den folgenden Themen vorgestellt und das Planungstool detail.</span><span class="sxs-lookup"><span data-stu-id="cc0d8-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cc0d8-117">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="cc0d8-117">In this section</span></span>

- [<span data-ttu-id="cc0d8-118">Installieren des Planungstools in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="cc0d8-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="cc0d8-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="cc0d8-120">Navigieren Sie das Planungstool in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="cc0d8-121">Erstellen der ersten Topologieentwurf für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="cc0d8-122">Bearbeiten Sie die Topologie in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="cc0d8-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="cc0d8-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="cc0d8-124">Überprüfen der Administratorberichte in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="cc0d8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc0d8-125">See also</span></span>

#### 

[<span data-ttu-id="cc0d8-126">Installieren von Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="cc0d8-127">Planen von instant messaging und Anwesenheit in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc0d8-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)

