---
title: 'Lync Server 2013: Planen der Darstellung freigegebener Leitungen'
description: 'Lync Server 2013: Planen der Darstellung freigegebener Leitungen.'
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
ms.openlocfilehash: 09c34a4792d6df9b37b138c08881699dfcdf684d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554381"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="d722f-103">Planen der Darstellung freigegebener Leitungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d722f-103">Plan for Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d722f-104">_**Letztes Änderungsstand des Themas:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="d722f-104">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="d722f-105">Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in lync Server 2013, Kumulatives Update April 2016, planen.</span><span class="sxs-lookup"><span data-stu-id="d722f-105">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="d722f-106">Die Darstellung freigegebener Leitungen ist ein Feature in lync Server 2013, Kumulatives Update April 2016 für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="d722f-106">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="d722f-107">Mit SLA können alle Enterprise-VoIP-aktivierten lync-Benutzer als freigegebene Nummer mit mehreren Zeilen konfiguriert werden, um auf mehrere Anrufe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="d722f-107">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="d722f-108">Die Anrufe werden nicht tatsächlich auf der freigegebenen Nummer empfangen, sondern werden an Benutzer weitergeleitet, die als Stellvertreter für die freigegebene Nummer fungieren.</span><span class="sxs-lookup"><span data-stu-id="d722f-108">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="d722f-109">Jeder der Stellvertretungen kann den Anruf annehmen, während der Rest der Stellvertreter eine Benachrichtigung auf seinem Telefon erhält, wer den Anruf abgeholt hat und welche Leitung damit beschäftigt geworden ist.</span><span class="sxs-lookup"><span data-stu-id="d722f-109">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="d722f-110">Sowohl die Anzahl der Zeilen als auch die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d722f-110">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="d722f-111">Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation passiert, wenn alle Zeilen beschäftigt sind) und MissedCallOption (der Fall, in dem keine der Stellvertreter einen Anruf abruft) auch für eine freigegebene Nummer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d722f-111">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="d722f-112">SLA wird nur auf den folgenden Telefongeräten unterstützt (wird für lync-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt):</span><span class="sxs-lookup"><span data-stu-id="d722f-112">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="d722f-113">Polycom VVX300 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="d722f-113">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="d722f-114">Polycom VVX400 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="d722f-114">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="d722f-115">Polycom VVX500 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="d722f-115">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="d722f-116">Polycom VVX600 mit Firmware-Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="d722f-116">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="d722f-117">SLA ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.</span><span class="sxs-lookup"><span data-stu-id="d722f-117">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="d722f-118">Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Online Appearance in lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="d722f-118">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="d722f-119">Funktionsliste</span><span class="sxs-lookup"><span data-stu-id="d722f-119">Feature List</span></span>

<span data-ttu-id="d722f-120">Das Einrichten einer SLA-Gruppe ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d722f-120">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="d722f-121">Alle Stellvertretungen in der Gruppe können eingehende Anrufe an dieselbe freigegebene Nummer beantworten.</span><span class="sxs-lookup"><span data-stu-id="d722f-121">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="d722f-122">Die Anrufe können PSTN-basiert oder auf SIP-Basis erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d722f-122">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="d722f-123">Stellvertretungen können Anrufe abhalten und annehmen.</span><span class="sxs-lookup"><span data-stu-id="d722f-123">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="d722f-124">Delegaten können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="d722f-124">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="d722f-125">Stellvertretungen können sehen, wie viele Anrufe derzeit für die freigegebene Nummer verwendet werden, und den Status jedes dieser Anrufe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d722f-125">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="d722f-126">Sie können eine maximale Anzahl gleichzeitiger Anrufe für die freigegebene Nummer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d722f-126">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="d722f-127">Sie können auch festlegen, wie zusätzliche Anrufe verarbeitet werden sollen, nachdem dieser Höchstwert erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d722f-127">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="d722f-128">Überschüssige Anrufe können mit einem Besetztzeichen zurückgewiesen, an eine Alternative Nummer weitergeleitet oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d722f-128">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="d722f-129">Sie können konfigurieren, wie verpasste Anrufe (Anrufe, die nach einer bestimmten Zeit nicht aufgenommen wurden) verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d722f-129">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="d722f-130">Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen verpasste Anrufe automatisch zu Voicemail.</span><span class="sxs-lookup"><span data-stu-id="d722f-130">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="d722f-131">Wenn für die Gruppenidentität (freigegebene Nummer) keine Voicemail aktiviert ist, können Sie auswählen, dass verpasste Anrufe mit einem Besetztzeichen abgelehnt, an eine Alternative Nummer weitergeleitet oder getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="d722f-131">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

