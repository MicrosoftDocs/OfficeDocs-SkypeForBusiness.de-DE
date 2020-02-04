---
title: Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="bd21e-102">Synchronisieren eines Kennworts für das Kerberos-Authentifizierungskonto mit IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd21e-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd21e-103">_**Letztes Änderungsdatum des Themas:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="bd21e-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="bd21e-104">Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der Mitglied der RTCUniversalServerAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="bd21e-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="bd21e-105">Auf einer Website können Front-End-Server, Standard Edition-Server und Directors ein Kerberos-Authentifizierungs Konto verwenden, um Anforderungen an den Webdienst Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bd21e-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="bd21e-106">Dieses Verfahren sucht jeden Server mit Webdiensten auf einer Website, der ein Kerberos-Konto zugewiesen wurde, und aktualisiert die Konfigurationseinstellungen für Internet Informationsdienste (IIS) so, dass das Kerberos-Konto verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd21e-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="bd21e-107">Ausführliche Informationen finden Sie unter [Festlegen eines Kennworts für ein Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd21e-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="bd21e-108">So können Sie ein Kennwort für ein Kerberos-Authentifizierungs Konto festlegen und konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bd21e-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="bd21e-109">Melden Sie sich bei einem Quellcomputer (wie fe01.contoso.com) als Mitglied der RTCUniversalServerAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="bd21e-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="bd21e-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bd21e-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bd21e-111">Führen Sie in der Befehlszeile der lync Server-Verwaltungsshell die folgenden beiden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bd21e-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="bd21e-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd21e-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bd21e-113">Der Name des Quellcomputers und des Zielcomputers muss ein FQDN-Name (Fully Qualified Domain) des Servers sein.</span><span class="sxs-lookup"><span data-stu-id="bd21e-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="bd21e-114">Sie können den Pool-FQDN nur verwenden, wenn der Poolname mit dem Namen des Computers identisch ist, den Sie als Quellcomputer oder Zielcomputer verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd21e-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="bd21e-115">Nachdem Sie die Kerberos-Authentifizierung geändert haben, beispielsweise ein Konto hinzugefügt oder ein Konto entfernt haben, müssen Sie <STRONG>enable-CsTopology</STRONG> über die Eingabeaufforderung der lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="bd21e-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

