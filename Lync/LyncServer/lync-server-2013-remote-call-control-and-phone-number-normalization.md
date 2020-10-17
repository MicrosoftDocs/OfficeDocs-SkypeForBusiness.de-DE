---
title: 'Lync Server 2013: Remote Anrufsteuerung und Telefonnummernnormalisierung'
description: 'Lync Server 2013: Remote Anrufsteuerung und Telefonnummernnormalisierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555811"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="2aa58-103">Remote Anrufsteuerung und Telefonnummernnormalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa58-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa58-104">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="2aa58-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="2aa58-105">Lync-Clients laden die Normalisierungsregeln für Telefonnummern als Teil des Adressbuchdienst-Dateidownloads (Address Book Service, ABS) herunter.</span><span class="sxs-lookup"><span data-stu-id="2aa58-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="2aa58-106">In Szenarien mit Remoteanrufsteuerung werden die vom Adressbuchdienst verwendeten Normalisierungsregeln für Rufnummern sowohl auf eingehende als auch auf ausgehende Anrufe mit Remoteanrufsteuerung angewendet.</span><span class="sxs-lookup"><span data-stu-id="2aa58-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="2aa58-107">Für eingehende Anrufe bei einem Benutzer, der für die Remoteanrufsteuerung aktiviert ist, wird die Rufnummer des Anrufers zunächst über das SIP/CSTA-Gateway oder eine Nebenstellenanlage (Private Branch Exchange, PBX) in das E.164-Format normalisiert.</span><span class="sxs-lookup"><span data-stu-id="2aa58-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="2aa58-108">Wenn lync Server 2013 den Anruf vom Gateway erhält, führt er Reverse Number Lookup (können) für die Telefonnummer des Anrufers anhand der normalisierten Nummer in der Microsoft Office Outlook-Kontaktliste des angerufenen oder in der globalen Adressliste (GAL) durch, die im Adressbuchdienst gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2aa58-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="2aa58-109">Wenn die umgekehrte Nummernsuche zu einem Treffer führt, wird der Anrufer in der Benachrichtigung über einen eingehenden Anruf mit seinem Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2aa58-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="2aa58-110">Für ausgehende Anrufe mit Remoteanrufsteuerung wendet lync die Normalisierungsregeln für den Adressbuchdienst auf die gewählte Nummer an, bevor der Anruf an das SIP/CSTA-Gateway weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2aa58-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="2aa58-111">Ausführliche Informationen zum Erstellen von Normalisierungsregeln für Telefonnummern für die Remoteanrufsteuerung finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2aa58-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="2aa58-112">Migrieren von Normalisierungsregeln für Rufnummern</span><span class="sxs-lookup"><span data-stu-id="2aa58-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="2aa58-113">Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert waren, finden Sie weitere Informationen in den folgenden Themen der Migrationsdokumentation:</span><span class="sxs-lookup"><span data-stu-id="2aa58-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="2aa58-114">Informationen zu lync Server 2010 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2aa58-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="2aa58-115">Informationen zu Communications Server 2007 R2 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2aa58-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

