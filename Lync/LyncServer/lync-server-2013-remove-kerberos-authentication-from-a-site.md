---
title: 'Lync Server 2013: Entfernen der Kerberos-Authentifizierung von einer Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fdf5a304d428efb3b1192d02ade0187f052171
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536412"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="6465c-102">In lync Server 2013 Entfernen der Kerberos-Authentifizierung von einer Website</span><span class="sxs-lookup"><span data-stu-id="6465c-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6465c-103">_**Letztes Änderungsstand des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="6465c-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="6465c-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="6465c-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="6465c-105">Wenn Sie die Kerberos-Authentifizierung von einem Standort entfernen oder eine Website zurückziehen müssen, müssen Sie die Kerberos-Authentifizierungs Konto Zuweisung von der Website mithilfe des Cmdlets **Remove-CsKerberosAccountAssignment** entfernen.</span><span class="sxs-lookup"><span data-stu-id="6465c-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="6465c-106">Verwenden Sie das folgende Verfahren, um die Zuweisung von Kerberos-Authentifizierungs Konten zu entfernen, wodurch die Zuweisung von allen Computern am Standort entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6465c-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="6465c-107">Wenn Sie das Kerberos-fähige Konto dauerhaft in den Ruhestand ziehen, sollten Sie Active Directory Benutzer und Computer verwenden, um es aus Active Directory-Domänendienste zu löschen, nachdem Sie die Zuordnung entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="6465c-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="6465c-108">Wenn Sie das Objekt in der Zukunft verwenden möchten, sollten Sie das Active Directory-Objekt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6465c-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="6465c-109">So entfernen Sie die Kerberos-Authentifizierung aus einem Standort</span><span class="sxs-lookup"><span data-stu-id="6465c-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="6465c-110">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an einem Computer mit den Verwaltungstools installiert ist.</span><span class="sxs-lookup"><span data-stu-id="6465c-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="6465c-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6465c-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6465c-112">Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="6465c-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="6465c-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6465c-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6465c-114">Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6465c-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

