---
title: 'Lync Server 2013: New-CsClientPolicy für Adressbuchverwaltung'
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
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="de58d-102">New-CsClientPolicy für Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de58d-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de58d-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="de58d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="de58d-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet New-CsClientPolicy auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="de58d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="de58d-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="de58d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="de58d-106">Das Cmdlet New-CsClientPolicy definiert eine große Anzahl von Einstellungen für die Bereitstellung von Clients für Features, die in lync Server 2013 zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="de58d-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="de58d-107">Für den Adressbuchdienst ist der Parameter AddressBookAvailability von Interesse.</span><span class="sxs-lookup"><span data-stu-id="de58d-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="de58d-108">Dieser Parameter, der direkte Auswirkungen auf die für Clients verfügbaren Optionen hat, bietet drei mögliche Optionen:</span><span class="sxs-lookup"><span data-stu-id="de58d-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="de58d-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="de58d-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="de58d-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="de58d-110">WebSearchOnly</span></span>

  - <span data-ttu-id="de58d-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="de58d-111">FileDownloadOnly</span></span>

<span data-ttu-id="de58d-112">Nach der Definition wird bestimmt, wie der Zugriff auf das Adressbuch durch Clients erfolgt.</span><span class="sxs-lookup"><span data-stu-id="de58d-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="de58d-113">Wenn Sie diesen Parameter definieren, müssen Sie eine der Optionen definieren.</span><span class="sxs-lookup"><span data-stu-id="de58d-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="de58d-114">Wenn Sie diese Einstellung nicht ändern, bleibt die standardmäßige WebSearchAndFileDownload in Kraft.</span><span class="sxs-lookup"><span data-stu-id="de58d-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="de58d-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="de58d-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="de58d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de58d-116">See Also</span></span>


[<span data-ttu-id="de58d-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="de58d-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

