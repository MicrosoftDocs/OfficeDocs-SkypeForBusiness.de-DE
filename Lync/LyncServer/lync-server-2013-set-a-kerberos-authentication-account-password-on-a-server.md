---
title: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server'
description: 'Lync Server 2013: Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 723392e670ca0b4bc9796cd62dab3b1a61f99dd1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574841"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="39f3e-103">Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39f3e-103">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f3e-104">_**Letztes Änderungsstand des Themas:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="39f3e-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="39f3e-105">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="39f3e-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="39f3e-106">Für das Kerberos-Konto muss für jeden Standort, der über Front-End-Server, Standard Edition-Server und Director-Server verfügt, ein Kennwort eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="39f3e-106">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="39f3e-107">Sie können das Kennwort einrichten, indem Sie das Cmdlet " **CsKerberosAccountPassword**   Windows PowerShell" auf einem Server am Standort ausführen (beispielsweise ein Front-End-Server).</span><span class="sxs-lookup"><span data-stu-id="39f3e-107">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="39f3e-108">Für jeden Standort müssen Sie das Cmdlet " **CsKerberosAccountPassword**" Ausführen   .</span><span class="sxs-lookup"><span data-stu-id="39f3e-108">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="39f3e-109">Das Cmdlet konfiguriert Internet Information Services (IIS) für den Webdienste Dienst und legt dann das Kennwort für das Computerkonto in Active Directory-Domänendienste fest.</span><span class="sxs-lookup"><span data-stu-id="39f3e-109">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="39f3e-110">Bei einer alternativen Methode wird IIS abhängig davon, welcher Parameter mit dem Cmdlet verwendet wird, auf einem Server konfiguriert, während ein anderer Server verwendet wird, der als Quelle des Kerberos-Kontokennworts konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="39f3e-110">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="39f3e-111">Bei Verwendung des Cmdlets **Set-CsKerberosAccountPassword** zum Festlegen des Kennworts legt Kerberos das Kennwort auf eine nach dem Zufallsprinzip generierte Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="39f3e-111">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="39f3e-112">Dieses Cmdlet kontaktiert alle IIS-Instanzen an allen lync Server 2013 zentralen Standorten, denen dieses Konto zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="39f3e-112">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="39f3e-113">So legen Sie ein Kennwort für ein Kerberos-Authentifizierungskonto fest</span><span class="sxs-lookup"><span data-stu-id="39f3e-113">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="39f3e-114">Melden Sie sich an einem beliebigen Domänencomputer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="39f3e-114">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39f3e-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="39f3e-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="39f3e-116">Führen Sie an der Befehlszeile die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="39f3e-116">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="39f3e-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39f3e-117">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39f3e-p103">Sie müssen den Parameter "UserAccount" im Format "Domäne\Benutzer" angeben. Das Format "Benutzer@Domäne.Erweiterung" wird zur Referenzierung der für die Kerberos-Authentifizierung erstellten Computerobjekte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39f3e-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="39f3e-120">Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="39f3e-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

