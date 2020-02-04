---
title: 'Lync Server 2013: Planen der Darstellung der freigegebenen Zeile'
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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="c135f-102">Planen der Darstellung der freigegebenen Zeile in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c135f-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c135f-103">_**Letztes Änderungsdatum des Themas:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="c135f-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="c135f-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie in lync Server 2013, Kumulatives Update April 2016, die Darstellung der freigegebenen Leitung planen.</span><span class="sxs-lookup"><span data-stu-id="c135f-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c135f-105">Die Darstellung der freigegebenen Zeile ist ein Feature in lync Server 2013, Kumulatives Update April 2016 für die Behandlung mehrerer Anrufe an eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c135f-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="c135f-106">SLA kann alle Enterprise-VoIP-aktivierten lync-Benutzer als freigegebene Nummer mit mehreren Zeilen konfigurieren, um auf mehrere Anrufe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="c135f-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="c135f-107">Die Anrufe werden für die freigegebene Nummer nicht tatsächlich empfangen, sondern an Benutzer weitergeleitet, die als Stellvertretungen für die freigegebene Nummer fungieren.</span><span class="sxs-lookup"><span data-stu-id="c135f-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="c135f-108">Jeder Delegierte kann den Anruf annehmen, während die restlichen Teilnehmer eine Benachrichtigung auf dem Telefon erhalten, wer den Anruf aufgenommen hat und welche Zeile damit ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="c135f-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="c135f-109">Die Anzahl der Zeilen und die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c135f-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="c135f-110">Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation geschieht, wenn alle Zeilen ausgelastet sind) und MissedCallOption (der Fall, in dem keiner der Stellvertretungen einen Anruf annimmt) auch für eine freigegebene Nummer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c135f-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="c135f-111">SLA wird nur auf den folgenden Telefongeräten unterstützt (es wird für lync-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt):</span><span class="sxs-lookup"><span data-stu-id="c135f-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="c135f-112">Polycom VVX300 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c135f-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c135f-113">Polycom VVX400 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c135f-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c135f-114">Polycom VVX500 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c135f-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="c135f-115">Polycom VVX600 mit Firmwareupdate 5.4.1</span><span class="sxs-lookup"><span data-stu-id="c135f-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="c135f-116">SLA ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.</span><span class="sxs-lookup"><span data-stu-id="c135f-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="c135f-117">Informationen zum Bereitstellen von SLA finden Sie unter [Bereitstellen der freigegebenen Leitungsdarstellung in lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="c135f-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="c135f-118">Liste der Funktionen</span><span class="sxs-lookup"><span data-stu-id="c135f-118">Feature List</span></span>

<span data-ttu-id="c135f-119">Das Einrichten einer SLA-Gruppe macht Folgendes möglich:</span><span class="sxs-lookup"><span data-stu-id="c135f-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="c135f-p102">Alle Stellvertretungen in der Gruppe können eingehende Anrufe für dieselbe gemeinsam genutzte Nummer annehmen. Diese Anrufe können Festnetz- oder SIP-Anrufe sein.</span><span class="sxs-lookup"><span data-stu-id="c135f-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="c135f-122">Stellvertretungen können Anrufe halten und annehmen.</span><span class="sxs-lookup"><span data-stu-id="c135f-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="c135f-123">Stellvertretungen können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="c135f-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="c135f-124">Stellvertretungen bekommen angezeigt, wie viele Anrufe es aktuell für die gemeinsam genutzte Nummer gibt, und sie können den Status jedes einzelnen Anrufs einsehen.</span><span class="sxs-lookup"><span data-stu-id="c135f-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="c135f-p103">Sie können eine maximale Anzahl gleichzeitiger Anrufe für die gemeinsam genutzte Nummer konfigurieren. Sie können auch einstellen, wie zusätzliche Anrufe behandelt werden sollen, wenn die maximale Anzahl erreicht worden ist. Zusätzliche Anrufe können mit einem Besetztzeichen abgewiesen, an eine alternative Nummer oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c135f-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="c135f-p104">Sie können konfigurieren, wie entgangene Anrufe (solche, die nach einer festgelegten Zeit nicht angenommen worden sind) behandelt werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen entgangene Anrufe automatisch an die Voicemail. Wenn Voicemail für die Gruppenidentität (gemeinsam genutzte Nummer) nicht aktiviert ist, können Sie wählen, ob entgangene Anrufe mit einem Besetztzeichen abgewiesen, an eine alternative Nummer weitergeleitet oder getrennt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c135f-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

