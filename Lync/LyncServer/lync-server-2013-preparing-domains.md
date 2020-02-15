---
title: 'Lync Server 2013: Vorbereiten von Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173b1293fb4bf0353b4e6d9038d05c1480697d17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="4624a-102">Vorbereiten von Domänen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4624a-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4624a-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4624a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4624a-104">Die Domänenvorbereitung ist der letzte Schritt bei der Vorbereitung Active Directory-Domänendienste auf lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4624a-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="4624a-105">Beim Schritt zur Domänenvorbereitung werden universellen Gruppen die erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) hinzugefügt, über die Berechtigungen zum Hosten und Verwalten von Benutzern in der Domäne gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="4624a-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="4624a-106">Bei der Domänenvorbereitung werden ACEs im Domänenstamm und in drei integrierten Containern erstellt: für Benutzer, Computer und Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="4624a-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="4624a-107">Sie können die Domänenvorbereitung auf jedem Computer in der Domäne ausführen, in der Sie lync Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4624a-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="4624a-108">Sie müssen jede Domäne vorbereiten, in der lync Server oder Benutzer gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="4624a-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="4624a-109">Wenn die Vererbung von Berechtigungen deaktiviert ist oder authentifizierte Benutzerberechtigungen in Ihrer Organisation deaktiviert sind, müssen Sie während der Domänenvorbereitung zusätzliche Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="4624a-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="4624a-110">Ausführliche Informationen finden Sie unter [Vorbereiten einer gesperrten Active Directory-Domänendienste in lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="4624a-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="4624a-111">Wenn in Ihrer Organisation Organisationseinheiten (OU) anstelle der drei integrierten Container (Benutzer, Computer und Domänencontroller) verwendet werden, müssen Sie Lesezugriff auf die Organisationseinheiten für die Gruppe Authentifizierte Benutzer gewähren.</span><span class="sxs-lookup"><span data-stu-id="4624a-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="4624a-112">Der Lesezugriff auf die Container ist für die Domänenvorbereitung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4624a-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="4624a-113">Wenn die Gruppe Authentifizierte Benutzer nicht über Lesezugriff auf die Organisationseinheit verfügt, führen Sie das **Grant-CsOuPermission-** Cmdlet aus, wie in den folgenden Codebeispielen dargestellt, um Leseberechtigungen für jede Organisationseinheit zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="4624a-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="4624a-114">Ausführliche Informationen zum **Grant-CsOuPermission-** Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4624a-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="4624a-115">Ausführliche Informationen zu den ACEs, die im Domänenstamm und in den Containern Benutzer, Computer und Domänencontroller erstellt wurden, finden Sie unter Änderungen, die <A href="lync-server-2013-changes-made-by-domain-preparation.md">von der Domänenvorbereitung in lync Server 2013 vorgenommen</A>wurden.</span><span class="sxs-lookup"><span data-stu-id="4624a-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4624a-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4624a-116">In This Section</span></span>

  - [<span data-ttu-id="4624a-117">Ausführung der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4624a-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="4624a-118">Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4624a-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

