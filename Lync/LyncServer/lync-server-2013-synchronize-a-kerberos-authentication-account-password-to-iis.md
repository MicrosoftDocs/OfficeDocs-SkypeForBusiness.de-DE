---
title: Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS
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
ms.openlocfilehash: 4ac886bf4eba4261a733241aa8d1d5396c4acc86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523852"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="d745f-102">Synchronisieren eines Kennworts für das Kerberos-Authentifizierungs Konto mit IIS in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d745f-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d745f-103">_**Letztes Änderungsstand des Themas:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="d745f-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="d745f-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d745f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="d745f-105">Auf einem Standort können Front-End-Server, Standard Edition-Server und Directors ein Kerberos-Authentifizierungs Konto verwenden, um Anforderungen an den Webdienste Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d745f-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="d745f-106">Dieses Verfahren sucht jeden Server, auf dem Webdienste ausgeführt wird, auf einem Standort, dem ein Kerberos-Konto zugewiesen wurde, und aktualisiert die Internet Information Services (IIS) Konfigurationseinstellungen für die Verwendung des Kerberos-Kontos.</span><span class="sxs-lookup"><span data-stu-id="d745f-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="d745f-107">Ausführliche Informationen finden Sie unter [Festlegen eines Kennworts für das Kerberos-Authentifizierungs Konto auf einem Server in lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="d745f-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="d745f-108">So legen Sie ein Kennwort für das Kerberos-Authentifizierungskonto fest</span><span class="sxs-lookup"><span data-stu-id="d745f-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="d745f-109">Melden Sie sich bei einem Quellcomputer (z. B. "fe01.contoso.com") als Mitglied der Gruppe "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="d745f-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d745f-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d745f-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d745f-111">Führen Sie in der lync Server-Verwaltungsshell Befehlszeile die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="d745f-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="d745f-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d745f-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d745f-p102">Bei den Namen für den Quell- und den Zielcomputer muss es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers handeln. Sie können den Pool-FQDN nur dann verwenden, wenn der Poolname mit dem Namen des Computers übereinstimmt, den Sie als Quell- oder Zielcomputer verwenden.</span><span class="sxs-lookup"><span data-stu-id="d745f-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d745f-115">Nachdem Sie Änderungen an der Kerberos-Authentifizierung vorgenommen haben, wie beispielsweise das Hinzufügen eines Kontos oder das Entfernen eines Kontos, müssen Sie <STRONG>enable-CsTopology</STRONG> über die lync Server-Verwaltungsshell Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="d745f-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

