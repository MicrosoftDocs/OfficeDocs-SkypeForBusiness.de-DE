---
title: 'Lync Server 2013: Erstellen eines Kerberos-Authentifizierungskontos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="bfabd-102">Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfabd-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfabd-103">_**Letztes Änderungsdatum des Themas:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="bfabd-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="bfabd-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="bfabd-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="bfabd-105">Sie können für jede Website Kerberos-Authentifizierungs Konten erstellen, oder Sie können ein einzelnes Kerberos-Authentifizierungs Konto erstellen und für alle Websites verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfabd-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="bfabd-106">Sie verwenden Windows PowerShell-Cmdlets zum Erstellen und Verwalten der Konten, einschließlich der Ermittlung der Konten, die den einzelnen Websites zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bfabd-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="bfabd-107">Der Topologie-Generator und die lync Server 2013-Systemsteuerung zeigen keine Kerberos-Authentifizierungs Konten an.</span><span class="sxs-lookup"><span data-stu-id="bfabd-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="bfabd-108">Gehen Sie wie folgt vor, um ein oder mehrere Benutzerkonten zu erstellen, die für die Kerberos-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bfabd-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="bfabd-109">So erstellen Sie ein Kerberos-Konto</span><span class="sxs-lookup"><span data-stu-id="bfabd-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="bfabd-110">Melden Sie sich als Mitglied der Gruppe Domänenadministratoren bei einem Computer in der Domäne mit lync Server 2013 oder auf einem Computer an, auf dem die Verwaltungstools installiert sind.</span><span class="sxs-lookup"><span data-stu-id="bfabd-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="bfabd-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bfabd-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bfabd-112">Führen Sie in der Befehlszeile den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bfabd-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="bfabd-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bfabd-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="bfabd-114">Vergewissern Sie sich, dass das Computerobjekt erstellt wurde, indem Sie Active Directory-Benutzer und-Computer öffnen, den Container **Benutzer** erweitern und dann bestätigen, dass sich das Computerobjekt für das Benutzerkonto im Container befindet.</span><span class="sxs-lookup"><span data-stu-id="bfabd-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

