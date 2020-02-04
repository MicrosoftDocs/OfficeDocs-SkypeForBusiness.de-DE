---
title: 'Lync Server 2013: Schützen von IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="cb716-102">Schützen von IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb716-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb716-103">_**Letztes Änderungsdatum des Themas:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="cb716-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="cb716-104">In Microsoft Office Communications Server 2007 und Microsoft Office Communications Server 2007 R2 wurden Internet Informationsdienste (IIS) unter einem Standardbenutzerkonto ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb716-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="cb716-105">Dies hatte das Potenzial, Probleme zu verursachen: Wenn das Kennwort abgelaufen ist, könnten ihre Webdienste verloren gehen, ein Problem, das oft schwer zu diagnostizieren war.</span><span class="sxs-lookup"><span data-stu-id="cb716-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="cb716-106">Um das Problem von ablaufenden Kennwörtern zu vermeiden, können Sie mithilfe von Microsoft lync Server 2013 ein Computerkonto erstellen (für einen Computer, der nicht tatsächlich vorhanden ist), der als Authentifizierungs Prinzipal für alle Computer in einer Website fungieren kann, auf denen IIS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cb716-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="cb716-107">Da diese Konten das Kerberos-Authentifizierungsprotokoll verwenden, werden sie als Kerberos-Konten und der neue Authentifizierungsprozess als Kerberos-Webauthentifizierung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cb716-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="cb716-108">Auf diese Weise können Sie alle IIS-Server über ein einziges Konto verwalten.</span><span class="sxs-lookup"><span data-stu-id="cb716-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="cb716-109">Wenn Sie Ihre Server unter diesem Authentifizierungs Prinzipal ausführen möchten, müssen Sie zuerst ein Computerkonto erstellen, indem Sie das Cmdlet New-CsKerberosAccount verwenden. Dieses Konto wird dann einem oder mehreren Websites zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cb716-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="cb716-110">Nachdem die Zuweisung erfolgt ist, wird die Zuordnung zwischen dem Konto und der lync Server 2013-Website durch Ausführen des Cmdlets Enable-CsTopology aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cb716-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="cb716-111">Dadurch wird unter anderem der erforderliche Dienstprinzipalname (SPN) in den Active Directory-Domänendiensten (AD DS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb716-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="cb716-112">SPNs bieten Clientanwendungen die Möglichkeit, einen bestimmten Dienst zu finden.</span><span class="sxs-lookup"><span data-stu-id="cb716-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="cb716-113">Ausführliche Informationen finden Sie unter [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cb716-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="cb716-114">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="cb716-114">Best Practices</span></span>

<span data-ttu-id="cb716-115">Um die Sicherheit von IIS zu erhöhen, empfehlen wir, ein Kerberos-Konto für IIS zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cb716-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="cb716-116">Wenn Sie kein Kerberos-Konto implementieren, wird IIS unter einem Standardbenutzerkonto ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb716-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

