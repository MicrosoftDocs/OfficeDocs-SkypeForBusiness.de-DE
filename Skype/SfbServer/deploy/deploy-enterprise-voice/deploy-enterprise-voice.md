---
title: Bereitstellen von Enterprise-VoIP in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen von Enterprise-VoIP für Skype für Business Server am zentralen Standort.'
ms.openlocfilehash: db1048e4050ec5f9d58436bba5d5c3282f0c4b7f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968483"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="264cb-103">Bereitstellen von Enterprise-VoIP in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-103">Deploy Enterprise Voice in Skype for Business Server</span></span> 
 
<span data-ttu-id="264cb-104">**Zusammenfassung:** Informationen Sie zum Bereitstellen von Enterprise-VoIP für Skype für Business Server am zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="264cb-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>
  
<span data-ttu-id="264cb-105">Verwenden Sie dieses Thema zum Bereitstellen von Enterprise-VoIP an einem zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="264cb-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="264cb-106">Zum Bereitstellen von Enterprise-VoIP an einem Zweigstellenstandort, fahren Sie mit [Zweigniederlassungen bereitstellen](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="264cb-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="264cb-107">Dieser Abschnitt enthält Verfahren für Bereitstellungen, in denen ein Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server verbunden ist, wie empfohlen und für Bereitstellungen mit einen eigenständigen vermittlungsserverpool. Sie können die folgende Inhalte überspringen, wenn Sie die Topologie-Generator zum Definieren und Veröffentlichen einer Topologie, die einen Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server collocates, da Bereitstellungsassistenten bereits automatisch der Dateien für Installation verwendet Vermittlungsserver, wenn Sie Dateien für den Front-End-Server-Pool oder Standard Edition-Server installiert haben:</span><span class="sxs-lookup"><span data-stu-id="264cb-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="264cb-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="264cb-108">In this section</span></span>

- [<span data-ttu-id="264cb-109">Sicherheit und Konfiguration erforderlichen Komponenten für Enterprise-VoIP in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="264cb-110">Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="264cb-111">Definieren eines Gateways im Topologie-Generator in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="264cb-112">Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="264cb-113">Installieren der Dateien für den Vermittlungsserver in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="264cb-114">Konfigurieren von Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="264cb-115">Erstellen oder Ändern einer übersetzungsregel für Rufnummernanzeige in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="264cb-116">Erstellen oder Ändern einer übersetzungsregel für die gewählte ID Präsentation in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="264cb-117">Erstellen oder Ändern einer Normalisierungsregel in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="264cb-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="264cb-118">Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)
    
- [<span data-ttu-id="264cb-119">Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="264cb-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="264cb-120">Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="264cb-121">Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="264cb-122">Bereitstellen von Funktionen für die anrufverwaltung in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="264cb-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="264cb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="264cb-123">See also</span></span>

[<span data-ttu-id="264cb-124">Planen Sie für Enterprise-VoIP in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="264cb-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

