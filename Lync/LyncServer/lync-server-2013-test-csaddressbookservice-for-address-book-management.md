---
title: 'Lync Server 2013: Test-CsAddressBookService für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a3b0f-102">Test-CsAddressBookService für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3b0f-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3b0f-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a3b0f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a3b0f-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen zum Ausführen des Test-CsAddressBookService-Cmdlets autorisiert: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a3b0f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a3b0f-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="a3b0f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="a3b0f-106">Lync Server 2013 enthält eine Reihe von Cmdlets, die synthetische Befehle initiieren, um zu bestätigen, dass eine bestimmte Funktion oder ein bestimmtes Feature ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3b0f-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="a3b0f-107">Test-CsAddressBookService bestätigt, dass ein definierter Benutzer eine Verbindung herstellen und die lokalen Dateien über den Adressbuch-Webdienst anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="a3b0f-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="a3b0f-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3b0f-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="a3b0f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3b0f-109">See Also</span></span>


[<span data-ttu-id="a3b0f-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="a3b0f-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

