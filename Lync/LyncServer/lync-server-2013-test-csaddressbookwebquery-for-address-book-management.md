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
ms.openlocfilehash: c50497979e8439a60799864376d1f93d36646cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="73b4c-102">Test-CsAddressBookWebQuery für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b4c-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b4c-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="73b4c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73b4c-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen zum Ausführen des Test-CsAddressBookWebQuery-Cmdlets autorisiert: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="73b4c-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="73b4c-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="73b4c-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="73b4c-106">Ähnlich wie bei der synthetischen Test-CsAddressBookService-Transaktion führt Test-CsAddressBookWebQuery eine Abfrage für die Adressbuch-Webabfrage aus, um sicherzustellen, dass Sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="73b4c-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="73b4c-107">Das Cmdlet stellt eine Verbindung mit der Web Ticket-Authentifizierung her und stellt die in – UserCredential angegebenen Anmeldeinformationen dar.</span><span class="sxs-lookup"><span data-stu-id="73b4c-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="73b4c-108">Wenn authentifiziert, gibt das Cmdlet dann die – TargetSipAddress-Informationen an.</span><span class="sxs-lookup"><span data-stu-id="73b4c-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="73b4c-109">Das Cmdlet sollte Erfolg melden, wenn es die Informationen über den Kontakt abrufen konnte.</span><span class="sxs-lookup"><span data-stu-id="73b4c-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="73b4c-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73b4c-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="73b4c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73b4c-111">See Also</span></span>


[<span data-ttu-id="73b4c-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="73b4c-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

