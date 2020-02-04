---
title: 'Lync Server 2013: Get-CsWebServiceConfiguration für die Verwaltung von Adressbüchern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c04cc523e27d655aa69b05f522efccf8153a37ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="7b96f-102">Get-CsWebServiceConfiguration für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b96f-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b96f-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7b96f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7b96f-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsWebServiceConfiguration" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7b96f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="7b96f-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="7b96f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="7b96f-106">Get-CsWebServiceConfiguration gibt Informationen zu der Webdienstkonfiguration zurück, die derzeit in Ihrer Organisation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b96f-106">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization.</span></span> <span data-ttu-id="7b96f-107">Von Interesse für die Adressbuchdienste ist der Status der Erweiterungsfunktion Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="7b96f-107">Of interest to the Address Book Services is the status of Distribution List Expansion function.</span></span> <span data-ttu-id="7b96f-108">Wenn das Attribut EnableGroupExpansion wahr ist, ermöglicht Ihre Organisation derzeit die Gruppenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="7b96f-108">If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="7b96f-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7b96f-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="7b96f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b96f-110">See Also</span></span>


[<span data-ttu-id="7b96f-111">Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b96f-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

