---
title: 'Lync Server 2013: Zuweisen eines Kerberos-Authentifizierungs Kontos zu einem Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf69e71dd66337551557bddd3bfb7700257a7f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="ca7c3-102">Zuweisen eines Kerberos-Authentifizierungs Kontos zu einem Standort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca7c3-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca7c3-103">_**Letztes Änderungsstand des Themas:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="ca7c3-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="ca7c3-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="ca7c3-105">Nach der Erstellung des Kerberos-Kontos müssen Sie dieses einem Standort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="ca7c3-106">Dies ist eine lync Server 2013 Website, keine Active Directory Website.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="ca7c3-107">Sie können pro Bereitstellung mehrere Kerberos-Authentifizierungskonten erstellen, einem Standort kann jedoch nur jeweils ein Konto zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="ca7c3-108">Verwenden Sie das folgende Verfahren, um ein zuvor erstelltes Kerberos-Authentifizierungskonto einem Standort zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="ca7c3-109">Ausführliche Informationen zum Erstellen des Kerberos-Kontos finden Sie unter [Erstellen eines Kerberos-Authentifizierungs Kontos in lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="ca7c3-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="ca7c3-110">So weisen Sie ein Kerberos-Authentifizierungskonto einem Standort zu</span><span class="sxs-lookup"><span data-stu-id="ca7c3-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="ca7c3-111">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins bei einem Computer in der Domäne an, auf dem lync Server 2013 oder an einem Computer mit den Verwaltungstools installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="ca7c3-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ca7c3-113">Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="ca7c3-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="ca7c3-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ca7c3-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="ca7c3-p102">Sie müssen den Parameter "UserAccount" im Format "Domäne\Benutzer" angeben. Das Format "Benutzer@Domäne.Erweiterung" wird zur Referenzierung der für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="ca7c3-117">**Optional**: Sie haben möglicherweise einen außer Kraft setzen-FQDN (vollqualifizierter Domänenname) für Ihre Webservices konfiguriert, wie pro [Änderung der Webdienste-URL in lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="ca7c3-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="ca7c3-118">Wenn dies der Fall ist, müssen Sie auch einen SPN für diesen FQDN hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="ca7c3-119">Wenn der FQDN beispielsweise "Webservices. contoso. local" war, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ca7c3-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ca7c3-120">Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ca7c3-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

