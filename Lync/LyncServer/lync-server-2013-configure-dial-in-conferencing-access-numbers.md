---
title: 'Lync Server 2013: Konfigurieren von Einwahlnummern für Einwahlkonferenzen'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="21e2c-102">Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21e2c-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21e2c-103">_**Letztes Änderungsdatum des Themas:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="21e2c-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="21e2c-104">Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="21e2c-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="21e2c-105">Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21e2c-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="21e2c-106">Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="21e2c-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="21e2c-107">Details zu Regionen finden Sie unter [Anforderungen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="21e2c-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="21e2c-108">Details zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="21e2c-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21e2c-109">Sie können erst dann eine neue Einwahl Zugriffsnummer verwenden, wenn die Active Directory-&nbsp;Domänendienste (AD DS)-Replikation dieser Zugriffsnummer abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="21e2c-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="21e2c-110">Die Replikation kann mehrere Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="21e2c-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="21e2c-111">Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="21e2c-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="21e2c-112">Verwenden Sie das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ", um den Anzeigenamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="21e2c-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="21e2c-113">Active Directory-Objekte sollten nicht manuell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="21e2c-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="21e2c-114">Details zum Ändern einer Zugriffsnummer finden Sie unter Dokumentation zur lync Server-Verwaltungsshell für das Cmdlet " <STRONG>Satz-CsDialInConferencingAccessNumber</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="21e2c-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21e2c-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="21e2c-115">In This Section</span></span>

[<span data-ttu-id="21e2c-116">Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21e2c-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21e2c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21e2c-117">See Also</span></span>


[<span data-ttu-id="21e2c-118">Anforderungen für Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21e2c-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="21e2c-119">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21e2c-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

