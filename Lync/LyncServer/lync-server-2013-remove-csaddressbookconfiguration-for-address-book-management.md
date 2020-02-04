---
title: Remove-CsAddressBookConfiguration für Adressbuchverwaltung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de016366fe888a159a449f7840a0f6dca03c7075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ea55c-102">Remove-CsAddressBookConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea55c-102">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea55c-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ea55c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ea55c-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Remove-CsAddressBookConfiguration" lokal auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ea55c-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="ea55c-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="ea55c-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="ea55c-106">Wie der Name schon sagt, entfernt Remove-CsAddressBookConfiguration die Konfiguration basierend auf der definierten Websiteidentität.</span><span class="sxs-lookup"><span data-stu-id="ea55c-106">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="ea55c-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea55c-107">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="ea55c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea55c-108">See Also</span></span>


<span data-ttu-id="ea55c-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ea55c-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

