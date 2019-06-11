---
title: 'Lync Server 2013: Telefone im öffentlichen Bereich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179d6a0102e62a081846a14981ed70294432ed44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="f99fb-102">Telefone im öffentlichen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99fb-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f99fb-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f99fb-104">Telefone im öffentlichen Bereich sind IP-Telefone, die keinem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f99fb-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="f99fb-105">Statt sich im Büro einer anderen Person zu befinden, befinden sich die Telefone im öffentlichen Bereich in der Regel in Gebäude-Lobbies, Cafeterias, Mitarbeiter-Lounges, Besprechungsräumen und anderen Orten, an denen sich eine große Anzahl von Personen wahrscheinlich versammeln wird.</span><span class="sxs-lookup"><span data-stu-id="f99fb-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="f99fb-106">Im Gegensatz zu anderen Telefonen in lync Server, die in der Regel mithilfe von VoIP-Richtlinien und Wählplänen verwaltet werden, die einzelnen Benutzern zugewiesen sind, sind für Telefone im öffentlichen Bereich keine einzelnen Benutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f99fb-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="f99fb-107">Das bedeutet, dass Sie anders als Ihre anderen Telefone verwaltet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f99fb-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="f99fb-108">Zum Verwalten von Telefonen im allgemeinen Bereich erstellen Sie für alle Ihre Telefone im öffentlichen Bereich Active Directory-Domänendienste, denen wie Benutzerkonten Richtlinien und sprach Pläne zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="f99fb-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="f99fb-109">Dieser Ansatz ermöglicht Ihnen, die Kontrolle über Telefone im öffentlichen Bereich zu behalten, auch wenn diese Telefone keinem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f99fb-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="f99fb-110">Verwenden Sie die Themen in diesem Abschnitt, um zu erfahren, wie Sie Kontaktobjekte für Telefone im allgemeinen Bereich erstellen, diese ändern und löschen sowie Konfigurationsinformationen zu den Telefonen im öffentlichen Bereich in Ihrer Bereitstellung konfigurieren und anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="f99fb-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f99fb-111">Sie haben drei Optionen für Telefone im öffentlichen Bereich: das allgemeine Bereichs Telefon Aastra 6721ip, das HP 4110 IP-Telefon und das Polycom CX500 IP-Telefon mit gemeinsamem Bereich.</span><span class="sxs-lookup"><span data-stu-id="f99fb-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="f99fb-112">Das Polycom CX3000 IP-Konferenztelefon ist ein weiteres Variant-Telefon im öffentlichen Bereich.</span><span class="sxs-lookup"><span data-stu-id="f99fb-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="f99fb-113">Sie ist jedoch für die Verwendung in Konferenzräumen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f99fb-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="f99fb-114">Ausführliche Informationen zu Telefonen im öffentlichen Bereich finden Sie im Abschnitt Telefone im allgemeinen Bereich unter <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Auswählen neuer Geräte</A>.</span><span class="sxs-lookup"><span data-stu-id="f99fb-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f99fb-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f99fb-115">In This Section</span></span>

  - [<span data-ttu-id="f99fb-116">Anzeigen von allgemeinen Telefon Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="f99fb-117">Erstellen oder Ändern eines Telefon Kontaktobjekts in einem gemeinsamen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="f99fb-118">Aktivieren oder Deaktivieren von Hot Desking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="f99fb-119">Löschen eines Kontaktobjekts für einen öffentlichen Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99fb-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="f99fb-120">Zuweisen von Richtlinien in lync Server 2013 zu einem Telefon im öffentlichen Bereich</span><span class="sxs-lookup"><span data-stu-id="f99fb-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

