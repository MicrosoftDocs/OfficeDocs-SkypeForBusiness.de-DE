---
title: 'Lync Server 2013: Set-CsClientPolicy für die Adressbuchverwaltung'
description: 'Lync Server 2013: Set-CsClientPolicy für die Adressbuchverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsClientPolicy for Address Book management
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429723(v=OCS.15)
ms:contentKeyID: 48185726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10cbf6cb23315715ddb71680f3725808a55ad4a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543291"
---
# <a name="set-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3b572-103">Set-CsClientPolicy für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b572-103">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b572-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b572-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3b572-105">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet Set-CsClientPolicy lokal ausführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3b572-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsClientPolicy cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3b572-106">Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten RBAC (Role-based Access Control)-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, (einschließlich aller von Ihnen erstellen benutzerdefinierten RBAC-Rollen):</span><span class="sxs-lookup"><span data-stu-id="3b572-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

<span data-ttu-id="3b572-107">Ähnlich wie bei New-CsClientPolicy können Sie mit dem Set-CsClientPolicy-Cmdlet Clienteinstellungen ändern, die bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3b572-107">Similar to New-CsClientPolicy, the Set-CsClientPolicy cmdlet allows you to modify client settings that are already in place.</span></span>

<span data-ttu-id="3b572-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b572-108">For example:</span></span>

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

<div>

## <a name="see-also"></a><span data-ttu-id="3b572-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b572-109">See Also</span></span>


[<span data-ttu-id="3b572-110">Gruppe-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3b572-110">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

