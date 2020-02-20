---
title: Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac1ca9cd79206ddd26a5bc139d40b1df8337dab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="ad348-102">Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad348-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad348-103">_**Letztes Änderungsstand des Themas:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="ad348-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="ad348-104">Das SIP/CSTA-Gateway muss als vertrauenswürdige Anwendung konfiguriert sein, damit lync Server eine statische Route für die Weiterleitung von Anrufen an das Gateway anwenden können.</span><span class="sxs-lookup"><span data-stu-id="ad348-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ad348-105">Wenn Sie Benutzer aus einer früheren Version von lync Server-Bereitstellung migrieren, müssen Sie unbedingt alle vorhandenen Einträge für vertrauenswürdige Anwendungen (zuvor als autorisierte Hosteinträge bezeichnet) entfernt haben, die Sie für das SIP/CSTA-Gateway erstellt haben, bevor Sie die Verfahren in diesem Thema befolgen.</span><span class="sxs-lookup"><span data-stu-id="ad348-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="ad348-106">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Entfernen eines autorisierten Legacyhosts in lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="ad348-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="ad348-107">Wenn Sie die Bereitstellung einer neuen Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) planen, müssen Sie überprüfen, ob die <STRONG>Einschränkung der Dienstnutzung auf ausgewählte IP-Adressen</STRONG> für vorhandene Vertrauenswürdige Anwendungen und Pools festgelegt werden soll, wenn Sie denselben TCP-Port für die neue vertrauenswürdige Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad348-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="ad348-108">So konfigurieren Sie Einträge für vertrauenswürdige Anwendungen für das SIP/CSTA-Gateway</span><span class="sxs-lookup"><span data-stu-id="ad348-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="ad348-109">Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder als rollenbasierte zugriffssteuerungsrolle installiert ist, der Sie das Cmdlet **New-CsTrustedApplicationPool** zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="ad348-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="ad348-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ad348-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad348-111">Gehen Sie zum Erstellen eines Eintrags für eine vertrauenswürdige Anwendung folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="ad348-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="ad348-112">Geben Sie für eine TLS-Verbindung (Transport Layer Security) den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="ad348-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="ad348-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad348-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="ad348-114">Geben Sie für eine TCP-Verbindung (Transmission Control Protocol) den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="ad348-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="ad348-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad348-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="ad348-116">Gehen Sie folgendermaßen vor, um die vertrauenswürdige Anwendung zu einem Pool hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="ad348-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="ad348-117">Geben Sie für eine TLS-Verbindung den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="ad348-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="ad348-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad348-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="ad348-119">Geben Sie für eine TCP-Verbindung den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="ad348-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="ad348-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad348-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="ad348-121">Zur Implementierung der veröffentlichten Topologieänderungen geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="ad348-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad348-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad348-122">See Also</span></span>


[<span data-ttu-id="ad348-123">Konfigurieren einer statischen Route für die Remoteanrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad348-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="ad348-124">Definieren einer SIP/CSTA-Gateway-IP-Adresse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad348-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

