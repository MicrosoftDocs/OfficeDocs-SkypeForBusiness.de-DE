---
title: 'Lync Server 2013: Set-CsAddressBookConfiguration für die Adressbuchverwaltung'
description: 'Lync Server 2013: Set-CsAddressBookConfiguration für die Adressbuchverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsAddressBookConfiguration for Address Book management
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429700(v=OCS.15)
ms:contentKeyID: 48183913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab7a58510b2bb6232d9908c77cf6b70bbeb927f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560891"
---
# <a name="set-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="fd8e8-103">Set-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd8e8-103">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd8e8-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fd8e8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fd8e8-p101">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Set-CsAddressBookConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="fd8e8-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

<span data-ttu-id="fd8e8-107">"Set-CsAddressBookConfiguration" ähnelt dem Cmdlet "New-CsAddressBookConfiguration", wird jedoch zum Ändern einer vorhandenen Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd8e8-107">Set-CsAddressBookConfiguration is similar to the New-CsAddressBookConfiguration cmdlet, except it is used to modify an existing configuration.</span></span>

<span data-ttu-id="fd8e8-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fd8e8-108">For example:</span></span>

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

<div>

## <a name="see-also"></a><span data-ttu-id="fd8e8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd8e8-109">See Also</span></span>


[<span data-ttu-id="fd8e8-110">Gruppe-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd8e8-110">Set-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

