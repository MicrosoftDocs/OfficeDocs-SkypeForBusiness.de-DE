---
title: 'Lync Server 2013: Konfigurieren von Zugriffsnummern für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83c7069db95d36e79d74cea81faf3aa98685832f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504772"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="ef33f-102">Konfigurieren von Zugriffsnummern für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef33f-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef33f-103">_**Letztes Änderungsstand des Themas:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="ef33f-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="ef33f-p101">Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef33f-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="ef33f-106">Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef33f-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="ef33f-107">Ausführliche Informationen zu Regionen finden Sie unter [Einwahlkonferenz Anforderungen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ef33f-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="ef33f-108">Ausführliche Informationen zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="ef33f-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef33f-109">Sie können keine neue Zugriffsnummer für die Einwahl verwenden, bis Active Directory-Domänendienste (AD &nbsp; DS)-Replikation dieser Zugriffsnummer abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ef33f-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="ef33f-110">Die Replikation kann mehrere Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ef33f-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ef33f-111">Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="ef33f-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="ef33f-112">Verwenden Sie das Cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>, um den Anzeigenamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ef33f-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="ef33f-113">Active Directory-Objekte sollten nicht manuell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef33f-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="ef33f-114">Ausführliche Informationen zum Ändern einer Zugriffsnummer finden Sie in lync Server-Verwaltungsshell Dokumentation für das Cmdlet " <STRONG>setCsDialInConferencingAccessNumber</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="ef33f-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef33f-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ef33f-115">In This Section</span></span>

[<span data-ttu-id="ef33f-116">Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef33f-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef33f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef33f-117">See Also</span></span>


[<span data-ttu-id="ef33f-118">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef33f-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="ef33f-119">Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef33f-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

