---
title: Bereitstellen von Enterprise-VoIP in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen von Enterprise-VoIP für Skype für Business Server 2015 an einem zentralen Standort.'
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="e0fb5-103">Bereitstellen von Enterprise-VoIP in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e0fb5-104">**Zusammenfassung:** Informationen Sie zum Bereitstellen von Enterprise-VoIP für Skype für Business Server 2015 an einem zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="e0fb5-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="e0fb5-105">Verwenden Sie dieses Thema zum Bereitstellen von Enterprise-VoIP an einem zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="e0fb5-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="e0fb5-106">Zum Bereitstellen von Enterprise-VoIP an einem Zweigstellenstandort, fahren Sie mit [Zweigniederlassungen bereitstellen](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="e0fb5-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="e0fb5-107">Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server verbunden ist, wie empfohlen und für Bereitstellungen mit einen eigenständigen vermittlungsserverpool. Sie können die folgende Inhalte überspringen, wenn Sie die Topologie-Generator zum Definieren und Veröffentlichen einer Topologie, die einen Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server collocates, da Bereitstellungsassistenten bereits automatisch der Dateien für Installation verwendet Vermittlungsserver, wenn Sie Dateien für den Front-End-Server-Pool oder Standard Edition-Server installiert haben:</span><span class="sxs-lookup"><span data-stu-id="e0fb5-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="e0fb5-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="e0fb5-108">In this section</span></span>

- [<span data-ttu-id="e0fb5-109">Sicherheit und Konfiguration erforderlichen Komponenten für Enterprise-VoIP in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="e0fb5-110">Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="e0fb5-111">Definieren eines Gateways im Topologie-Generator in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="e0fb5-112">Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="e0fb5-113">Installieren der Dateien für den Vermittlungsserver in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="e0fb5-114">Konfigurieren von Trunks in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="e0fb5-115">Erstellen oder Ändern einer übersetzungsregel für Rufnummernanzeige in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="e0fb5-116">Erstellen oder Ändern einer übersetzungsregel für die gewählte ID Präsentation in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="e0fb5-117">Erstellen oder Ändern einer Normalisierungsregel in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="e0fb5-118">Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="e0fb5-119">Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="e0fb5-120">Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="e0fb5-121">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="e0fb5-122">Bereitstellen von Funktionen für die anrufverwaltung in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="e0fb5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0fb5-123">See also</span></span>

#### 

[<span data-ttu-id="e0fb5-124">Planen Sie für Enterprise-VoIP in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e0fb5-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

