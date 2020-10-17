---
title: 'Lync Server 2013: Bereitstellen des SEFAUtil-Tools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91392470d47cc4d59130e7c304656f9eee48ae5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531372"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="18213-102">Bereitstellen des SEFAUtil-Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18213-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18213-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="18213-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="18213-104">Zum Bereitstellen und Verwalten der gruppenanrufannahme müssen Sie das SEFAUtil Resource Kit-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="18213-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="18213-105">Das Tool ist Teil der lync Server 2013 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="18213-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="18213-106">Bevor Sie SEFAUtil installieren können, müssen Sie über einen vertrauenswürdigen Anwendungspool in Ihrer Topologie verfügen, SEFAUtil als vertrauenswürdige Anwendung angeben und die Topologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="18213-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18213-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK müssen auf jedem Computer installiert sein, auf dem Sie das SEFAUtil-Tool ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="18213-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="18213-108">Sie können das SEFAUtil in jeder beliebigen Front-End-Pool in Ihrer Bereitstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="18213-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18213-109">Weitere Informationen zur Ausführung von SEFAUtil finden Sie im TechNet-Blog Artikel "How to Get SEFAUtil Running?".</span><span class="sxs-lookup"><span data-stu-id="18213-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="18213-110">an <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .</span><span class="sxs-lookup"><span data-stu-id="18213-110">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="18213-111">So stellen Sie SEFAUtil bereit</span><span class="sxs-lookup"><span data-stu-id="18213-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="18213-112">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="18213-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="18213-113">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="18213-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="18213-114">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="18213-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="18213-115">Definieren Sie bei Bedarf einen vertrauenswürdigen Anwendungspool für die Front-End-Pool, in der Sie SEFAUtil ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="18213-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="18213-116">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18213-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="18213-117">Definieren Sie das SEFAUtil-Tool als vertrauenswürdige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="18213-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="18213-118">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18213-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18213-119">Sie können bei Bedarf einen anderen Port verwenden.</span><span class="sxs-lookup"><span data-stu-id="18213-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="18213-120">Aktivieren Sie die Topologie mit Ihren Änderungen.</span><span class="sxs-lookup"><span data-stu-id="18213-120">Enable the topology with your changes.</span></span> <span data-ttu-id="18213-121">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18213-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="18213-122">Installieren Sie die lync Server 2013 Resource Kit-Tools auf einem Front-End-Server im vertrauenswürdigen Anwendungspool, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="18213-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="18213-123">Stellen Sie sicher, dass das SEFAUtil-Tool wie folgt ordnungsgemäß ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="18213-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="18213-124">Führen Sie das Tool über die Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in Ihrer Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="18213-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="18213-125">Das Tool befindet sich im Verzeichnis \Programme\Microsoft lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="18213-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="18213-126">Zeigt die Anrufweiterleitungseinstellungen eines Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="18213-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="18213-127">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="18213-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="18213-128">Die Anrufweiterleitungseinstellungen für den Benutzer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18213-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

