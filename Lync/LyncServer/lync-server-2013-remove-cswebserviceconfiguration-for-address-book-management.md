---
title: 'Lync Server 2013: Remove-CsWebServiceConfiguration für Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f3e11219b41cc4717fc370b7f396980921e3403
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="05632-102">Remove-CsWebServiceConfiguration für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05632-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05632-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="05632-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="05632-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Remove-CsWebServiceConfiguration" lokal auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="05632-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="05632-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="05632-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="05632-106">Das Cmdlet Remove-CsWebServiceConfiguration ermöglicht es einem Administrator, eine zuvor erstellte Webdienste-Konfiguration zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="05632-106">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration.</span></span> <span data-ttu-id="05632-107">Das Cmdlet kann die globale Webdienste-Konfiguration nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="05632-107">The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="05632-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="05632-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="05632-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05632-109">See Also</span></span>


[<span data-ttu-id="05632-110">Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="05632-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

