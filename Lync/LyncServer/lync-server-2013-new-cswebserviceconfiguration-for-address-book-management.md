---
title: 'Lync Server 2013: New-CsWebServiceConfiguration für Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e00af-102">New-CsWebServiceConfiguration für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00af-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e00af-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e00af-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e00af-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet New-CsWebServiceConfiguration lokal auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e00af-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="e00af-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="e00af-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="e00af-106">Das Cmdlet New-CsWebServiceConfiguration definiert eine neue Konfiguration für Webdienste in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e00af-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="e00af-107">Der Bereich für die Webdienstkonfiguration kann sich nur auf der Website oder auf der Dienstebene befinden.</span><span class="sxs-lookup"><span data-stu-id="e00af-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="e00af-108">Auf globaler Ebene kann keine neue Webdienste-Konfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e00af-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="e00af-109">Das EnableGroupExansion-Attribut ist speziell für das Adressbuch interessant.</span><span class="sxs-lookup"><span data-stu-id="e00af-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="e00af-110">Wenn Sie auf "true" festgelegt ist, können die Webdienste auf Anforderungen für Gruppen Erweiterungen Antworten.</span><span class="sxs-lookup"><span data-stu-id="e00af-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="e00af-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e00af-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="e00af-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e00af-112">See Also</span></span>


[<span data-ttu-id="e00af-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="e00af-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

