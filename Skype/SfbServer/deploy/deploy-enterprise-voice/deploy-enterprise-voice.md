---
title: Bereitstellen von Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Enterprise-VoIP für Skype for Business Server an einem zentralen Standort bereitstellen.'
ms.openlocfilehash: 3e85ac96415788e8e15ba1ed11786864b6fc3124
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245427"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="c10d2-103">Bereitstellen von Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="c10d2-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Enterprise-VoIP für Skype for Business Server an einem zentralen Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c10d2-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="c10d2-105">Verwenden Sie dieses Thema, um Enterprise-VoIP an einem zentralen Standort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c10d2-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="c10d2-106">Wenn Sie Enterprise-VoIP an einer Zweigstelle bereitstellen möchten, wechseln Sie zum [Bereitstellen von Zweigstellen](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="c10d2-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="c10d2-107">Dieser Abschnitt enthält Verfahren für Bereitstellungen, bei denen ein Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server, wie empfohlen, und auch bei Bereitstellungen mit einem eigenständigen vermittlungsserverpool zusammengestellt wird. Sie können den folgenden Inhalt überspringen, wenn Sie mithilfe des Topologie-Generators eine Topologie definiert und veröffentlicht haben, die einen Vermittlungsserver auf jedem Front-End-Server oder Standard Edition-Server Kollokatoren, weil die Dateien von dem Bereitstellungs-Assistenten bereits automatisch installiert wurden Vermittlungsserver, wenn Sie Dateien für Ihren Front-End-Serverpool oder Standard Edition-Server installiert haben:</span><span class="sxs-lookup"><span data-stu-id="c10d2-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="c10d2-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="c10d2-108">In this section</span></span>

- [<span data-ttu-id="c10d2-109">Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="c10d2-110">Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="c10d2-111">Definieren eines Gateways im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="c10d2-112">Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="c10d2-113">Installieren der Dateien für den Vermittlungsserver in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="c10d2-114">Konfigurieren von Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="c10d2-115">Erstellen oder Ändern einer Übersetzungsregel für die Anrufer-ID-Präsentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="c10d2-116">Erstellen oder Ändern einer Übersetzungsregel für die benannte ID-Präsentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="c10d2-117">Erstellen oder Ändern einer Normalisierungsregel in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c10d2-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="c10d2-118">Erstellen oder Ändern eines Wählplans in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="c10d2-119">Konfigurieren von VoIP-Richtlinien, PSTN-Nutzungsdaten Sätzen und VoIP-Routen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c10d2-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="c10d2-120">Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="c10d2-121">Bereitstellen von erweiterten Enterprise-VoIP-Features in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="c10d2-122">Bereitstellen von anrufverwaltungsfunktionen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c10d2-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="c10d2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c10d2-123">See also</span></span>

[<span data-ttu-id="c10d2-124">Planen von Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c10d2-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

