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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: 86406af88648d367f02fd420c9ba278bdfd47185
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888594"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="24531-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="24531-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="24531-104">Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="24531-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="24531-105">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24531-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="24531-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24531-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="24531-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="24531-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="24531-108">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="24531-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="24531-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="24531-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="24531-110">Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="24531-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="24531-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="24531-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="24531-112">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="24531-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="24531-113">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="24531-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="24531-114">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="24531-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="24531-115">Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="24531-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="24531-116">Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="24531-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="24531-117">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="24531-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="24531-118">Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="24531-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="24531-119">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="24531-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="24531-120">Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="24531-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

1. <span data-ttu-id="24531-121">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="24531-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
2. <span data-ttu-id="24531-122">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="24531-122">Pair the SBC</span></span> 
3. <span data-ttu-id="24531-123">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="24531-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="24531-124">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="24531-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="24531-125">Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="24531-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="24531-126">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.</span><span class="sxs-lookup"><span data-stu-id="24531-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="24531-127">Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="24531-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="24531-128">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="24531-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="24531-129">Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="24531-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="24531-130">Koppeln des SBC mit dem Mandanten</span><span class="sxs-lookup"><span data-stu-id="24531-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="24531-131">Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="24531-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="24531-132">Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="24531-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="24531-133">Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="24531-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="24531-134">Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="24531-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="24531-135">Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24531-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="24531-136">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="24531-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="24531-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="24531-137">**contoso**.com</span></span><br/><span data-ttu-id="24531-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="24531-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="24531-139">Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="24531-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="24531-140">Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="24531-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="24531-141">Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="24531-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="24531-142">Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="24531-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="24531-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="24531-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="24531-144">Gibt</span><span class="sxs-lookup"><span data-stu-id="24531-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="24531-145">Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="24531-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="24531-146">Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24531-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="24531-147">In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie zum Festlegen von ```New-CsOnlinePstnGateway```Parametern für verwenden können.</span><span class="sxs-lookup"><span data-stu-id="24531-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="24531-148">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="24531-148">Required?</span></span>|<span data-ttu-id="24531-149">Name</span><span class="sxs-lookup"><span data-stu-id="24531-149">Name</span></span>|<span data-ttu-id="24531-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24531-150">Description</span></span>|<span data-ttu-id="24531-151">Standard</span><span class="sxs-lookup"><span data-stu-id="24531-151">Default</span></span>|<span data-ttu-id="24531-152">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="24531-152">Possible values</span></span>|<span data-ttu-id="24531-153">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="24531-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24531-154">Ja</span><span class="sxs-lookup"><span data-stu-id="24531-154">Yes</span></span>|<span data-ttu-id="24531-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="24531-155">FQDN</span></span>|<span data-ttu-id="24531-156">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="24531-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="24531-157">Keine</span><span class="sxs-lookup"><span data-stu-id="24531-157">None</span></span>|<span data-ttu-id="24531-158">NoneFQDN-Name, 63-Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="24531-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="24531-159">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="24531-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="24531-160">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-160">No</span></span>|<span data-ttu-id="24531-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="24531-161">MediaBypass</span></span> |<span data-ttu-id="24531-162">Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="24531-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="24531-163">Keine</span><span class="sxs-lookup"><span data-stu-id="24531-163">None</span></span>|<span data-ttu-id="24531-164">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-164">True</span></span><br/><span data-ttu-id="24531-165">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-165">False</span></span>|<span data-ttu-id="24531-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="24531-166">Boolean</span></span>|
|<span data-ttu-id="24531-167">Ja</span><span class="sxs-lookup"><span data-stu-id="24531-167">Yes</span></span>|<span data-ttu-id="24531-168">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="24531-168">SipSignalingPort</span></span> |<span data-ttu-id="24531-169">Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="24531-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="24531-170">Keine</span><span class="sxs-lookup"><span data-stu-id="24531-170">None</span></span>|<span data-ttu-id="24531-171">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="24531-171">Any port</span></span>|<span data-ttu-id="24531-172">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="24531-172">0 to 65535</span></span> |
|<span data-ttu-id="24531-173">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-173">No</span></span>|<span data-ttu-id="24531-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="24531-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="24531-175">Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="24531-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="24531-176">In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.</span><span class="sxs-lookup"><span data-stu-id="24531-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="24531-177">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="24531-177">The default value is 10.</span></span>|<span data-ttu-id="24531-178">10</span><span class="sxs-lookup"><span data-stu-id="24531-178">10</span></span>|<span data-ttu-id="24531-179">Nummer</span><span class="sxs-lookup"><span data-stu-id="24531-179">Number</span></span>|<span data-ttu-id="24531-180">Int</span><span class="sxs-lookup"><span data-stu-id="24531-180">Int</span></span>|
|<span data-ttu-id="24531-181">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-181">No</span></span>|<span data-ttu-id="24531-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="24531-182">ForwardCallHistory</span></span> |<span data-ttu-id="24531-183">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="24531-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="24531-184">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="24531-185">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="24531-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="24531-186">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-186">False</span></span>|<span data-ttu-id="24531-187">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-187">True</span></span><br/><span data-ttu-id="24531-188">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-188">False</span></span>|<span data-ttu-id="24531-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="24531-189">Boolean</span></span>|
|<span data-ttu-id="24531-190">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-190">No</span></span>|<span data-ttu-id="24531-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="24531-191">ForwardPAI</span></span>|<span data-ttu-id="24531-192">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="24531-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="24531-193">Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="24531-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="24531-194">Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="24531-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="24531-195">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="24531-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="24531-196">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-196">False</span></span>|<span data-ttu-id="24531-197">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-197">True</span></span><br/><span data-ttu-id="24531-198">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-198">False</span></span>|<span data-ttu-id="24531-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="24531-199">Boolean</span></span>|
|<span data-ttu-id="24531-200">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-200">No</span></span>|<span data-ttu-id="24531-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="24531-201">SendSIPOptions</span></span> |<span data-ttu-id="24531-202">Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24531-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="24531-203">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="24531-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="24531-204">Wir empfehlen dringend, SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="24531-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="24531-205">Der Standardwert ist **wahr**.</span><span class="sxs-lookup"><span data-stu-id="24531-205">Default value is **True**.</span></span> |<span data-ttu-id="24531-206">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-206">True</span></span>|<span data-ttu-id="24531-207">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-207">True</span></span><br/><span data-ttu-id="24531-208">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-208">False</span></span>|<span data-ttu-id="24531-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="24531-209">Boolean</span></span>|
|<span data-ttu-id="24531-210">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-210">No</span></span>|<span data-ttu-id="24531-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="24531-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="24531-212">Wird vom Warnungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="24531-212">Used by alerting system.</span></span> <span data-ttu-id="24531-213">Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="24531-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="24531-214">Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="24531-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="24531-215">Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="24531-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="24531-216">NULL</span><span class="sxs-lookup"><span data-stu-id="24531-216">Null</span></span>|<span data-ttu-id="24531-217">NULL</span><span class="sxs-lookup"><span data-stu-id="24531-217">Null</span></span><br/><span data-ttu-id="24531-218">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="24531-218">1 to 100,000</span></span> ||
|<span data-ttu-id="24531-219">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-219">No</span></span>|<span data-ttu-id="24531-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="24531-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="24531-221">Ermöglicht das manuelle auswählen von Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="24531-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="24531-222">Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="24531-223">Wir wählen immer am nächsten zum SBC-Rechenzentrum aus.</span><span class="sxs-lookup"><span data-stu-id="24531-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="24531-224">In einigen Fällen kann eine öffentliche IP-Adresse beispielsweise aus dem US-Bereich einem SBC in Europa zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="24531-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="24531-225">In diesem Fall wird kein optimaler Medienpfad verwendet.</span><span class="sxs-lookup"><span data-stu-id="24531-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="24531-226">Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="24531-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="24531-227">Wir empfehlen, diesen Parameter nur dann festzulegen, wenn die Anrufprotokolle eindeutig darauf hinweisen, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="24531-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="24531-228">Keine</span><span class="sxs-lookup"><span data-stu-id="24531-228">None</span></span>|<span data-ttu-id="24531-229">Landesvorwahl im ISO-Format</span><span class="sxs-lookup"><span data-stu-id="24531-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="24531-230">Nein</span><span class="sxs-lookup"><span data-stu-id="24531-230">No</span></span>|<span data-ttu-id="24531-231">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="24531-231">Enabled</span></span>|<span data-ttu-id="24531-232">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="24531-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="24531-233">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="24531-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="24531-234">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-234">False</span></span>|<span data-ttu-id="24531-235">Wahr</span><span class="sxs-lookup"><span data-stu-id="24531-235">True</span></span><br/><span data-ttu-id="24531-236">Falsch</span><span class="sxs-lookup"><span data-stu-id="24531-236">False</span></span>|<span data-ttu-id="24531-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="24531-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="24531-238">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="24531-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="24531-239">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="24531-239">Verify the connection:</span></span> 
- <span data-ttu-id="24531-240">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.</span><span class="sxs-lookup"><span data-stu-id="24531-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="24531-241">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="24531-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="24531-242">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet</span><span class="sxs-lookup"><span data-stu-id="24531-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="24531-243">Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="24531-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="24531-244">Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter **Enabled** den Wert **true**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="24531-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="24531-245">Eingeben</span><span class="sxs-lookup"><span data-stu-id="24531-245">Enter:</span></span>

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="24531-246">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-246">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="24531-247">Überprüfen des SIP-Options Flusses</span><span class="sxs-lookup"><span data-stu-id="24531-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="24531-248">Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.</span><span class="sxs-lookup"><span data-stu-id="24531-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="24531-249">Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="24531-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="24531-250">Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="24531-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="24531-251">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="24531-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="24531-252">Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24531-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="24531-253">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="24531-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="24531-254">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="24531-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="24531-255">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="24531-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="24531-256">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="24531-256">Configure voice routing.</span></span> <span data-ttu-id="24531-257">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="24531-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="24531-258">Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="24531-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="24531-259">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="24531-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="24531-260">Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="24531-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="24531-261">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="24531-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="24531-262">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="24531-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="24531-263">Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal.</span><span class="sxs-lookup"><span data-stu-id="24531-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="24531-264">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="24531-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="24531-265">Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="24531-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="24531-266">Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen des direkten Routings](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="24531-266">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="24531-267">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="24531-267">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="24531-268">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="24531-268">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="24531-269">Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten.</span><span class="sxs-lookup"><span data-stu-id="24531-269">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="24531-270">Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="24531-270">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="24531-271">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="24531-271">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="24531-272">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="24531-272">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="24531-273">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="24531-273">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="24531-274">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24531-274">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="24531-275">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="24531-275">This can be done in one step.</span></span> 

<span data-ttu-id="24531-276">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="24531-276">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="24531-277">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="24531-277">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="24531-278">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="24531-278">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="24531-279">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-279">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="24531-280">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="24531-280">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="24531-281">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24531-281">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="24531-282">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="24531-282">Configure Voice Routing</span></span> 

<span data-ttu-id="24531-283">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="24531-283">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="24531-284">Als Zahlenmuster bezeichnet</span><span class="sxs-lookup"><span data-stu-id="24531-284">Called number pattern</span></span> 
- <span data-ttu-id="24531-285">Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="24531-285">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="24531-286">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="24531-286">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="24531-287">Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-287">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="24531-288">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="24531-288">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="24531-289">VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="24531-289">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="24531-290">PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="24531-290">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="24531-291">VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="24531-291">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="24531-292">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="24531-292">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="24531-293">Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="24531-293">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="24531-294">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="24531-294">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="24531-295">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-295">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="24531-296">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="24531-296">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="24531-297">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-297">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="24531-298">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="24531-298">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="24531-299">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="24531-299">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="24531-301">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="24531-301">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="24531-302">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="24531-302">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="24531-303">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-303">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="24531-304">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="24531-304">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="24531-305">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="24531-305">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="24531-307">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="24531-307">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="24531-308">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="24531-308">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="24531-309">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="24531-309">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="24531-310">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="24531-310">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="24531-311">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="24531-311">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="24531-312">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="24531-312">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="24531-313">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="24531-313">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="24531-314">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="24531-314">**PSTN usage**</span></span>|<span data-ttu-id="24531-315">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="24531-315">**Voice route**</span></span>|<span data-ttu-id="24531-316">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="24531-316">**Number pattern**</span></span>|<span data-ttu-id="24531-317">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="24531-317">**Priority**</span></span>|<span data-ttu-id="24531-318">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="24531-318">**SBC**</span></span>|<span data-ttu-id="24531-319">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="24531-319">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24531-320">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-320">US only</span></span>|<span data-ttu-id="24531-321">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="24531-321">"Redmond 1"</span></span>|<span data-ttu-id="24531-322">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="24531-322">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="24531-323">1</span><span class="sxs-lookup"><span data-stu-id="24531-323">1</span></span>|<span data-ttu-id="24531-324">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-324">sbc1.contoso.biz</span></span><br/><span data-ttu-id="24531-325">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-325">sbc2.contoso.biz</span></span>|<span data-ttu-id="24531-326">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="24531-326">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="24531-327">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-327">US only</span></span>|<span data-ttu-id="24531-328">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="24531-328">"Redmond 2"</span></span>|<span data-ttu-id="24531-329">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="24531-329">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="24531-330">2</span><span class="sxs-lookup"><span data-stu-id="24531-330">2</span></span>|<span data-ttu-id="24531-331">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-331">sbc3.contoso.biz</span></span><br/><span data-ttu-id="24531-332">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-332">sbc4.contoso.biz</span></span>|<span data-ttu-id="24531-333">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="24531-333">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="24531-334">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-334">US only</span></span>|<span data-ttu-id="24531-335">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="24531-335">"Other +1"</span></span>|<span data-ttu-id="24531-336">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="24531-336">^\\+1(\d{10})$</span></span>|<span data-ttu-id="24531-337">3</span><span class="sxs-lookup"><span data-stu-id="24531-337">3</span></span>|<span data-ttu-id="24531-338">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-338">sbc5.contoso.biz</span></span><br/><span data-ttu-id="24531-339">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-339">sbc6.contoso.biz</span></span>|<span data-ttu-id="24531-340">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="24531-340">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="24531-341">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="24531-341">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="24531-342">In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-342">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="24531-343">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="24531-343">Examples of call routes</span></span>

<span data-ttu-id="24531-344">Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="24531-344">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="24531-345">**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="24531-345">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="24531-346">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-346">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="24531-347">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="24531-347">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="24531-348">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="24531-348">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="24531-349">Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24531-349">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

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

<span data-ttu-id="24531-350">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24531-350">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="24531-351">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-351">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="24531-352">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-352">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="24531-353">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-353">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="24531-354">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-354">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="24531-355">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="24531-355">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="24531-356">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="24531-356">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="24531-357">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="24531-357">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="24531-358">Alle Anrufe an denselben SBC weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="24531-358">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="24531-359">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="24531-359">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="24531-360">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="24531-360">Which should return:</span></span>
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

<span data-ttu-id="24531-361">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-361">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="24531-362">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="24531-362">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="24531-363">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-363">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="24531-364">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="24531-364">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="24531-365">**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24531-365">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="24531-366">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-366">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="24531-367">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="24531-367">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="24531-368">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-368">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="24531-369">Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="24531-369">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="24531-370">Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-370">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="24531-371">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="24531-371">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="24531-372">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="24531-372">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="24531-373">Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-373">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="24531-374">In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="24531-374">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="24531-375">Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="24531-375">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="24531-376">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24531-376">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="24531-377">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-377">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="24531-378">John Woods – Anrufe an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="24531-378">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="24531-379">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24531-379">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="24531-380">Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-380">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="24531-382">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="24531-382">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="24531-383">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="24531-383">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="24531-384">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="24531-384">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="24531-386">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="24531-386">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="24531-387">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="24531-387">**PSTN usage**</span></span>|<span data-ttu-id="24531-388">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="24531-388">**Voice route**</span></span>|<span data-ttu-id="24531-389">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="24531-389">**Number pattern**</span></span>|<span data-ttu-id="24531-390">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="24531-390">**Priority**</span></span>|<span data-ttu-id="24531-391">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="24531-391">**SBC**</span></span>|<span data-ttu-id="24531-392">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="24531-392">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24531-393">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-393">US Only</span></span>|<span data-ttu-id="24531-394">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="24531-394">"Redmond 1"</span></span>|<span data-ttu-id="24531-395">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="24531-395">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="24531-396">1</span><span class="sxs-lookup"><span data-stu-id="24531-396">1</span></span>|<span data-ttu-id="24531-397">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-397">sbc1.contoso.biz</span></span><br/><span data-ttu-id="24531-398">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-398">sbc2.contoso.biz</span></span>|<span data-ttu-id="24531-399">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="24531-399">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="24531-400">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-400">US Only</span></span>|<span data-ttu-id="24531-401">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="24531-401">"Redmond 2"</span></span>|<span data-ttu-id="24531-402">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="24531-402">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="24531-403">2</span><span class="sxs-lookup"><span data-stu-id="24531-403">2</span></span>|<span data-ttu-id="24531-404">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-404">sbc3.contoso.biz</span></span><br/><span data-ttu-id="24531-405">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-405">sbc4.contoso.biz</span></span>|<span data-ttu-id="24531-406">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="24531-406">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="24531-407">Nur USA</span><span class="sxs-lookup"><span data-stu-id="24531-407">US Only</span></span>|<span data-ttu-id="24531-408">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="24531-408">"Other +1"</span></span>|<span data-ttu-id="24531-409">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="24531-409">^\\+1(\d{10})$</span></span>|<span data-ttu-id="24531-410">3</span><span class="sxs-lookup"><span data-stu-id="24531-410">3</span></span>|<span data-ttu-id="24531-411">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-411">sbc5.contoso.biz</span></span><br/><span data-ttu-id="24531-412">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-412">sbc6>.contoso.biz</span></span>|<span data-ttu-id="24531-413">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="24531-413">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="24531-414">International</span><span class="sxs-lookup"><span data-stu-id="24531-414">International</span></span>|<span data-ttu-id="24531-415">International</span><span class="sxs-lookup"><span data-stu-id="24531-415">International</span></span>|<span data-ttu-id="24531-416">\d +</span><span class="sxs-lookup"><span data-stu-id="24531-416">\d+</span></span>|<span data-ttu-id="24531-417">4</span><span class="sxs-lookup"><span data-stu-id="24531-417">4</span></span>|<span data-ttu-id="24531-418">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-418">sbc2.contoso.biz</span></span><br/><span data-ttu-id="24531-419">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="24531-419">sbc5.contoso.biz</span></span>|<span data-ttu-id="24531-420">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="24531-420">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="24531-421">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="24531-421">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="24531-422">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="24531-422">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="24531-423">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="24531-423">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="24531-424">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="24531-424">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="24531-425">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="24531-425">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="24531-426">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="24531-426">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="24531-427">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="24531-427">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="24531-428">Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="24531-428">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="24531-429">Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="24531-429">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>   


<span data-ttu-id="24531-430">**Schritt 1**: Erstellen der PSTN-Nutzung "International"</span><span class="sxs-lookup"><span data-stu-id="24531-430">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="24531-431">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="24531-431">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="24531-432">**Schritt 2**: Erstellen der neuen VoIP-Route "International"</span><span class="sxs-lookup"><span data-stu-id="24531-432">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="24531-433">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-433">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="24531-434">**Schritt 3**: Erstellen einer VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="24531-434">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="24531-435">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="24531-435">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="24531-436">Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:</span><span class="sxs-lookup"><span data-stu-id="24531-436">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="24531-437">a.</span><span class="sxs-lookup"><span data-stu-id="24531-437">a.</span></span> <span data-ttu-id="24531-438">Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="24531-438">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="24531-439">Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="24531-439">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="24531-440">b.</span><span class="sxs-lookup"><span data-stu-id="24531-440">b.</span></span> <span data-ttu-id="24531-441">Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="24531-441">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="24531-442">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="24531-442">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="24531-443">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-443">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="24531-444">**Schritt 4**: weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="24531-444">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="24531-445">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="24531-445">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="24531-446">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="24531-446">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="24531-447">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="24531-447">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="24531-448">Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen</span><span class="sxs-lookup"><span data-stu-id="24531-448">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="24531-449">Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen.</span><span class="sxs-lookup"><span data-stu-id="24531-449">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="24531-450">Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="24531-450">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="24531-451">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel zur Interoperabilität von Informationen zwischen Skype und Teams: [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business nutzen](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="24531-451">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="24531-452">Konfigurieren des direkten Sendens von Anrufen an Voicemail</span><span class="sxs-lookup"><span data-stu-id="24531-452">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="24531-453">Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden.</span><span class="sxs-lookup"><span data-stu-id="24531-453">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="24531-454">Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an.</span><span class="sxs-lookup"><span data-stu-id="24531-454">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="24531-455">Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail".</span><span class="sxs-lookup"><span data-stu-id="24531-455">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="24531-456">In diesem Fall erhält der Nutzer der Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit dem Anrufbeantworter des Benutzers verbunden.</span><span class="sxs-lookup"><span data-stu-id="24531-456">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="24531-457">Übersetzen von Rufnummern für Anrufer und Anrufer für ausgehende und eingehende Anrufe in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="24531-457">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="24531-458">Manchmal möchten mandantenadministratoren die Anrufer-oder Rufnummernanzeige für ausgehende und/oder eingehende Anrufe basierend auf den von Ihnen erstellten Mustern ändern, um die Interoperabilität mit SBCS zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="24531-458">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="24531-459">Sie können eine Richtlinie für die Übersetzungsregeln festlegen, um die Anrufer-oder Rufnummernanzeige in ein alternatives Format zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="24531-459">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="24531-460">Sie können die Richtlinie verwenden, um Zahlen für Folgendes zu übersetzen:</span><span class="sxs-lookup"><span data-stu-id="24531-460">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="24531-461">Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams-Client (angerufener).</span><span class="sxs-lookup"><span data-stu-id="24531-461">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="24531-462">Ausgehende Anrufe: Anrufe von einem Team-Client (Anrufer) an einen PSTN-Endpunkt (angerufener).</span><span class="sxs-lookup"><span data-stu-id="24531-462">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="24531-463">Die Richtlinie wird auf der SBC-Ebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="24531-463">The policy is applied at the SBC level.</span></span> <span data-ttu-id="24531-464">Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der Sie angezeigt werden, wenn Sie Sie in PowerShell auflisten.</span><span class="sxs-lookup"><span data-stu-id="24531-464">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="24531-465">Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="24531-465">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="24531-466">Zum Erstellen, ändern, anzeigen und Löschen von Regeln für die Nummern Manipulation verwenden Sie die Cmdlets [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Sets-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)und [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .</span><span class="sxs-lookup"><span data-stu-id="24531-466">To create, modify, view, and delete number manipulation rules, use the [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule), and [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlets.</span></span>

<span data-ttu-id="24531-467">Zum zuweisen, konfigurieren und Auflisten von Regeln für die Nummern Manipulation auf SBCS verwenden Sie die Cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) und [setCSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) zusammen ```InboundPSTNNumberTranslationRules```mit ```OutboundTeamsNumberTranslationRules```den ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList``` ```InboundTeamsNumberTranslationRules```,,,,, ```OutboundPSTNNumberTranslationRulesList``` ,, und Parametern.</span><span class="sxs-lookup"><span data-stu-id="24531-467">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="24531-468">Beispiele</span><span class="sxs-lookup"><span data-stu-id="24531-468">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="24531-469">Beispiel-SBC-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="24531-469">Example SBC configuration</span></span>

<span data-ttu-id="24531-470">In den Beispielszenarien führen wir das ```New-CsOnlinePSTNGateway``` Cmdlet aus, um die folgende SBC-Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24531-470">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="24531-471">Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="24531-471">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="24531-472">Name</span><span class="sxs-lookup"><span data-stu-id="24531-472">Name</span></span>  |<span data-ttu-id="24531-473">Muster</span><span class="sxs-lookup"><span data-stu-id="24531-473">Pattern</span></span> |<span data-ttu-id="24531-474">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="24531-474">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="24531-475">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="24531-475">AddPlus1</span></span>     |<span data-ttu-id="24531-476">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="24531-476">^(\d{10})$</span></span>          |<span data-ttu-id="24531-477">+1$1</span><span class="sxs-lookup"><span data-stu-id="24531-477">+1$1</span></span>          |
|<span data-ttu-id="24531-478">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="24531-478">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="24531-479">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="24531-479">^(\d{4})$</span></span>          | <span data-ttu-id="24531-480">+ 1206555 $1</span><span class="sxs-lookup"><span data-stu-id="24531-480">+1206555$1</span></span>         |
|<span data-ttu-id="24531-481">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="24531-481">AddSeattleAreaCode</span></span>    |<span data-ttu-id="24531-482">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="24531-482">^(\d{4})$</span></span>          | <span data-ttu-id="24531-483">425555 $1</span><span class="sxs-lookup"><span data-stu-id="24531-483">425555$1</span></span>         |
|<span data-ttu-id="24531-484">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="24531-484">StripPlus1</span></span>    |<span data-ttu-id="24531-485">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="24531-485">^+1(\d{10})$</span></span>          | <span data-ttu-id="24531-486">$1</span><span class="sxs-lookup"><span data-stu-id="24531-486">$1</span></span>         |

<span data-ttu-id="24531-487">In diesen Beispielszenarien haben wir zwei Benutzer, Alice und Bob.</span><span class="sxs-lookup"><span data-stu-id="24531-487">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="24531-488">Alice ist ein Team Benutzer und Ihre Nummer ist + 1 206 555 0100.</span><span class="sxs-lookup"><span data-stu-id="24531-488">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="24531-489">Bob ist ein PSTN-Benutzer und seine Nummer ist + 1 425 555 0100.</span><span class="sxs-lookup"><span data-stu-id="24531-489">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="24531-490">Beispiel 1: eingehender Anruf an eine zehnstellige Zahl</span><span class="sxs-lookup"><span data-stu-id="24531-490">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="24531-491">Bob ruft Alice mit einer nicht-E. 164-zehnstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="24531-491">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="24531-492">Bob wählt 2065550100, um Alice zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24531-492">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="24531-493">SBC verwendet 2065550100 in den RequestURI und den Headern und 4255550100 im from-Header.</span><span class="sxs-lookup"><span data-stu-id="24531-493">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="24531-494">Header</span><span class="sxs-lookup"><span data-stu-id="24531-494">Header</span></span>  |<span data-ttu-id="24531-495">Original</span><span class="sxs-lookup"><span data-stu-id="24531-495">Original</span></span> |<span data-ttu-id="24531-496">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="24531-496">Translated header</span></span> |<span data-ttu-id="24531-497">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="24531-497">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="24531-498">RequestURI</span><span class="sxs-lookup"><span data-stu-id="24531-498">RequestURI</span></span>  |<span data-ttu-id="24531-499">Einladen von SIP:2065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-499">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="24531-500">Einladen von SIP:+12065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-500">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="24531-501">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-501">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="24531-502">An</span><span class="sxs-lookup"><span data-stu-id="24531-502">TO</span></span>    |<span data-ttu-id="24531-503">An: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-503">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-504">An: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-504">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-505">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-505">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="24531-506">Von</span><span class="sxs-lookup"><span data-stu-id="24531-506">FROM</span></span>   |<span data-ttu-id="24531-507">Von: \<SIP:4255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-507">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-508">Von: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-508">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-509">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-509">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="24531-510">Beispiel 2: eingehende Anrufe an eine vierstellige Zahl</span><span class="sxs-lookup"><span data-stu-id="24531-510">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="24531-511">Bob ruft Alice mit einer vierstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="24531-511">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="24531-512">Bob wählt 0100, um Alice zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24531-512">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="24531-513">SBC verwendet 0100 in den RequestURI und den Headern und 4255550100 im from-Header.</span><span class="sxs-lookup"><span data-stu-id="24531-513">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="24531-514">Header</span><span class="sxs-lookup"><span data-stu-id="24531-514">Header</span></span>  |<span data-ttu-id="24531-515">Original</span><span class="sxs-lookup"><span data-stu-id="24531-515">Original</span></span> |<span data-ttu-id="24531-516">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="24531-516">Translated header</span></span> |<span data-ttu-id="24531-517">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="24531-517">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="24531-518">RequestURI</span><span class="sxs-lookup"><span data-stu-id="24531-518">RequestURI</span></span>  |<span data-ttu-id="24531-519">Einladen von SIP:0100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-519">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="24531-520">Einladen von SIP:+12065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-520">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="24531-521">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="24531-521">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="24531-522">An</span><span class="sxs-lookup"><span data-stu-id="24531-522">TO</span></span>    |<span data-ttu-id="24531-523">An: \<SIP:0100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-523">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-524">An: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-524">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-525">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="24531-525">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="24531-526">Von</span><span class="sxs-lookup"><span data-stu-id="24531-526">FROM</span></span>   |<span data-ttu-id="24531-527">Von: \<SIP:4255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-527">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-528">Von: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-528">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-529">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-529">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="24531-530">Beispiel 3: ausgehender Anruf mit einer zehnstelligen nicht-E. 164-Nummer</span><span class="sxs-lookup"><span data-stu-id="24531-530">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="24531-531">Alice ruft Bob mit einer zehnstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="24531-531">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="24531-532">Alice wählt 425 555 0100, um Bob zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24531-532">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="24531-533">SBC ist für die Verwendung von nicht-E. 164-Nummern für Teams und PSTN-Benutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="24531-533">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="24531-534">In diesem Szenario übersetzt ein Wählplan die Nummer vor dem Senden an die direkte Routing Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="24531-534">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="24531-535">Wenn Alice in den Teams-Client 425 555 0100 eingibt, wird die Nummer im Länder Wählplan in + 14255550100 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="24531-535">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="24531-536">Bei den resultierenden Zahlen handelt es sich um eine kumulative Normalisierung der Wähl Plan Regeln und der Übersetzungsregeln für Teams.</span><span class="sxs-lookup"><span data-stu-id="24531-536">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="24531-537">Die Übersetzungsregeln für Teams entfernen das "+ 1", das vom Wählplan hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="24531-537">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="24531-538">Header</span><span class="sxs-lookup"><span data-stu-id="24531-538">Header</span></span>  |<span data-ttu-id="24531-539">Original</span><span class="sxs-lookup"><span data-stu-id="24531-539">Original</span></span> |<span data-ttu-id="24531-540">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="24531-540">Translated header</span></span> |<span data-ttu-id="24531-541">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="24531-541">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="24531-542">RequestURI</span><span class="sxs-lookup"><span data-stu-id="24531-542">RequestURI</span></span>  |<span data-ttu-id="24531-543">Einladen von SIP:+14255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-543">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="24531-544">Einladen von SIP:4255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-544">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="24531-545">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-545">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="24531-546">An</span><span class="sxs-lookup"><span data-stu-id="24531-546">TO</span></span>    |<span data-ttu-id="24531-547">An: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-547">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-548">An: \<SIP:4255555555@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-548">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="24531-549">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-549">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="24531-550">Von</span><span class="sxs-lookup"><span data-stu-id="24531-550">FROM</span></span>   |<span data-ttu-id="24531-551">Von: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-551">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-552">Von: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-552">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-553">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-553">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="24531-554">Beispiel 4: Outbound-Anruf mit einer vierstelligen nicht-E. 164-Nummer</span><span class="sxs-lookup"><span data-stu-id="24531-554">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="24531-555">Alice ruft Bob mit einer vierstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="24531-555">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="24531-556">Alice verwendet 0100, um Bob von anrufen oder über einen Kontakt zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="24531-556">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="24531-557">SBC ist für die Verwendung von nicht-E. 164-vierstelligen Zahlen für Teams-Benutzer und zehnstellige Zahlen für PSTN-Benutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="24531-557">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="24531-558">In diesem Szenario wird der Wählplan nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="24531-558">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="24531-559">Header</span><span class="sxs-lookup"><span data-stu-id="24531-559">Header</span></span>  |<span data-ttu-id="24531-560">Original</span><span class="sxs-lookup"><span data-stu-id="24531-560">Original</span></span> |<span data-ttu-id="24531-561">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="24531-561">Translated header</span></span> |<span data-ttu-id="24531-562">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="24531-562">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="24531-563">RequestURI</span><span class="sxs-lookup"><span data-stu-id="24531-563">RequestURI</span></span>  |<span data-ttu-id="24531-564">Einladen von SIP:0100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-564">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="24531-565">Einladen von SIP:4255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="24531-565">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="24531-566">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="24531-566">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="24531-567">An</span><span class="sxs-lookup"><span data-stu-id="24531-567">TO</span></span>    |<span data-ttu-id="24531-568">An: \<SIP:0100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-568">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-569">An: \<SIP:4255555555@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-569">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="24531-570">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="24531-570">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="24531-571">Von</span><span class="sxs-lookup"><span data-stu-id="24531-571">FROM</span></span>   |<span data-ttu-id="24531-572">Von: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-572">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="24531-573">Von: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="24531-573">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="24531-574">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="24531-574">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="24531-575">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24531-575">See also</span></span>

[<span data-ttu-id="24531-576">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="24531-576">Plan Direct Routing</span></span>](direct-routing-plan.md)
