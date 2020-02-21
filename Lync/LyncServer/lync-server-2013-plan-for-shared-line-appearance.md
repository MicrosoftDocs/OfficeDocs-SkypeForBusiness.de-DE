---
title: 'Lync Server 2013: Planen der Darstellung freigegebener Leitungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="2e03b-102">Planen der Darstellung freigegebener Leitungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e03b-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e03b-103">_**Letztes Änderungsstand des Themas:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="2e03b-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="2e03b-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in lync Server 2013, Kumulatives Update April 2016, planen.</span><span class="sxs-lookup"><span data-stu-id="2e03b-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="2e03b-105">Die Darstellung freigegebener Leitungen ist ein Feature in lync Server 2013, Kumulatives Update April 2016 für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2e03b-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="2e03b-106">Mit SLA können alle Enterprise-VoIP-aktivierten lync-Benutzer als freigegebene Nummer mit mehreren Zeilen konfiguriert werden, um auf mehrere Anrufe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="2e03b-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="2e03b-107">Die Anrufe werden nicht tatsächlich auf der freigegebenen Nummer empfangen, sondern werden an Benutzer weitergeleitet, die als Stellvertreter für die freigegebene Nummer fungieren.</span><span class="sxs-lookup"><span data-stu-id="2e03b-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="2e03b-108">Jeder der Stellvertretungen kann den Anruf annehmen, während der Rest der Stellvertreter eine Benachrichtigung auf seinem Telefon erhält, wer den Anruf abgeholt hat und welche Leitung damit beschäftigt geworden ist.</span><span class="sxs-lookup"><span data-stu-id="2e03b-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="2e03b-109">Sowohl die Anzahl der Zeilen als auch die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2e03b-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="2e03b-110">Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation passiert, wenn alle Zeilen beschäftigt sind) und MissedCallOption (der Fall, in dem keine der Stellvertreter einen Anruf abruft) auch für eine freigegebene Nummer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2e03b-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="2e03b-111">SLA wird nur auf den folgenden Telefongeräten unterstützt (wird für lync-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt):</span><span class="sxs-lookup"><span data-stu-id="2e03b-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="2e03b-112">Polycom VVX300 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e03b-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="2e03b-113">Polycom VVX400 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e03b-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="2e03b-114">Polycom VVX500 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e03b-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="2e03b-115">Polycom VVX600 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e03b-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="2e03b-116">SLA ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.</span><span class="sxs-lookup"><span data-stu-id="2e03b-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="2e03b-117">Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Online Appearance in lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="2e03b-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="2e03b-118">Funktionsliste</span><span class="sxs-lookup"><span data-stu-id="2e03b-118">Feature List</span></span>

<span data-ttu-id="2e03b-119">Das Einrichten einer SLA-Gruppe ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2e03b-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="2e03b-120">Alle Stellvertretungen in der Gruppe können eingehende Anrufe an dieselbe freigegebene Nummer beantworten.</span><span class="sxs-lookup"><span data-stu-id="2e03b-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="2e03b-121">Die Anrufe können PSTN-basiert oder auf SIP-Basis erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2e03b-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="2e03b-122">Stellvertretungen können Anrufe abhalten und annehmen.</span><span class="sxs-lookup"><span data-stu-id="2e03b-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="2e03b-123">Delegaten können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="2e03b-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="2e03b-124">Stellvertretungen können sehen, wie viele Anrufe derzeit für die freigegebene Nummer verwendet werden, und den Status jedes dieser Anrufe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e03b-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="2e03b-125">Sie können eine maximale Anzahl gleichzeitiger Anrufe für die freigegebene Nummer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2e03b-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="2e03b-126">Sie können auch festlegen, wie zusätzliche Anrufe verarbeitet werden sollen, nachdem dieser Höchstwert erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="2e03b-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="2e03b-127">Überschüssige Anrufe können mit einem Besetztzeichen zurückgewiesen, an eine Alternative Nummer weitergeleitet oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2e03b-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="2e03b-128">Sie können konfigurieren, wie verpasste Anrufe (Anrufe, die nach einer bestimmten Zeit nicht aufgenommen wurden) verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e03b-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="2e03b-129">Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen verpasste Anrufe automatisch zu Voicemail.</span><span class="sxs-lookup"><span data-stu-id="2e03b-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="2e03b-130">Wenn für die Gruppenidentität (freigegebene Nummer) keine Voicemail aktiviert ist, können Sie auswählen, dass verpasste Anrufe mit einem Besetztzeichen abgelehnt, an eine Alternative Nummer weitergeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="2e03b-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

