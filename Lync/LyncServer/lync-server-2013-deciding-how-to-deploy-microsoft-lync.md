---
title: 'Lync Server 2013: entscheiden, wie Microsoft lync bereitgestellt wird'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdd7deb87eef28e3b439f290f6da5a90d2fe50dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="03774-102">Entscheidung über die Bereitstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03774-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03774-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="03774-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="03774-104">Bei der Planung von lync ist die erste wichtige Entscheidung, wie Microsoft lync bereitgestellt wird: als lync Server 2013 lokal oder lync online mit Microsoft Office 365 in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="03774-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="03774-105">**Lync Server 2013 lokal** : diese Option bietet den vollständigen lync-Featuresatz und bietet größtmögliche Flexibilität bei der Konfiguration, dem anpassen und dem Betrieb Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03774-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="03774-106">Alle Server werden vor Ort installiert und von Ihrer Organisation verwaltet.</span><span class="sxs-lookup"><span data-stu-id="03774-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="03774-107">Eine lokale Bereitstellung stellt die gesamte Palette von lync Server Funktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="03774-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="03774-108">**Lync Online in der Cloud** Lync Online richtet sich an Organisationen, die die Kosten und Agilität von Cloud-basierten Chatnachrichten, Anwesenheitsinformationen und Besprechungen ohne Einbußen bei den Geschäftsklassen Funktionen von lync Server nutzen möchten.</span><span class="sxs-lookup"><span data-stu-id="03774-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="03774-109">Mit lync Online wird die erforderliche Serverinfrastruktur von Microsoft bereitgestellt und verwaltet, und die laufende Wartung, Patches und Upgrades werden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="03774-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="03774-110">Einige in einer lokalen Bereitstellung verfügbare Features sind in lync Online nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="03774-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="03774-111">Welcher Bereitstellungstyp am besten für Sie geeignet ist, hängt von den Arbeitsauslastungen, die Sie bereitstellen möchten, sowie vom geografischen und wirtschaftlichen Status Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="03774-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="03774-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="03774-112">Lync Server</span></span>

<span data-ttu-id="03774-113">Eine lokale Lync Server-Bereitstellung eignet sich am besten für folgende Szenarien:</span><span class="sxs-lookup"><span data-stu-id="03774-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="03774-114">**Vollständige Enterprise-VoIP-Funktionen**   Wenn Sie eine vollständige Enterprise-VoIP-Lösung zum Ersetzen Ihrer Nebenstellenanlage oder die erweiterte Anruffunktionen verwenden möchten, ist eine lokale lync Server Bereitstellung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03774-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="03774-115">Eine lokale Bereitstellung unterstützt die direkte Konnektivität mit den Nebenstellenanlagen und Trunks sowie erweiterte Telefonfunktionen, wie Reaktionsgruppen und das Parken von Anrufen.</span><span class="sxs-lookup"><span data-stu-id="03774-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="03774-116">Diese Features werden von lync Online derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="03774-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="03774-117">**Steuerelemente**   für die Medienqualität Wenn Sie die gesamte Palette an Features für die Medien Qualitätssicherungs Funktionen wie Anrufsteuerung (Call Admission Control, CAC) und QoS (Quality of Service) nutzen möchten, benötigen Sie eine lokale Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03774-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="03774-118">**Beständiger Chat**   Wenn Sie beständigen Chat für Ihre Organisation bereitstellen müssen, müssen Sie eine lokale Bereitstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="03774-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="03774-119">**Drittanbieter-Server Anwendungen**   nur lokale Bereitstellungen können mit vertrauenswürdigen Drittanbieteranwendungen verwendet werden, die das verwaltete API von Microsoft Unified Communications (UCMA) verwenden.</span><span class="sxs-lookup"><span data-stu-id="03774-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="03774-120">**Multi-nationale/multiregionale Unternehmen, die regionale Unterstützung**   benötigen wenn Sie über Rechenzentren in mehreren Ländern oder Regionen verfügen und Server auf regionaler Basis bereitgestellt und verwaltet werden müssen, ist eine lokale Bereitstellung am besten, da Sie diese Art von regionalen Verwaltungsfunktionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="03774-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="03774-121">**Vollständige Kontrolle über Richtlinien, Berichte und Upgrades**   mit einer lokalen lync Server-Bereitstellung haben Sie Zugriff auf den vollständigen Server-und Clientrichtlinien, Überwachung und andere Berichte sowie Timing von Upgrades.</span><span class="sxs-lookup"><span data-stu-id="03774-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="03774-122">Lync Online stellt eine Teilmenge von Richtlinieneinstellungen und-Berichten bereit und bietet ein eingeschränktes, wenn auch erhebliches Fenster für das akzeptieren von Upgrades.</span><span class="sxs-lookup"><span data-stu-id="03774-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="03774-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="03774-123">Lync Online</span></span>

<span data-ttu-id="03774-124">Falls keiner der in der Liste aufgeführten Faktoren für Sie von entscheidender Bedeutung ist, sollten Sie sich für Lync Online entscheiden, das einfacher bereitzustellen und zu verwalten ist.</span><span class="sxs-lookup"><span data-stu-id="03774-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="03774-125">Lync Online bietet eine robuste Funktion für Sofortnachrichten, Anwesenheit und Konferenzen sowie Sprach-und Videoanrufe über IP zwischen Benutzern in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="03774-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

