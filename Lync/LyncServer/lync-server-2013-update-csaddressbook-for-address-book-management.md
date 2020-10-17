---
title: 'Lync Server 2013: Update-CsAddressBook für die Adressbuchverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdbef7a3826a734262a77aa39fb2ce32e547463
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527702"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e6b0f-102">Update-CsAddressBook für die Adressbuchverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b0f-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b0f-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e6b0f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e6b0f-104">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Update-CsAddressBook-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="e6b0f-105">Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten RBAC (Role-based Access Control)-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde, (einschließlich aller von Ihnen erstellen benutzerdefinierten RBAC-Rollen):</span><span class="sxs-lookup"><span data-stu-id="e6b0f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="e6b0f-106">Das Cmdlet Update-CsAddressBook ersetzt den Befehl **abserver.exe – syncNow** von Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="e6b0f-107">Der Zweck des Cmdlets besteht darin, eine Synchronisierung sofort zu initiieren, anstatt auf die geplante Zeit zu warten.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="e6b0f-108">Im ersten Beispielbefehl werden alle Adressbücher in der Organisation aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="e6b0f-109">Die zweite aktualisiert nur das Adressbuch, das dem definierten Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6b0f-110">In lync Server 2013 übernimmt lync Server Benutzerreplikationsdienst die Änderungen aus Active Directory und aktualisiert die lync Server Benutzerdatenbank basierend auf einem konfigurierten Intervall.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="e6b0f-111">Lync Server Benutzerreplikationsdienst wird die Änderungen auch schnell an die RTCab-Datenbank weitergeben, ohne dass der Administrator Update-CSAddressBook ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="e6b0f-112">Administratoren müssen Update-CSAddressBook nur ausführen, wenn der Download der Adressbuchdatei aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e6b0f-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="e6b0f-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6b0f-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="e6b0f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6b0f-114">See Also</span></span>


[<span data-ttu-id="e6b0f-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="e6b0f-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

