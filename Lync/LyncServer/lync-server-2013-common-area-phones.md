---
title: 'Lync Server 2013: Telefone für gemeinsame Bereiche'
description: 'Lync Server 2013: Telefone für gemeinsame Bereiche.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8a68f875bba1d43a91e5a252259841d7a6bbda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577031"
---
# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="08499-103">Telefone in öffentlichen Bereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08499-103">Common area phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08499-104">_**Letztes Änderungsstand des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="08499-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="08499-105">Telefone in öffentlichen Bereichen sind IP-Telefone, die keinem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="08499-105">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="08499-106">Anstatt sich im Büro eines anderen zu befinden, befinden sich Telefone in öffentlichen Bereichen in der Regel in Gebäude Lobbys, Cafeterias, Mitarbeiter-Lounges, Besprechungsräumen und an anderen Standorten, an denen sich eine große Anzahl von Personen wahrscheinlich versammeln wird.</span><span class="sxs-lookup"><span data-stu-id="08499-106">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="08499-107">Im Gegensatz zu anderen Telefonen in lync Server, die in der Regel mithilfe von VoIP-Richtlinien und Wählplänen verwaltet werden, die einzelnen Benutzern zugewiesen sind, haben für Telefone in öffentlichen Bereichen keine einzelnen Benutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="08499-107">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="08499-108">Dies bedeutet, dass Sie anders verwaltet werden müssen als Ihre anderen Telefone.</span><span class="sxs-lookup"><span data-stu-id="08499-108">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="08499-109">Zum Verwalten von Telefonen in öffentlichen Bereichen erstellen Sie Active Directory-Domänendienste Kontaktobjekte für alle Telefone in öffentlichen Bereichen, die wie Benutzerkonten Richtlinien und VoIP-Pläne zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="08499-109">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="08499-110">Mit diesem Ansatz können Sie die Kontrolle über Telefone in öffentlichen Bereichen aufrecht erhalten, auch wenn diese Telefone keinem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="08499-110">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="08499-111">Verwenden Sie die Themen in diesem Abschnitt, um zu erfahren, wie Sie Kontaktobjekte für Telefone in öffentlichen Bereichen erstellen, diese ändern und löschen sowie Konfigurationsinformationen zu den Telefonen für gemeinsame Bereiche in Ihrer Bereitstellung konfigurieren und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="08499-111">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08499-112">Sie haben drei Optionen für Telefone in öffentlichen Bereichen: das Aastra 6721ip-Telefon im öffentlichen Bereich, das HP 4110-IP-Telefon und das Polycom-IP-Telefon im öffentlichen Bereich von Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="08499-112">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="08499-113">Das Polycom CX3000-IP-Konferenztelefon ist eine weitere Variante des Telefonapparats für gemeinsame Bereiche.</span><span class="sxs-lookup"><span data-stu-id="08499-113">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="08499-114">Sie ist jedoch für die Verwendung in Konferenzräumen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="08499-114">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="08499-115">Ausführliche Informationen zu Telefonen in öffentlichen Bereichen finden Sie im Abschnitt Telefone für gemeinsame Bereiche unter <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Auswählen neuer Geräte</A>.</span><span class="sxs-lookup"><span data-stu-id="08499-115">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08499-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="08499-116">In This Section</span></span>

  - [<span data-ttu-id="08499-117">Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08499-117">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="08499-118">Erstellen oder Ändern eines Kontaktobjekts für ein Telefon mit öffentlichen Bereichen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08499-118">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="08499-119">Aktivieren oder Deaktivieren des Hot deskings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08499-119">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="08499-120">Löschen eines Kontaktobjekts für einen öffentlichen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08499-120">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="08499-121">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="08499-121">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

