---
title: 'Lync Server 2013: Remoteanrufsteuerung und Normalisieren von Rufnummern'
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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="3d341-102">Remoteanrufsteuerung und Normalisieren von Rufnummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d341-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d341-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="3d341-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="3d341-104">Lync-Clients laden Telefonnummern Normalisierungsregeln als Teil des Adressbuchdienst-Dateidownloads (ABS) herunter.</span><span class="sxs-lookup"><span data-stu-id="3d341-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="3d341-105">In Szenarien für die Remoteanrufsteuerung werden die Normalisierungsregeln für den Adressbuchdienst für eingehende und ausgehende Anrufe in der Remoteanrufsteuerung angewendet.</span><span class="sxs-lookup"><span data-stu-id="3d341-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="3d341-106">Für eingehende Anrufe an einen Benutzer mit Remoteanrufsteuerung wird die Telefonnummer des Anrufers zuerst vom SIP/CSTA-Gateway oder von der PBX (Private Branch Exchange) auf das E. 164-Format normiert.</span><span class="sxs-lookup"><span data-stu-id="3d341-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="3d341-107">Wenn lync Server 2013 den Anruf vom Gateway empfängt, führt er Reverse Number Lookup (RNL) für die Telefonnummer des Anrufers anhand der normalisierten Nummer in der Microsoft Office Outlook-Kontaktliste des berufenen oder in der globalen Adressliste (GAL) durch, die in gespeichert ist. der Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="3d341-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="3d341-108">Wenn die Suche nach einer umgekehrten Zahl erfolgreich gefunden wird, wird der Anrufer in der Benachrichtigung über den eingehenden Anruf durch den Namen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3d341-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="3d341-109">Bei ausgehenden Remote Anruf Steuerungs anrufen wendet lync die Normalisierungsregeln für den Adressbuchdienst auf die gewählte Nummer an, bevor der Anruf an das SIP/CSTA-Gateway weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3d341-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="3d341-110">Details zum Erstellen von Regeln für die Normalisierung der Telefonnummern für die Remoteanrufsteuerung finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3d341-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="3d341-111">Migrieren von Normalisierungsregeln für Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="3d341-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="3d341-112">Wenn Sie Benutzer migrieren, die zuvor für die Remoteanrufsteuerung aktiviert wurden, lesen Sie die folgenden Themen in der Migrationsdokumentation:</span><span class="sxs-lookup"><span data-stu-id="3d341-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="3d341-113">Informationen zu lync Server 2010 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3d341-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="3d341-114">Informationen zu Communications Server 2007 R2 finden Sie unter [Migrieren des Adressbuchs](migrate-address-book_1.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3d341-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

