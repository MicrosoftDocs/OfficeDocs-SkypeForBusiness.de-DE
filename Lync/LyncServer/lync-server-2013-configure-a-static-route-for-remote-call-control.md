---
title: 'Lync Server 2013: Konfigurieren einer statischen Route für die Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="cca19-102">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cca19-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cca19-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="cca19-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="cca19-104">Die Remote Anrufsteuerung setzt voraus, dass jeder lync Server-Pool mit einem Pfad von diesem Pool zum SIP/CSTA-Gateway konfiguriert ist, das eine Verbindung mit der PBX (Private Branch Exchange) herstellt.</span><span class="sxs-lookup"><span data-stu-id="cca19-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="cca19-105">Dieser Pfad setzt voraus, dass jeder Pool über eine statische Route für jedes Gateway verfügt, für das der Pool SIP-Anruf Steuerungsmeldungen erhält, die mit Anrufen an die Telefonanlage verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="cca19-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="cca19-106">Wenn Sie eine globale statische Route für die Remoteanrufsteuerung konfigurieren, wird für jeden Pool, der nicht mit einer statischen Route auf der Poolebene konfiguriert ist, die globale statische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="cca19-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="cca19-107">So konfigurieren Sie eine statische Route für die Remoteanrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="cca19-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="cca19-108">Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder einer rollenbasierten zugriffssteuerungsrolle (Role-Based Access Control, RBAC) installiert ist, der Sie das Cmdlet **New-CsStaticRoute** zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="cca19-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="cca19-109">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="cca19-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cca19-110">Führen Sie eine der folgenden Aktionen aus, um eine statische Route zu erstellen und Sie in der Variablen $TLSRoute oder $TCPRoute zu speichern:</span><span class="sxs-lookup"><span data-stu-id="cca19-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="cca19-111">Wenn Sie untergeordnete Domänen einer Domäne abgleichen möchten, können Sie im MatchUri-Parameter einen Platzhalterwert angeben.</span><span class="sxs-lookup"><span data-stu-id="cca19-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="cca19-112">Beispiel: <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cca19-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="cca19-113">Dieser Wert entspricht jeder Domäne, die mit dem Suffix <STRONG>contoso.net</STRONG>endet.</span><span class="sxs-lookup"><span data-stu-id="cca19-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="cca19-114">Bei einer TLS-Verbindung (Transport Layer Security) geben Sie Folgendes an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="cca19-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="cca19-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cca19-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="cca19-116">Wenn UseDefaultCertificate auf "false" festgelegt ist, müssen Sie TLSCertIssuer-und TLSCertSerialNumber-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="cca19-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="cca19-117">Diese Parameter geben den Namen der Zertifizierungsstelle an, die das in der statischen Route verwendete Zertifikat ausgestellt hat, und die Seriennummer des jeweiligen TLS-Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="cca19-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="cca19-118">Details zu diesen Parametern finden Sie unter Hilfe zur lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="cca19-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="cca19-119">Bei einer TCP-Verbindung (Transmission Control Protocol) geben Sie Folgendes an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="cca19-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="cca19-120">Wenn Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) angeben, müssen Sie zuerst einen DNS-Eintrag (Domain Name System) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cca19-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="cca19-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cca19-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="cca19-122">Im folgenden finden Sie die Standardwerte für optionale Parameter für statische Routen:</span><span class="sxs-lookup"><span data-stu-id="cca19-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="cca19-123">Enabled = wahr</span><span class="sxs-lookup"><span data-stu-id="cca19-123">Enabled = True</span></span>
        
          - <span data-ttu-id="cca19-124">MatchOnlyPhoneUri = falsch</span><span class="sxs-lookup"><span data-stu-id="cca19-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="cca19-125">ReplaceHostInRequestUri = falsch</span><span class="sxs-lookup"><span data-stu-id="cca19-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="cca19-126">Wir empfehlen dringend, diese Standardwerte nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cca19-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="cca19-127">Wenn Sie jedoch einen dieser Parameter ändern müssen, lesen Sie Hilfe zur lync Server-Verwaltungsshell, indem Sie an der Eingabeaufforderung Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="cca19-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="cca19-128">Führen Sie eine der folgenden Aktionen aus, um eine neu erstellte statische Route im zentralen Verwaltungsspeicher beizubehalten:</span><span class="sxs-lookup"><span data-stu-id="cca19-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cca19-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cca19-129">See Also</span></span>


[<span data-ttu-id="cca19-130">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cca19-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="cca19-131">Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cca19-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

