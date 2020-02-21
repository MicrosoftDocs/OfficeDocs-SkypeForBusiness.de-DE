---
title: 'Lync Server 2013: Konfigurieren einer statischen Route für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e871e3023449123af76530659397e1faa6b51d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="88454-102">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88454-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88454-103">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="88454-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="88454-104">Für die Remote Anrufsteuerung muss jeder lync Server-Pool mit einem Pfad vom Pool zum SIP/CSTA-Gateway konfiguriert werden, das eine Verbindung mit der PBX-Anlage (Private Branch Exchange, Nebenstellenanlage) herstellt.</span><span class="sxs-lookup"><span data-stu-id="88454-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="88454-105">Dieser Pfad erfordert, dass jeder Pool über eine statische Route für jedes Gateway verfügt, für das der Pool SIP-Anrufsteuerungsnachrichten für Anrufe an die Nebenstellenanlage proxyt.</span><span class="sxs-lookup"><span data-stu-id="88454-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="88454-106">Wenn Sie eine globale statische Route für die Remoteanrufsteuerung konfigurieren, wird für jeden Pool, der nicht mit einer statischen Route auf Poolebene konfiguriert ist, die globale statische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="88454-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="88454-107">So konfigurieren Sie eine statische Route für die Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="88454-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="88454-108">Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet **New-CsStaticRoute** zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="88454-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="88454-109">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="88454-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88454-110">Führen Sie einen der folgenden Schritte aus, um eine statische Route zu erstellen und Sie in der Variablen $TLSRoute oder $TCPRoute zu platzieren:</span><span class="sxs-lookup"><span data-stu-id="88454-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="88454-111">Um untergeordnete Domänen einer Domäne abzugleichen, können Sie einen Platzhalterwert im Parameter MatchUri angeben.</span><span class="sxs-lookup"><span data-stu-id="88454-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="88454-112">Beispiel: <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88454-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="88454-113">Dieser Wert entspricht einer Domäne, die mit dem Suffix <STRONG>contoso.net</STRONG>endet.</span><span class="sxs-lookup"><span data-stu-id="88454-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="88454-114">Geben Sie für eine TLS-Verbindung (Transport Layer Security) den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="88454-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="88454-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88454-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="88454-116">Wenn UseDefaultCertificate auf false festgelegt ist, müssen Sie TLSCertIssuer-und TLSCertSerialNumber-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="88454-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="88454-117">Diese Parameter geben den Namen der Zertifizierungsstelle an, die das in der statischen Route verwendete Zertifikat ausgestellt hat, sowie die Seriennummer des jeweiligen TLS-Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="88454-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="88454-118">Ausführliche Informationen zu diesen Parametern finden Sie unter lync Server-Verwaltungsshell Hilfe, indem Sie an der Eingabeaufforderung Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="88454-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="88454-119">Geben Sie für eine TCP-Verbindung (Transmission Control Protocol) den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="88454-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="88454-120">Wenn Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) angeben, müssen Sie zuerst einen Domain Name System (DNS) einen Datensatz konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="88454-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="88454-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88454-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="88454-122">Im folgenden sind die Standardwerte für optionale Parameter für statische Routen angegeben:</span><span class="sxs-lookup"><span data-stu-id="88454-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="88454-123">Enabled = true</span><span class="sxs-lookup"><span data-stu-id="88454-123">Enabled = True</span></span>
        
          - <span data-ttu-id="88454-124">MatchOnlyPhoneUri = false</span><span class="sxs-lookup"><span data-stu-id="88454-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="88454-125">ReplaceHostInRequestUri = false</span><span class="sxs-lookup"><span data-stu-id="88454-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="88454-126">Es wird dringend empfohlen, diese Standardwerte nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="88454-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="88454-127">Wenn Sie jedoch einen dieser Parameter ändern müssen, lesen Sie lync Server-Verwaltungsshell Hilfe, indem Sie an der Eingabeaufforderung Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="88454-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="88454-128">Führen Sie nach Bedarf eine der folgenden Aktionen aus, um eine neu erstellte statische Route im zentralen Verwaltungsspeicher beizubehalten:</span><span class="sxs-lookup"><span data-stu-id="88454-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88454-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88454-129">See Also</span></span>


[<span data-ttu-id="88454-130">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88454-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="88454-131">Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88454-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

