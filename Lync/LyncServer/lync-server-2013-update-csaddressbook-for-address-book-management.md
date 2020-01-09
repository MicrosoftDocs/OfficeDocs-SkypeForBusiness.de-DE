---
title: 'Lync Server 2013: Update-CsAddressBook für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e10f9d52d9e4090601330cad44d5da03e69540
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f6f1b-102">Update-CsAddressBook für die Verwaltung von Adressbüchern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6f1b-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6f1b-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f6f1b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f6f1b-104">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Update-CsAddressBook-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f6f1b-105">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller rollenbasierten zugriffssteuerungsrollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="f6f1b-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="f6f1b-106">Das Cmdlet Update-CsAddressBook ersetzt den Befehl **ABServer. exe – syncNow** von Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="f6f1b-107">Der Zweck des Cmdlets besteht darin, eine Synchronisierung sofort zu initiieren, anstatt auf die geplante Zeit zu warten.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="f6f1b-108">Mit dem ersten Beispielbefehl werden alle Adressbücher in der Organisation aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="f6f1b-109">Der zweite aktualisiert nur das Adressbuch, das dem definierten Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6f1b-110">In lync Server 2013 wird der lync Server-Benutzerreplikationsdienst die Änderungen aus Active Directory aufnehmen und die lync Server-Benutzerdatenbank basierend auf einem konfigurierten Intervall aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="f6f1b-111">Der lync Server-Benutzerreplikationsdienst gibt die Änderungen auch schnell an die RTCab-Datenbank weiter, ohne dass der Administrator Update-CSAddressBook ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="f6f1b-112">Administratoren müssen nur Update-CSAddressBook ausführen, wenn der Download der Adressbuchdatei aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f6f1b-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="f6f1b-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f6f1b-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="f6f1b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6f1b-114">See Also</span></span>


[<span data-ttu-id="f6f1b-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="f6f1b-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

