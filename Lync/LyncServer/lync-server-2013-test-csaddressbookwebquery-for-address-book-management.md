---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4112f34eb35bcf45991e6744327487afe9a2a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519242"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="7c349-102">Test-CsAddressBookWebQuery für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c349-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c349-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7c349-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7c349-p101">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Test-CsAddressBookWebQuery" ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="7c349-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="7c349-p102">Ähnlich wie die synthetische Transaktion "Test-CsAddressBookService" führt "Test-CsAddressBookWebQuery" eine Abfrage beim Adressbuch-Webabfragedienst durch, um sicherzustellen, dass dieser ordnungsgemäß ausgeführt wird. Das Cmdlet stellt eine Verbindung mit dem Webticketdienst zur Authentifizierung her und legt die in "–UserCredential" angegebenen Anmeldeinformationen vor. Nach der Authentifizierung übergibt das Cmdlet die Informationen in "–TargetSipAddress". Das Cmdlet sollte eine erfolgreiche Ausführung melden, wenn die Informationen zum Kontakt abgerufen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="7c349-p102">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly. The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential. If authenticated, the cmdlet then present the –TargetSipAddress information. The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="7c349-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7c349-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="7c349-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c349-111">See Also</span></span>


[<span data-ttu-id="7c349-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="7c349-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

