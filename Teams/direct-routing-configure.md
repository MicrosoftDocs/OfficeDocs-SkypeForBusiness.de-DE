---
title: Konfigurieren von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Sie das direkte Routing für das Microsoft-Telefonsystem konfigurieren.
ms.openlocfilehash: d1a763f150004b5c558dd311dd54ed6975dcb0c1
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018768"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="cbc7a-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="cbc7a-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="cbc7a-104">Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen von Direct Routing sowie dessen Planung und Bereitstellung an: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="cbc7a-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="cbc7a-105">Lesen Sie [Planen des direkten Routings](direct-routing-plan.md), falls Sie dies noch nicht getan haben, um weitere Informationen zu Voraussetzungen und weiteren Schritten zu erhalten, die Sie ausführen müssen, bevor Sie das Netzwerk Ihres Microsoft-Telefonsystems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="cbc7a-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing für das Microsoft-Telefonsystem konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="cbc7a-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer für die Verwendung von Direct Routing konfiguriert werden, um eine Verbindung mit dem öffentlichen Telefonfestnetz (PSTN) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="cbc7a-108">Um die in diesem Artikel beschriebenen Schritte ausführen zu können, müssen Administratoren mit PowerShell-Cmdlets vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="cbc7a-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="cbc7a-110">Sie sollten sich unbedingt vergewissern, dass Ihr SBC bereits gemäß der Empfehlung Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="cbc7a-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="cbc7a-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="cbc7a-112">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="cbc7a-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="cbc7a-113">Ribbon Communications-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="cbc7a-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="cbc7a-114">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="cbc7a-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="cbc7a-115">Sie können Ihr Microsoft-Telefonsystem konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und dann anhand der folgenden Vorgehensweisen Microsoft Teams als bevorzugten Anrufclient einrichten:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="cbc7a-116">Koppeln des SBC mit einem Microsoft-Telefonsystem und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="cbc7a-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="cbc7a-117">Aktivieren von Benutzern für den Direct Routing-Dienst</span><span class="sxs-lookup"><span data-stu-id="cbc7a-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="cbc7a-118">Sicherstellen, dass Microsoft Teams der bevorzugte Anrufclient für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="cbc7a-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="cbc7a-119">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="cbc7a-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="cbc7a-120">Nachstehend finden Sie die drei allgemeinen Schritte, mit denen Sie den SBC mit der Direct Routing-Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="cbc7a-121">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbc7a-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="cbc7a-122">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="cbc7a-122">Pair the SBC</span></span> 
- <span data-ttu-id="cbc7a-123">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="cbc7a-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="cbc7a-124">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbc7a-124">Connecting to Skype for Business Online by using Windows PowerShell</span></span> 

<span data-ttu-id="cbc7a-125">Sie können eine PowerShell-Sitzung verwenden, die mit dem Mandanten verbunden ist, um den SBC mit der Direct Routing-Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="cbc7a-126">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) aus.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="cbc7a-127">Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="cbc7a-128">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="cbc7a-129">Der Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="cbc7a-130">Koppeln des SBC an den Mandanten</span><span class="sxs-lookup"><span data-stu-id="cbc7a-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="cbc7a-131">Um den SBC mit dem Mandanten zu koppeln, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="cbc7a-132">Es wird dringend empfohlen, mithilfe der Informationen in der SBC-Dokumentation im SBC einen maximalen Anrufgrenzwert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="cbc7a-133">Der Grenzwert löst eine Benachrichtigung aus, wenn der SBC die Kapazität erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="cbc7a-134">Sie können den SBC nur dann koppeln, wenn der Domänenanteil des FQDN mit einer der Domänen übereinstimmt, die in Ihrem Mandanten registriert sind, mit Ausnahme von \*.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="cbc7a-135">Die Verwendung von \*.onmicrosoft.com-Domänennamen wird für FQDN-Namen des SBC nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="cbc7a-136">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="cbc7a-137">**contoso**.com</span><span class="sxs-lookup"><span data-stu-id="cbc7a-137">contoso.com</span></span><br/><span data-ttu-id="cbc7a-138">**contoso**.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cbc7a-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="cbc7a-139">Sie können den Namen „sbc.contoso.com“ für den SBC-Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="cbc7a-140">Wenn Sie versuchen, den SBC mit dem Namen „sbc.contoso.abc“ zu koppeln, lässt das System dies nicht zu, da diese Domäne nicht Eigentümer dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="cbc7a-141">Zusätzlich zu der Domäne, die in Ihrem Mandanten registriert ist, ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3- oder E5-Lizenz vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="cbc7a-142">Andernfalls wird folgender Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-142">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span><br/>
  <span data-ttu-id="cbc7a-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="cbc7a-144">Rückgabewerte:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="cbc7a-145">Während des Kopplungsprozesses können zusätzliche Optionen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="cbc7a-146">Im vorherigen Beispiel werden jedoch nur die minimal erforderlichen Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="cbc7a-147">In der folgenden Tabelle sind die zusätzlichen Parameter aufgelistet, die Sie zum Festlegen von Parametern für `New-CsOnlinePstnGateway` verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="cbc7a-148">Pflichtfeld?</span><span class="sxs-lookup"><span data-stu-id="cbc7a-148">Required</span></span>|<span data-ttu-id="cbc7a-149">Name</span><span class="sxs-lookup"><span data-stu-id="cbc7a-149">Name</span></span>|<span data-ttu-id="cbc7a-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbc7a-150">Description</span></span>|<span data-ttu-id="cbc7a-151">Standard</span><span class="sxs-lookup"><span data-stu-id="cbc7a-151">Default</span></span>|<span data-ttu-id="cbc7a-152">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="cbc7a-152">Possible values</span></span>|<span data-ttu-id="cbc7a-153">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="cbc7a-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbc7a-154">Ja</span><span class="sxs-lookup"><span data-stu-id="cbc7a-154">Yes</span></span>|<span data-ttu-id="cbc7a-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="cbc7a-155">FQDN</span></span>|<span data-ttu-id="cbc7a-156">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="cbc7a-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="cbc7a-157">Keiner</span><span class="sxs-lookup"><span data-stu-id="cbc7a-157">None</span></span>|<span data-ttu-id="cbc7a-158">NoneFQDN-Name, Begrenzung 63 Zeichen</span><span class="sxs-lookup"><span data-stu-id="cbc7a-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="cbc7a-159">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen in [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="cbc7a-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="cbc7a-160">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-160">No</span></span>|<span data-ttu-id="cbc7a-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="cbc7a-161">MediaBypass</span></span> |<span data-ttu-id="cbc7a-162">Der Parameter ist zur zukünftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-162">The parameter reserved for future use.</span></span> <span data-ttu-id="cbc7a-163">Der vom SBC angegebene Parameter unterstützt die Medienumgehung, und der Administrator möchte diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-163">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="cbc7a-164">Keiner</span><span class="sxs-lookup"><span data-stu-id="cbc7a-164">None</span></span>|<span data-ttu-id="cbc7a-165">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-165">True</span></span><br/><span data-ttu-id="cbc7a-166">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-166">False</span></span>|<span data-ttu-id="cbc7a-167">Boolesch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-167">Boolean</span></span>|
|<span data-ttu-id="cbc7a-168">Ja</span><span class="sxs-lookup"><span data-stu-id="cbc7a-168">Yes</span></span>|<span data-ttu-id="cbc7a-169">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="cbc7a-169">SipSignallingPort</span></span> |<span data-ttu-id="cbc7a-170">Überwachungsport für die Kommunikation mit Direct Routing-Diensten über das TLS-Protokoll (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-170">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="cbc7a-171">Keiner</span><span class="sxs-lookup"><span data-stu-id="cbc7a-171">None</span></span>|<span data-ttu-id="cbc7a-172">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="cbc7a-172">Any port</span></span>|<span data-ttu-id="cbc7a-173">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="cbc7a-173">0 to 65535</span></span> |
|<span data-ttu-id="cbc7a-174">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-174">No</span></span>|<span data-ttu-id="cbc7a-175">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="cbc7a-175">FailoverTimeSeconds</span></span> |<span data-ttu-id="cbc7a-176">Beim Standardwert „True“ werden ausgehende Anrufe, die nicht innerhalb von zehn Sekunden vom Gateway angenommen werden, an das nächste verfügbare Gateway weitergeleitet. Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch getrennt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-176">When set to True, outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="cbc7a-177">In einer Organisation mit langsamen Netzwerken und Gatewayreaktionen kann dies dazu führen, dass Anrufe unnötig getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-177">However, in an organization with slow networks and gateway responses, or when the process of establishing calls takes more than 10 seconds, this could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="cbc7a-178">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-178">The default value is True.</span></span>|<span data-ttu-id="cbc7a-179">10</span><span class="sxs-lookup"><span data-stu-id="cbc7a-179">10%</span></span>|<span data-ttu-id="cbc7a-180">Zahl</span><span class="sxs-lookup"><span data-stu-id="cbc7a-180">Number</span></span>|<span data-ttu-id="cbc7a-181">Int</span><span class="sxs-lookup"><span data-stu-id="cbc7a-181">int</span></span>|
|<span data-ttu-id="cbc7a-182">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-182">No</span></span>|<span data-ttu-id="cbc7a-183">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="cbc7a-183">ForwardCallHistory</span></span> |<span data-ttu-id="cbc7a-184">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-184">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="cbc7a-185">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Header: „History-info“ und „Referred-By“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-185">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="cbc7a-186">Der Standardwert ist **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-186">The default value is False ($False).</span></span> |<span data-ttu-id="cbc7a-187">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-187">False</span></span>|<span data-ttu-id="cbc7a-188">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-188">True</span></span><br/><span data-ttu-id="cbc7a-189">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-189">False</span></span>|<span data-ttu-id="cbc7a-190">Boolesch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-190">Boolean</span></span>|
|<span data-ttu-id="cbc7a-191">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-191">No</span></span>|<span data-ttu-id="cbc7a-192">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="cbc7a-192">ForwardPAI</span></span>|<span data-ttu-id="cbc7a-193">Gibt an, ob der P-Asserted-Identity (PAI)-Header zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-193">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="cbc7a-194">Der PAI-Header bietet eine Möglichkeit zum Überprüfen der Identität des Anrufers.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-194">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="cbc7a-195">Wenn diese Option aktiviert ist, wird auch der Header „Privacy:ID“ gesendet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-195">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="cbc7a-196">Der Standardwert ist **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-196">The default value is False ($False).</span></span>|<span data-ttu-id="cbc7a-197">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-197">False</span></span>|<span data-ttu-id="cbc7a-198">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-198">True</span></span><br/><span data-ttu-id="cbc7a-199">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-199">False</span></span>|<span data-ttu-id="cbc7a-200">Boolesch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-200">Boolean</span></span>|
|<span data-ttu-id="cbc7a-201">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-201">No</span></span>|<span data-ttu-id="cbc7a-202">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="cbc7a-202">SendSIPOptions</span></span> |<span data-ttu-id="cbc7a-203">Definiert, ob ein SBC die SIP-Optionen sendet oder nicht.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-203">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="cbc7a-204">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Benachrichtigungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-204">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="cbc7a-205">Es wird dringend empfohlen, dass Sie die SIP-Optionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-205">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="cbc7a-206">Der Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-206">Default value is TRUE.</span></span> |<span data-ttu-id="cbc7a-207">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-207">True</span></span>|<span data-ttu-id="cbc7a-208">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-208">True</span></span><br/><span data-ttu-id="cbc7a-209">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-209">False</span></span>|<span data-ttu-id="cbc7a-210">Boolesch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-210">Boolean</span></span>|
|<span data-ttu-id="cbc7a-211">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-211">No</span></span>|<span data-ttu-id="cbc7a-212">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="cbc7a-212">MaxConcurrentSessions</span></span> |<span data-ttu-id="cbc7a-213">Wird vom Benachrichtigungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-213">Used by alerting system.</span></span> <span data-ttu-id="cbc7a-214">Wenn ein Wert festgelegt ist, wird vom Benachrichtigungssystem eine Benachrichtigung an den Mandantenadministrator generiert, wenn die Anzahl der gleichzeitigen Sitzungen 90 % oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-214">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="cbc7a-215">Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-215">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="cbc7a-216">Das Überwachungssystem meldet jedoch alle 24 Stunden die Anzahl von gleichzeitigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-216">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="cbc7a-217">Null</span><span class="sxs-lookup"><span data-stu-id="cbc7a-217">Null</span></span>|<span data-ttu-id="cbc7a-218">Null</span><span class="sxs-lookup"><span data-stu-id="cbc7a-218">Null</span></span><br/><span data-ttu-id="cbc7a-219">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="cbc7a-219">1 to 100,000</span></span> ||
|<span data-ttu-id="cbc7a-220">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-220">No</span></span>|<span data-ttu-id="cbc7a-221">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="cbc7a-221">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="cbc7a-222">Hiermit können Sie den Pfad für Medien manuell auswählen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-222">Allows selecting path for media manually.</span></span> <span data-ttu-id="cbc7a-223">Beim direkten Routing wird ein Rechenzentrum für den Medienpfad zugewiesen, der auf der öffentlichen IP des SBC basiert.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-223">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="cbc7a-224">Wir wählen immer das dem SBC-Rechenzentrum nächstgelegene Rechenzentrum aus.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-224">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="cbc7a-225">In einigen Fällen kann eine öffentliche IP-Adresse, z. B. aus einem amerikanischen Bereich, einem SBC in Europa zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-225">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="cbc7a-226">In diesem Fall wird nicht der optimale Medienpfad verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-226">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="cbc7a-227">Dieser Parameter ermöglicht das manuelle Festlegen der bevorzugten Region für den Mediendatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-227">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="cbc7a-228">Es wird empfohlen, diesen Parameter nur festzulegen, wenn die Anrufprotokolle deutlich erkennen lassen, dass die automatische Zuordnung des Rechenzentrums für den Medienpfad dem SBC-Rechenzentrum nicht das nächstgelegene Rechenzentrum des SBC-Rechenzentrums ist.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-228">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="cbc7a-229">Keiner</span><span class="sxs-lookup"><span data-stu-id="cbc7a-229">None</span></span>|<span data-ttu-id="cbc7a-230">Ländercodes im ISO-Format</span><span class="sxs-lookup"><span data-stu-id="cbc7a-230">Country codes in ISO format</span></span>||
|<span data-ttu-id="cbc7a-231">Nein</span><span class="sxs-lookup"><span data-stu-id="cbc7a-231">No</span></span>|<span data-ttu-id="cbc7a-232">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="cbc7a-232">Enabled</span></span>|<span data-ttu-id="cbc7a-233">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-233">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="cbc7a-234">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird, oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-234">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="cbc7a-235">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-235">False</span></span>|<span data-ttu-id="cbc7a-236">Wahr</span><span class="sxs-lookup"><span data-stu-id="cbc7a-236">True</span></span><br/><span data-ttu-id="cbc7a-237">False</span><span class="sxs-lookup"><span data-stu-id="cbc7a-237">False</span></span>|<span data-ttu-id="cbc7a-238">Boolesch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-238">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="cbc7a-239">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="cbc7a-239">Verify the SBC pairing</span></span> 

<span data-ttu-id="cbc7a-240">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-240">Verify the connection:</span></span> 
- <span data-ttu-id="cbc7a-241">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-241">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="cbc7a-242">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-242">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="cbc7a-243">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet</span><span class="sxs-lookup"><span data-stu-id="cbc7a-243">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="cbc7a-244">Überprüfen Sie nach der Kopplung des SBC, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer PowerShell-Remotesitzung ausführen: `Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="cbc7a-244">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="cbc7a-245">Das gekoppelte Gateway sollte wie im Beispiel unten in der Liste angezeigt werden und überprüfen, dass für den Parameter *Aktiviert* der Wert **True** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-245">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="cbc7a-246">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-246">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="cbc7a-247">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-247">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="cbc7a-248">Überprüfen des SIP-Optionsflusses</span><span class="sxs-lookup"><span data-stu-id="cbc7a-248">Validate SIP Options flow</span></span> 

<span data-ttu-id="cbc7a-249">Um die Kopplung mithilfe ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SIP-Verwaltungsschnittstelle, und bestätigen Sie, dass der SBC „200 OK“-Antworten auf seine ausgehenden OPTIONS-Nachrichten empfängt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-249">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="cbc7a-250">Wenn das direkte Routing eingehende OPTIONS-Nachrichten sieht, sendet es ausgehende SIP-OPTIONS-Nachrichten an den SBC-FQDN, der im Headerfeld „Kontakt“ in der eingehenden OPTIONS-Nachricht konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-250">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="cbc7a-251">Verwenden Sie zum Überprüfen der Kopplung mithilfe der eingehenden SIP-Optionen die SBC-Verwaltungsoberfläche, und stellen Sie sicher, dass der SBC eine Antwort auf die OPTIONS-Nachrichten sendet, die von Direct Routing eintreffen, und dass der gesendete Antwortcode „200 OK“ lautet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-251">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="cbc7a-252">Aktivieren von Benutzern für den Direct Routing-Dienst</span><span class="sxs-lookup"><span data-stu-id="cbc7a-252">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="cbc7a-253">Führen Sie die folgenden Schritte aus, wenn Sie bereit sind, die Benutzer für den Direct Routing-Dienst zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-253">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="cbc7a-254">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystemlizenz zu.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-254">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="cbc7a-255">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-255">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="cbc7a-256">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-256">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="cbc7a-257">Konfigurieren Sie das VoIP-Routing.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-257">Configure voice routing.</span></span> <span data-ttu-id="cbc7a-258">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-258">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="cbc7a-259">Erstellen Sie einen Benutzer in Office 365, und weisen Sie die Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-259">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="cbc7a-260">Es gibt zwei Optionen für das Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-260">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="cbc7a-261">Es wird jedoch empfohlen, dass sich Ihre Organisation für eine Option entscheidet, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-261">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="cbc7a-262">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie den Benutzer mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-262">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="cbc7a-263">Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-263">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="cbc7a-264">Erstellen Sie den Benutzer direkt im Office 365-Administratorportal.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-264">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="cbc7a-265">Weitere Informationen finden Sie unter [Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-265">[Add users individually or in bulk to Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span></span> 

<span data-ttu-id="cbc7a-266">Wenn Ihre Skype for Business Online-Bereitstellung gemeinsam mit Skype for Business 2015 oder Lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer im lokalen Active Directory zu erstellen und ihn mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-266">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="cbc7a-267">Erforderliche Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-267">Required Licenses</span></span> 

- <span data-ttu-id="cbc7a-268">Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan 2 und Teams) + Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="cbc7a-268">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="cbc7a-269">Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan 2 und Teams) + Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="cbc7a-269">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="cbc7a-270">Optionale Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-270">Optional licenses:</span></span> 

- <span data-ttu-id="cbc7a-271">Anrufplan</span><span class="sxs-lookup"><span data-stu-id="cbc7a-271">Domestic Calling Plan</span></span> 
- <span data-ttu-id="cbc7a-272">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="cbc7a-272">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="cbc7a-273">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-273">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="cbc7a-274">Direct Routing setzt voraus, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-274">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="cbc7a-275">Sie können dies überprüfen, indem Sie sich den Parameter „RegistrarPool“ ansehen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-275">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="cbc7a-276">Er muss einen Wert in der Domäne „infra.lync.com“ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-276">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="cbc7a-277">Stellen Sie eine Verbindung zu Remote-PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-277">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="cbc7a-278">Geben Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-278">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="cbc7a-279">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-279">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="cbc7a-280">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, die Telefonnummer und die Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-280">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="cbc7a-281">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-281">This can be done in one step.</span></span> 

<span data-ttu-id="cbc7a-282">So fügen Sie die Telefonnummer hinzu und aktivieren diese für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-282">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="cbc7a-283">Stellen Sie eine Verbindung zu einer PowerShell-Sitzung her.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-283">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="cbc7a-284">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-284">Enter the following command: Enable-PSRemoting -force</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="cbc7a-285">Um beispielsweise eine Rufnummer für den Benutzer „Spencer Low“ hinzuzufügen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-285">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="cbc7a-286">Die verwendete Rufnummer muss als vollständige E.164-Rufnummer mit Ländervorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-286">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="cbc7a-287">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, können Sie die Telefonnummer des Benutzers mithilfe der lokalen Skype for Business-Verwaltungsshell oder über die Systemsteuerung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-287">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="cbc7a-288">Konfigurieren des VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="cbc7a-288">Configure Voice Routing</span></span> 

<span data-ttu-id="cbc7a-289">Das Microsoft-Telefonsystem verfügt über einen Routingmechanismus, der die Übermittlung eines Anrufs an einen bestimmten SBC basierend auf Folgendem ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-289">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="cbc7a-290">Muster der angerufenen Nummer</span><span class="sxs-lookup"><span data-stu-id="cbc7a-290">Called number pattern</span></span> 
- <span data-ttu-id="cbc7a-291">Muster der angerufenen Nummer + spezifischer Benutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="cbc7a-291">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="cbc7a-292">SBCs können als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-292">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="cbc7a-293">Dies bedeutet: Wenn der SBC, der für dieses Nummernmuster oder für dieses Nummernmuster und den spezifischen Benutzer als aktiv konfiguriert wurde, nicht verfügbar ist, werden die Anrufe an einen Backup-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-293">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="cbc7a-294">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-294">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="cbc7a-295">VoIP-Routingrichtlinie – Container für PSTN-Verwendungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="cbc7a-295">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="cbc7a-296">PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; kann in unterschiedlichen VoIP-Routing Richtlinien gemeinsam genutzt werden</span><span class="sxs-lookup"><span data-stu-id="cbc7a-296">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="cbc7a-297">VoIP-Routen – Nummernmuster und Gruppe von Online-PSTN-Gateways, die für Anrufe verwendet werden sollen, wenn die Anrufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="cbc7a-297">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="cbc7a-298">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert außerdem die Konfiguration, die angewendet wird, wenn der Anruf über den SBC platziert wird, z. B. "P-Asserted-Identity (PAI)" oder „bevorzugte Codecs“; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="cbc7a-298">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="cbc7a-299">Erstellen einer VoIP-Routingrichtlinie mit einer PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="cbc7a-299">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="cbc7a-300">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien im Anrufverlauf.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-300">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="cbc7a-301">**Anrufverlauf 1 (links):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an den SBC „sbc1.contoso.biz“ oder „sbc2.contoso.biz“ weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-301">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cbc7a-302">Wenn weder „sbc1.contoso.biz“ noch „sbc2.contoso.biz“ verfügbar ist, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-302">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="cbc7a-303">**Anrufverlauf 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an den SBC „sbc1.contoso.biz“ oder „sbc2.contoso.biz“ weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-303">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="cbc7a-304">Wenn einer der SBCs nicht verfügbar ist, wird die Route mit der niedrigeren Priorität versucht (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-304">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="cbc7a-305">Wenn keiner der SBCS verfügbar ist, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-305">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für die VoIP-Routingrichtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="cbc7a-307">In beiden Beispielen werden die SBCs in den Routen in zufälliger Reihenfolge versucht, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-307">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cbc7a-308">Sofern der Benutzer nicht auch eine Lizenz für den Microsoft-Anrufplan hat, werden Anrufe an eine beliebige Nummer (mit Ausnahme von Nummern, die den Mustern +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration entsprechen) getrennt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-308">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="cbc7a-309">Wenn der Benutzer über eine Anrufplanlizenz verfügt, wird der Anruf automatisch gemäß den Richtlinien des Microsoft-Anrufplans geleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-309">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="cbc7a-310">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Microsoft-Anrufplanlizenz, und es ist keine zusätzliche Konfiguration für das Anrufrouting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-310">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="cbc7a-311">In dem Beispiel in dem folgenden Diagramm wird eine VoIP-Route zum Senden von Anrufen an alle anderen US-amerikanischen und kanadischen Nummern hinzugefügt (Nummern, die dem Nummernmuster +1 XXX XXX XX XX entsprechen).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-311">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="cbc7a-313">Für alle anderen Anrufe wird (wenn ein Benutzer sowohl eine Lizenz für das Microsoft-Telefonsystem als auch für den Microsoft-Anrufplan hat) die automatische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-313">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="cbc7a-314">Wenn es keine Übereinstimmung mit Nummernmustern in den vom Administrator erstellten Online-VoIP-Routen gibt, erfolgt die Weiterleitung über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-314">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="cbc7a-315">Wenn der Benutzer nur das Microsoft-Telefonsystem hat, wird der Anruf getrennt, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-315">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cbc7a-316">In diesem Fall spielt der Prioritätswert für "Andere + 1" keine Rolle, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-316">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="cbc7a-317">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und weder „sbc5.contoso.biz“ noch „sbc6.contoso.biz“ verfügbar ist, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-317">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="cbc7a-318">Die folgende Tabelle enthält eine Zusammenfassung der Konfiguration mit drei VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-318">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="cbc7a-319">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="cbc7a-319">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="cbc7a-320">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-320">**PSTN usage**</span></span>|<span data-ttu-id="cbc7a-321">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-321">**Voice Route**</span></span>|<span data-ttu-id="cbc7a-322">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-322">**Number pattern**</span></span>|<span data-ttu-id="cbc7a-323">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-323">**Priority**</span></span>|<span data-ttu-id="cbc7a-324">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-324">**SBC**</span></span>|<span data-ttu-id="cbc7a-325">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-325">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbc7a-326">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-326">US only</span></span>|<span data-ttu-id="cbc7a-327">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-327">"Redmond 1"</span></span>|<span data-ttu-id="cbc7a-328">^\\+1(425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-328">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cbc7a-329">1</span><span class="sxs-lookup"><span data-stu-id="cbc7a-329">1</span></span>|<span data-ttu-id="cbc7a-330">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-330">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-331">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-331">sbc2.contoso.biz</span></span>|<span data-ttu-id="cbc7a-332">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cbc7a-332">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cbc7a-333">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-333">US only</span></span>|<span data-ttu-id="cbc7a-334">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-334">"Redmond 2"</span></span>|<span data-ttu-id="cbc7a-335">^\\+1(425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-335">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cbc7a-336">2</span><span class="sxs-lookup"><span data-stu-id="cbc7a-336">2</span></span>|<span data-ttu-id="cbc7a-337">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-337">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-338">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-338">sbc4.contoso.biz</span></span>|<span data-ttu-id="cbc7a-339">Backup-Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cbc7a-339">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cbc7a-340">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-340">US only</span></span>|<span data-ttu-id="cbc7a-341">"Andere +1"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-341">"Other +1"</span></span>|<span data-ttu-id="cbc7a-342">^\\+1(\d{10})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-342">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cbc7a-343">3</span><span class="sxs-lookup"><span data-stu-id="cbc7a-343">3</span></span>|<span data-ttu-id="cbc7a-344">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-344">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-345">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-345">sbc6.contoso.biz</span></span>|<span data-ttu-id="cbc7a-346">Route für angerufene Nummern +1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cbc7a-346">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="cbc7a-347">Alle Routen sind der PSTN-Verwendung „USA und Kanada“ zugeordnet, und die PSTN-Verwendung ist der VoIP-Routingrichtlinie „Nur USA“ zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-347">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="cbc7a-348">In diesem Beispiel wird die VoIP-Routingrichtlinie dem Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-348">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="cbc7a-349">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="cbc7a-349">Examples of call routes</span></span>

<span data-ttu-id="cbc7a-350">Im folgenden Beispiel wird gezeigt, wie Routen, PSTN-Verwendungen und Routingrichtlinien konfiguriert werden. Außerdem wird die Richtlinie dem Benutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-350">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="cbc7a-351">**Schritt 1:** Erstellen Sie die PSTN-Verwendung „USA und Kanada“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-351">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="cbc7a-352">Geben Sie in einer Skype for Business-PowerShell-Remotesitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-352">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="cbc7a-353">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-353">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="cbc7a-354">Dadurch wird eine Liste von Namen zurückgegeben, die möglicherweise abgeschnitten sind:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-354">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="cbc7a-355">Im nachstehenden Beispiel sehen Sie das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-355">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="cbc7a-356">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: „Redmond 1“, „Redmond 2“ und „Andere +1“, wie in der vorherigen Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-356">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="cbc7a-357">Zum Erstellen der Route „Redmond 1“ geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-357">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="cbc7a-358">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-358">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
<span data-ttu-id="cbc7a-359">Zum Erstellen der Route „Redmond 2“ geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-359">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cbc7a-360">Zum Erstellen der Route „Andere +1“ geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-360">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="cbc7a-361">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut einen gültigen Ausdruck darstellt.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-361">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="cbc7a-362">Sie können ihn auf dieser Website testen: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="cbc7a-362">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="cbc7a-363">In einigen Fällen müssen alle Anrufe an den gleichen SBC geleitet werden. Verwenden Sie in diesem Fall -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-363">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="cbc7a-364">Weiterleiten aller Anrufe an den gleichen SBC</span><span class="sxs-lookup"><span data-stu-id="cbc7a-364">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="cbc7a-365">Überprüfen Sie, ob Sie die Route korrekt konfiguriert haben, indem Sie den PowerShell-Befehl `Get-CSOnlineVoiceRoute` mithilfe der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-365">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="cbc7a-366">Dadurch sollte Folgendes zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-366">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="cbc7a-367">In diesem Beispiel wurde der Route "Andere + 1" automatisch die Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-367">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="cbc7a-368">**Schritt 3:** Erstellen Sie eine VoIP-Routingrichtlinie „Nur USA“, und fügen Sie der Richtlinie die PSTN-Verwendung „USA und Kanada“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-368">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="cbc7a-369">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-369">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="cbc7a-370">Das Ergebnis ist in diesem Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-370">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="cbc7a-371">**Schritt 4:** Gewähren Sie dem Benutzer Spencer Low mithilfe von PowerShell eine VoIP-Routingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-371">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="cbc7a-372">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-372">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="cbc7a-373">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-373">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="cbc7a-374">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-374">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="cbc7a-375">Erstellen einer VoIP-Routingrichtlinie mit mehreren PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="cbc7a-375">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="cbc7a-376">Die zuvor erstellte VoIP-Routingrichtlinie lässt nur Anrufe an Telefonnummern in den USA und Kanada zu – es sei denn, dem Benutzer wurde auch die Microsoft-Anrufplanlizenz zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-376">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="cbc7a-377">Im folgenden Beispiel können Sie die VoIP-Routingrichtlinie "Keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-377">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="cbc7a-378">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Verwendung „USA und Kanada“ sowie die neue PSTN-Verwendung „International“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-378">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="cbc7a-379">Dadurch werden alle anderen Anrufe an den SBCS „sbc2.contoso.biz“ und „sbc5.contoso.biz“ weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-379">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="cbc7a-380">In den gezeigten Beispielen wird dem Benutzer „Spencer Low“ die Richtlinie „Nur USA“ und dem Benutzer „John Woods die Richtlinie „Keine Einschränkungen“ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-380">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="cbc7a-381">Spencer Low – Es sind nur Anrufe an US-amerikanische und kanadische Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-381">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="cbc7a-382">Bei Anrufen an eine Nummer aus dem Redmond-Nummernbereich muss die spezifische Gruppe von SBCs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-382">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="cbc7a-383">Nicht US-Nummern werden nicht weitergeleitet, es sei denn, die Anrufplanlizenz ist dem Benutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-383">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="cbc7a-384">John Woods – Es sind Anrufe an beliebige Nummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-384">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="cbc7a-385">Bei Anrufen an eine Nummer aus dem Redmond-Nummernbereich muss die spezifische Gruppe von SBCs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-385">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="cbc7a-386">Nicht US-Nummern werden über „sbc2.contoso.biz“ und „sbc5.contoso.biz“ geleitet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-386">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die dem Benutzer Spencer Low zugewiesene VoIP-Routingrichtlinie](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="cbc7a-388">Für alle anderen Anrufe wird (wenn ein Benutzer sowohl eine Lizenz für das Microsoft-Telefonsystem als auch für den Microsoft-Anrufplan hat) die automatische Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-388">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="cbc7a-389">Wenn es keine Übereinstimmung mit Nummernmustern in den vom Administrator erstellten Online-VoIP-Routen gibt, erfolgt die Weiterleitung über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-389">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="cbc7a-390">Wenn der Benutzer nur das Microsoft-Telefonsystem hat, wird der Anruf getrennt, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-390">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer John Woods zugewiesene VoIP-Routingrichtlinie](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="cbc7a-392">Die folgende Tabelle enthält eine Zusammenfassung der Verwendungen der Routingrichtlinie „Keine Einschränkungen“ und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-392">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="cbc7a-393">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-393">**PSTN usage**</span></span>|<span data-ttu-id="cbc7a-394">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-394">**Voice Route**</span></span>|<span data-ttu-id="cbc7a-395">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-395">**Number pattern**</span></span>|<span data-ttu-id="cbc7a-396">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-396">**Priority**</span></span>|<span data-ttu-id="cbc7a-397">**SBC**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-397">**SBC**</span></span>|<span data-ttu-id="cbc7a-398">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cbc7a-398">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbc7a-399">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-399">US Only</span></span>|<span data-ttu-id="cbc7a-400">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-400">"Redmond 1"</span></span>|<span data-ttu-id="cbc7a-401">^\\+1(425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-401">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cbc7a-402">1</span><span class="sxs-lookup"><span data-stu-id="cbc7a-402">1</span></span>|<span data-ttu-id="cbc7a-403">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-403">sbc1.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-404">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-404">sbc2.contoso.biz</span></span>|<span data-ttu-id="cbc7a-405">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cbc7a-405">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cbc7a-406">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-406">US Only</span></span>|<span data-ttu-id="cbc7a-407">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-407">"Redmond 2"</span></span>|<span data-ttu-id="cbc7a-408">^\\+1(425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-408">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="cbc7a-409">2</span><span class="sxs-lookup"><span data-stu-id="cbc7a-409">2</span></span>|<span data-ttu-id="cbc7a-410">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-410">sbc3.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-411">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-411">sbc4.contoso.biz</span></span>|<span data-ttu-id="cbc7a-412">Backup-Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="cbc7a-412">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="cbc7a-413">Nur USA</span><span class="sxs-lookup"><span data-stu-id="cbc7a-413">US Only</span></span>|<span data-ttu-id="cbc7a-414">"Andere +1"</span><span class="sxs-lookup"><span data-stu-id="cbc7a-414">"Other +1"</span></span>|<span data-ttu-id="cbc7a-415">^\\+1(\d{10})$</span><span class="sxs-lookup"><span data-stu-id="cbc7a-415">^\\+1(\d{10})$</span></span>|<span data-ttu-id="cbc7a-416">3</span><span class="sxs-lookup"><span data-stu-id="cbc7a-416">3</span></span>|<span data-ttu-id="cbc7a-417">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-417">sbc5.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-418">sbc6>.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-418">sbc6>.contoso.biz</span></span>|<span data-ttu-id="cbc7a-419">Route für angerufene Nummern +1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="cbc7a-419">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="cbc7a-420">International</span><span class="sxs-lookup"><span data-stu-id="cbc7a-420">International</span></span>|<span data-ttu-id="cbc7a-421">International</span><span class="sxs-lookup"><span data-stu-id="cbc7a-421">International</span></span>|<span data-ttu-id="cbc7a-422">\d +</span><span class="sxs-lookup"><span data-stu-id="cbc7a-422">d.</span></span>|<span data-ttu-id="cbc7a-423">4</span><span class="sxs-lookup"><span data-stu-id="cbc7a-423">4</span></span>|<span data-ttu-id="cbc7a-424">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-424">sbc2.contoso.biz</span></span><br/><span data-ttu-id="cbc7a-425">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="cbc7a-425">sbc5.contoso.biz</span></span>|<span data-ttu-id="cbc7a-426">Route für ein beliebiges Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="cbc7a-426">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="cbc7a-427">Die Reihenfolge der PSTN-Verwendungen in VoIP-Routingrichtlinien ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-427">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="cbc7a-428">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn eine Übereinstimmung in der ersten Verwendung gefunden wird, werden keine anderen Verwendungen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-428">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="cbc7a-429">Die PSTN-Verwendung „International“ muss nach der PSTN-Nutzung „Nur USA“ platziert werden.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-429">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="cbc7a-430">Wenn Sie die Reihenfolge der PSTN-Verwendungen ändern möchten, führen Sie den Befehl `Set-CSOnlineVoiceRoutingPolicy` aus.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-430">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="cbc7a-431">Um beispielsweise die Reihenfolge von „USA und Kanada“ an erster Stelle und „International“ an zweiter Stelle umkehren möchten, führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-431">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="cbc7a-432">Die Priorität für die VoIP-Routen „Andere + 1“ und „International“ wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-432">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="cbc7a-433">Sie spielt keine Rolle, solange Sie niedrigere Prioritäten als „Redmond 1“ und „Redmond 2“ haben.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-433">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="cbc7a-434">Beispiel der dem Benutzer John Woods zugewiesene VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="cbc7a-434">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="cbc7a-435">Die Schritte zum Erstellen der PSTN-Verwendung „International“, der VoIP-Route „International“, der VoIP-Routingrichtlinie „Keine Einschränkungen“ und zum Zuweisen dieser Richtlinie zum Benutzer „John Woods“ sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-435">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="cbc7a-436">Erstellen Sie zuerst die PSTN-Verwendung „International“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-436">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="cbc7a-437">Geben Sie in einer PowerShell-Remotesitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-437">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="cbc7a-438">Erstellen Sie als nächstes die neue VoIP-Route „International“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-438">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="cbc7a-439">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-439">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. <span data-ttu-id="cbc7a-440">Als Nächstes erstellen Sie eine VoIP-Routingrichtlinie „Keine Einschränkungen“.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-440">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="cbc7a-441">Die PSTN-Verwendungen „Redmond 1“ und „Redmond“ werden in dieser VoIP-Routingrichtlinie wiederverwendet, um eine spezielle Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als lokale Anrufe beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-441">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="cbc7a-442">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-442">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="cbc7a-443">Weisen Sie dem Benutzer „John Woods“ mithilfe des folgenden Befehls die VoIP-Routingrichtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-443">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="cbc7a-444">Überprüfen Sie dann die Zuweisung mithilfe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-444">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="cbc7a-445">Dadurch wird Folgendes zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cbc7a-445">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="cbc7a-446">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wird, keine Einschränkungen aufweist und der Logik der Anrufweiterleitung folgt, die für USA, Kanada und internationale Gespräche verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-446">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="cbc7a-447">Ordnen Sie den Benutzern den Modus „Nur Teams“ zu, um sicherzustellen, dass Anrufe in Microsoft Teams eingehen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-447">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="cbc7a-448">Das direkte Routing erfordert, dass sich die Benutzer im Modus „Nur Teams“ befinden, um sicherzustellen, dass eingehende Anrufe im Team-Client eingehen.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-448">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="cbc7a-449">Um Benutzer im Modus „Nur Teams“ zu setzen, weisen Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="cbc7a-449">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="cbc7a-450">Falls Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel für Informationen zur Interoperabilität zwischen Skype und Teams: [Anleitung zur Migration und Interoperabilität für Unternehmen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="cbc7a-450">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="cbc7a-451">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbc7a-451">See also</span></span>

[<span data-ttu-id="cbc7a-452">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="cbc7a-452">Plan Direct Routing</span></span>](direct-routing-plan.md)
