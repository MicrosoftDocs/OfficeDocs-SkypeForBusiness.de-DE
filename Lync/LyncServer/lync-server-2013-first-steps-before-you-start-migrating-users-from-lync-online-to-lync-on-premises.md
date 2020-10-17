---
title: 'Lync Server 2013: Erste Schritte vor dem Start der Migration von Benutzern von lync online zu lync lokal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8065d1c09ab48b1b3a874fd11d7f8fcad298bfcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500842"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="f6b44-102">Erste Schritte vor dem Start der Migration von Benutzern von lync online zu lync lokal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6b44-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6b44-103">_**Letztes Änderungsstand des Themas:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="f6b44-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="f6b44-104">Bevor Sie mit dem Verschieben lync Online Benutzer in Ihre lokale Umgebung beginnen, überprüfen Sie, dass alle der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="f6b44-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="f6b44-105">Ihre lync Server lokale Umgebung muss vollständig bereitgestellt und überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="f6b44-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="f6b44-106">Weitere Informationen finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6b44-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="f6b44-107">Ihr lync Online-Mandant muss für den Remote-PowerShell-Zugriff konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="f6b44-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="f6b44-108">Installieren Sie dazu zunächst das lync Online Modul für Windows PowerShell, das Sie hier erhalten können: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="f6b44-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="f6b44-109">Nachdem Sie das Modul installiert haben, können Sie eine Remotesitzung einrichten, indem Sie die folgenden Cmdlets in der lync Server-Verwaltungsshell eingeben:</span><span class="sxs-lookup"><span data-stu-id="f6b44-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="f6b44-110">Weitere Informationen zum Einrichten einer Remote-PowerShell-Sitzung mit lync Online finden Sie unter [Herstellen einer Verbindung mit lync Online mithilfe von Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6b44-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="f6b44-111">Weitere Informationen zum Verwenden des lync Online-PowerShell-Moduls finden Sie unter [using Windows PowerShell to manage lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6b44-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="f6b44-112">Ihr lync Online muss für den freigegebenen SIP-Adressraum konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="f6b44-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="f6b44-113">Starten Sie dazu zunächst eine Remote-PowerShell-Sitzung mit lync online.</span><span class="sxs-lookup"><span data-stu-id="f6b44-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="f6b44-114">Führen Sie dann das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f6b44-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="f6b44-115">Nachdem Sie diese Schritte abgeschlossen haben, können Sie mit der [Migration lync Online Benutzer zu lokal in lync Server 2013 in lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f6b44-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

