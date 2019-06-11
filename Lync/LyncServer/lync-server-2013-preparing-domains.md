---
title: 'Lync Server 2013: Vorbereiten von Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1f5693a14084627d20ae66fa6ec85f6b6c6c6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="be888-102">Vorbereiten von Domänen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be888-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be888-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="be888-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="be888-104">Die Domänenvorbereitung ist der letzte Schritt beim Vorbereiten der Active Directory-Domänendienste für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be888-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="be888-105">Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen ACEs (Access Control Entries, Zugriffssteuerungseinträge) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="be888-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="be888-106">Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="be888-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="be888-107">Sie können die Domänenvorbereitung auf jedem Computer in der Domäne ausführen, in der Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="be888-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="be888-108">Sie müssen jede Domäne vorbereiten, die lync Server oder Benutzer hosten soll.</span><span class="sxs-lookup"><span data-stu-id="be888-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="be888-109">Wenn die Vererbung von Berechtigungen deaktiviert ist oder die Berechtigungen für authentifizierte Benutzer in Ihrer Organisation deaktiviert sind, müssen Sie während der Domänenvorbereitung weitere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="be888-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="be888-110">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="be888-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="be888-111">Wenn Ihre Organisation Organisationseinheiten (OU) anstelle der drei integrierten Container (also Benutzer, Computer und Domänencontroller) verwendet, müssen Sie den Organisationseinheiten Lesezugriff für die Gruppe Authentifizierte Benutzer erteilen.</span><span class="sxs-lookup"><span data-stu-id="be888-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="be888-112">Für die Domänenvorbereitung ist Lesezugriff auf die Container erforderlich.</span><span class="sxs-lookup"><span data-stu-id="be888-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="be888-113">Wenn die Gruppe der authentifizierten Benutzer keinen Lesezugriff auf die Organisationseinheit hat, führen Sie das Cmdlet **Grant-CsOuPermission** aus, wie in den folgenden Codebeispielen veranschaulicht, um Leseberechtigungen für jede OU zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="be888-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="be888-114">Details zum Cmdlet **Grant-CsOuPermission** finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="be888-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="be888-115">Details zu den ACEs, die im Domänenstamm und in den Containern Benutzer, Computer und Domänencontroller erstellt wurden, finden Sie unter Änderungen, die <A href="lync-server-2013-changes-made-by-domain-preparation.md">von der Domänenvorbereitung in lync Server 2013 vorgenommen</A>wurden.</span><span class="sxs-lookup"><span data-stu-id="be888-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be888-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="be888-116">In This Section</span></span>

  - [<span data-ttu-id="be888-117">Ausführen der Domänenvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be888-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="be888-118">Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be888-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

