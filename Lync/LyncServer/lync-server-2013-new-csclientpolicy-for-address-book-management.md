---
title: 'Lync Server 2013: New-CsClientPolicy für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a253fb46dfdfe63957efa97ffa68d97ead65ed87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508822"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f3643-102">New-CsClientPolicy für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3643-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3643-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3643-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3643-104">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet New-CsClientPolicy lokal ausführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3643-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f3643-105">Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten RBAC (Role-based Access Control)-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, (einschließlich aller von Ihnen erstellen benutzerdefinierten RBAC-Rollen):</span><span class="sxs-lookup"><span data-stu-id="f3643-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="f3643-106">Das Cmdlet New-CsClientPolicy definiert eine große Anzahl von Einstellungen für die Bereitstellung von Clients für Features, die in lync Server 2013 verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f3643-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="f3643-107">Für den Adressbuchdienst ist der Parameter AddressBookAvailability von Interesse.</span><span class="sxs-lookup"><span data-stu-id="f3643-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="f3643-108">Dieser Parameter, der sich direkt auf die für Clients verfügbaren Optionen auswirkt, bietet drei mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="f3643-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="f3643-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="f3643-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="f3643-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="f3643-110">WebSearchOnly</span></span>

  - <span data-ttu-id="f3643-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="f3643-111">FileDownloadOnly</span></span>

<span data-ttu-id="f3643-p103">Dieser Parameter, sofern definiert, gibt an, wie durch Clients auf das Adressbuch zugegriffen wird. Wenn Sie diesen Parameter definieren, müssen Sie eine der Optionen festlegen. Wenn Sie diese Einstellung nicht ändern, bleibt der Standardwert "WebSearchAndFileDownload" in Kraft.</span><span class="sxs-lookup"><span data-stu-id="f3643-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="f3643-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f3643-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="f3643-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3643-116">See Also</span></span>


[<span data-ttu-id="f3643-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="f3643-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

