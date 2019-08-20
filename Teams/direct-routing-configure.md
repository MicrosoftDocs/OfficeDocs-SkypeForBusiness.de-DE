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
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: 4013e0fd914630f154f407ad9c70e2c6915723f5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464611"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="76792-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="76792-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="76792-104">Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="76792-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="76792-105">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76792-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="76792-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76792-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="76792-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="76792-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="76792-108">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="76792-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="76792-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="76792-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="76792-110">Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="76792-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="76792-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="76792-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="76792-112">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="76792-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="76792-113">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="76792-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="76792-114">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="76792-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="76792-115">Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="76792-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="76792-116">Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="76792-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="76792-117">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="76792-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="76792-118">Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="76792-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="76792-119">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="76792-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="76792-120">Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="76792-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="76792-121">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="76792-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="76792-122">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="76792-122">Pair the SBC</span></span> 
- <span data-ttu-id="76792-123">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="76792-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="76792-124">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="76792-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="76792-125">Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="76792-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="76792-126">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.</span><span class="sxs-lookup"><span data-stu-id="76792-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="76792-127">Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="76792-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="76792-128">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="76792-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="76792-129">Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="76792-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="76792-130">Koppeln des SBC mit dem Mandanten</span><span class="sxs-lookup"><span data-stu-id="76792-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="76792-131">Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="76792-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="76792-132">Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="76792-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="76792-133">Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="76792-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="76792-134">Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="76792-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="76792-135">Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="76792-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="76792-136">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="76792-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="76792-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="76792-137">**contoso**.com</span></span><br/><span data-ttu-id="76792-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="76792-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="76792-139">Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="76792-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="76792-140">Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="76792-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="76792-141">Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="76792-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="76792-142">Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="76792-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="76792-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="76792-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="76792-144">Gibt</span><span class="sxs-lookup"><span data-stu-id="76792-144">Returns:</span></span>
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
<span data-ttu-id="76792-145">Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="76792-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="76792-146">Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76792-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="76792-147">In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie beim Festlegen von Parametern für verwenden können.`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="76792-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="76792-148">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="76792-148">Required?</span></span>|<span data-ttu-id="76792-149">Name</span><span class="sxs-lookup"><span data-stu-id="76792-149">Name</span></span>|<span data-ttu-id="76792-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76792-150">Description</span></span>|<span data-ttu-id="76792-151">Standard</span><span class="sxs-lookup"><span data-stu-id="76792-151">Default</span></span>|<span data-ttu-id="76792-152">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="76792-152">Possible values</span></span>|<span data-ttu-id="76792-153">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="76792-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76792-154">Ja</span><span class="sxs-lookup"><span data-stu-id="76792-154">Yes</span></span>|<span data-ttu-id="76792-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="76792-155">FQDN</span></span>|<span data-ttu-id="76792-156">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="76792-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="76792-157">Keine</span><span class="sxs-lookup"><span data-stu-id="76792-157">None</span></span>|<span data-ttu-id="76792-158">NoneFQDN-Name, 63-Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="76792-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="76792-159">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für Benennungs [Konventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="76792-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="76792-160">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-160">No</span></span>|<span data-ttu-id="76792-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="76792-161">MediaBypass</span></span> |<span data-ttu-id="76792-162">Der Parameter, der für die spätere Verwendung reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="76792-162">The parameter reserved for future use.</span></span> <span data-ttu-id="76792-163">Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="76792-163">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="76792-164">Keine</span><span class="sxs-lookup"><span data-stu-id="76792-164">None</span></span>|<span data-ttu-id="76792-165">True</span><span class="sxs-lookup"><span data-stu-id="76792-165">True</span></span><br/><span data-ttu-id="76792-166">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-166">False</span></span>|<span data-ttu-id="76792-167">Boolean</span><span class="sxs-lookup"><span data-stu-id="76792-167">Boolean</span></span>|
|<span data-ttu-id="76792-168">Ja</span><span class="sxs-lookup"><span data-stu-id="76792-168">Yes</span></span>|<span data-ttu-id="76792-169">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="76792-169">SipSignallingPort</span></span> |<span data-ttu-id="76792-170">Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="76792-170">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="76792-171">Keine</span><span class="sxs-lookup"><span data-stu-id="76792-171">None</span></span>|<span data-ttu-id="76792-172">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="76792-172">Any port</span></span>|<span data-ttu-id="76792-173">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="76792-173">0 to 65535</span></span> |
|<span data-ttu-id="76792-174">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-174">No</span></span>|<span data-ttu-id="76792-175">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="76792-175">FailoverTimeSeconds</span></span> |<span data-ttu-id="76792-176">Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="76792-176">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="76792-177">In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.</span><span class="sxs-lookup"><span data-stu-id="76792-177">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="76792-178">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="76792-178">The default value is 10.</span></span>|<span data-ttu-id="76792-179">10</span><span class="sxs-lookup"><span data-stu-id="76792-179">10</span></span>|<span data-ttu-id="76792-180">Nummer</span><span class="sxs-lookup"><span data-stu-id="76792-180">Number</span></span>|<span data-ttu-id="76792-181">Int</span><span class="sxs-lookup"><span data-stu-id="76792-181">Int</span></span>|
|<span data-ttu-id="76792-182">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-182">No</span></span>|<span data-ttu-id="76792-183">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="76792-183">ForwardCallHistory</span></span> |<span data-ttu-id="76792-184">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="76792-184">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="76792-185">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-185">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="76792-186">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="76792-186">The default value is **False** ($False).</span></span> |<span data-ttu-id="76792-187">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-187">False</span></span>|<span data-ttu-id="76792-188">True</span><span class="sxs-lookup"><span data-stu-id="76792-188">True</span></span><br/><span data-ttu-id="76792-189">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-189">False</span></span>|<span data-ttu-id="76792-190">Boolean</span><span class="sxs-lookup"><span data-stu-id="76792-190">Boolean</span></span>|
|<span data-ttu-id="76792-191">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-191">No</span></span>|<span data-ttu-id="76792-192">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="76792-192">ForwardPAI</span></span>|<span data-ttu-id="76792-193">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="76792-193">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="76792-194">Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="76792-194">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="76792-195">Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="76792-195">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="76792-196">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="76792-196">The default value is **False** ($False).</span></span>|<span data-ttu-id="76792-197">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-197">False</span></span>|<span data-ttu-id="76792-198">True</span><span class="sxs-lookup"><span data-stu-id="76792-198">True</span></span><br/><span data-ttu-id="76792-199">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-199">False</span></span>|<span data-ttu-id="76792-200">Boolean</span><span class="sxs-lookup"><span data-stu-id="76792-200">Boolean</span></span>|
|<span data-ttu-id="76792-201">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-201">No</span></span>|<span data-ttu-id="76792-202">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="76792-202">SendSIPOptions</span></span> |<span data-ttu-id="76792-203">Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76792-203">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="76792-204">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="76792-204">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="76792-205">Wir empfehlen dringend, SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76792-205">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="76792-206">Der Standardwert ist **wahr**.</span><span class="sxs-lookup"><span data-stu-id="76792-206">Default value is **True**.</span></span> |<span data-ttu-id="76792-207">True</span><span class="sxs-lookup"><span data-stu-id="76792-207">True</span></span>|<span data-ttu-id="76792-208">True</span><span class="sxs-lookup"><span data-stu-id="76792-208">True</span></span><br/><span data-ttu-id="76792-209">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-209">False</span></span>|<span data-ttu-id="76792-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="76792-210">Boolean</span></span>|
|<span data-ttu-id="76792-211">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-211">No</span></span>|<span data-ttu-id="76792-212">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="76792-212">MaxConcurrentSessions</span></span> |<span data-ttu-id="76792-213">Wird vom Warnungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="76792-213">Used by alerting system.</span></span> <span data-ttu-id="76792-214">Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="76792-214">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="76792-215">Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="76792-215">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="76792-216">Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="76792-216">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="76792-217">NULL</span><span class="sxs-lookup"><span data-stu-id="76792-217">Null</span></span>|<span data-ttu-id="76792-218">NULL</span><span class="sxs-lookup"><span data-stu-id="76792-218">Null</span></span><br/><span data-ttu-id="76792-219">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="76792-219">1 to 100,000</span></span> ||
|<span data-ttu-id="76792-220">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-220">No</span></span>|<span data-ttu-id="76792-221">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="76792-221">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="76792-222">Ermöglicht das manuelle auswählen von Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="76792-222">Allows selecting path for media manually.</span></span> <span data-ttu-id="76792-223">Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-223">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="76792-224">Wir wählen immer am nächsten zum SBC-Rechenzentrum aus.</span><span class="sxs-lookup"><span data-stu-id="76792-224">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="76792-225">In einigen Fällen kann eine öffentliche IP-Adresse beispielsweise aus dem US-Bereich einem SBC in Europa zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="76792-225">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="76792-226">In diesem Fall wird kein optimaler Medienpfad verwendet.</span><span class="sxs-lookup"><span data-stu-id="76792-226">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="76792-227">Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76792-227">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="76792-228">Wir empfehlen, diesen Parameter nur dann festzulegen, wenn die Anrufprotokolle eindeutig darauf hinweisen, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="76792-228">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="76792-229">Keine</span><span class="sxs-lookup"><span data-stu-id="76792-229">None</span></span>|<span data-ttu-id="76792-230">Landesvorwahl im ISO-Format</span><span class="sxs-lookup"><span data-stu-id="76792-230">Country codes in ISO format</span></span>||
|<span data-ttu-id="76792-231">Nein</span><span class="sxs-lookup"><span data-stu-id="76792-231">No</span></span>|<span data-ttu-id="76792-232">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="76792-232">Enabled</span></span>|<span data-ttu-id="76792-233">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76792-233">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="76792-234">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="76792-234">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="76792-235">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-235">False</span></span>|<span data-ttu-id="76792-236">True</span><span class="sxs-lookup"><span data-stu-id="76792-236">True</span></span><br/><span data-ttu-id="76792-237">Falsch</span><span class="sxs-lookup"><span data-stu-id="76792-237">False</span></span>|<span data-ttu-id="76792-238">Boolean</span><span class="sxs-lookup"><span data-stu-id="76792-238">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="76792-239">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="76792-239">Verify the SBC pairing</span></span> 

<span data-ttu-id="76792-240">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="76792-240">Verify the connection:</span></span> 
- <span data-ttu-id="76792-241">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.</span><span class="sxs-lookup"><span data-stu-id="76792-241">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="76792-242">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="76792-242">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="76792-243">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet</span><span class="sxs-lookup"><span data-stu-id="76792-243">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="76792-244">Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="76792-244">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="76792-245">Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter *Enabled* den Wert **true**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="76792-245">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="76792-246">Eingeben</span><span class="sxs-lookup"><span data-stu-id="76792-246">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="76792-247">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="76792-247">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="76792-248">Überprüfen des SIP-Options Flusses</span><span class="sxs-lookup"><span data-stu-id="76792-248">Validate SIP Options flow</span></span> 

<span data-ttu-id="76792-249">Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.</span><span class="sxs-lookup"><span data-stu-id="76792-249">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="76792-250">Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="76792-250">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="76792-251">Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="76792-251">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="76792-252">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="76792-252">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="76792-253">Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="76792-253">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="76792-254">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="76792-254">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="76792-255">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="76792-255">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="76792-256">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="76792-256">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="76792-257">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="76792-257">Configure voice routing.</span></span> <span data-ttu-id="76792-258">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="76792-258">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="76792-259">Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="76792-259">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="76792-260">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="76792-260">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="76792-261">Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="76792-261">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="76792-262">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="76792-262">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="76792-263">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="76792-263">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="76792-264">Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal.</span><span class="sxs-lookup"><span data-stu-id="76792-264">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="76792-265">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="76792-265">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="76792-266">Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="76792-266">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="76792-267">Erforderliche Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="76792-267">Required licenses:</span></span> 

- <span data-ttu-id="76792-268">Office 365 Enterprise E3 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2 und Teams) + Telefon System</span><span class="sxs-lookup"><span data-stu-id="76792-268">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="76792-269">Office 365 Enterprise E5 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2, Teams und Telefon System)</span><span class="sxs-lookup"><span data-stu-id="76792-269">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="76792-270">Optionale Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="76792-270">Optional licenses:</span></span> 

- <span data-ttu-id="76792-271">Anrufplan</span><span class="sxs-lookup"><span data-stu-id="76792-271">Calling Plan</span></span> 
- <span data-ttu-id="76792-272">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="76792-272">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="76792-273">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="76792-273">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="76792-274">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="76792-274">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="76792-275">Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten.</span><span class="sxs-lookup"><span data-stu-id="76792-275">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="76792-276">Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="76792-276">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="76792-277">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="76792-277">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="76792-278">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="76792-278">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="76792-279">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="76792-279">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="76792-280">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76792-280">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="76792-281">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="76792-281">This can be done in one step.</span></span> 

<span data-ttu-id="76792-282">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="76792-282">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="76792-283">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="76792-283">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="76792-284">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="76792-284">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="76792-285">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-285">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="76792-286">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="76792-286">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="76792-287">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76792-287">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="76792-288">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="76792-288">Configure Voice Routing</span></span> 

<span data-ttu-id="76792-289">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="76792-289">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="76792-290">Als Zahlenmuster bezeichnet</span><span class="sxs-lookup"><span data-stu-id="76792-290">Called number pattern</span></span> 
- <span data-ttu-id="76792-291">Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="76792-291">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="76792-292">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="76792-292">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="76792-293">Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-293">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="76792-294">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="76792-294">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="76792-295">VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="76792-295">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="76792-296">PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="76792-296">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="76792-297">VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="76792-297">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="76792-298">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="76792-298">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="76792-299">Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="76792-299">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="76792-300">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="76792-300">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="76792-301">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-301">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="76792-302">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="76792-302">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="76792-303">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-303">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="76792-304">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="76792-304">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="76792-305">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="76792-305">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="76792-307">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="76792-307">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="76792-308">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="76792-308">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="76792-309">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-309">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="76792-310">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="76792-310">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="76792-311">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="76792-311">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="76792-313">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="76792-313">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="76792-314">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="76792-314">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="76792-315">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="76792-315">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="76792-316">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="76792-316">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="76792-317">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="76792-317">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="76792-318">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="76792-318">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="76792-319">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="76792-319">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="76792-320">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="76792-320">**PSTN usage**</span></span>|<span data-ttu-id="76792-321">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="76792-321">**Voice route**</span></span>|<span data-ttu-id="76792-322">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="76792-322">**Number pattern**</span></span>|<span data-ttu-id="76792-323">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="76792-323">**Priority**</span></span>|<span data-ttu-id="76792-324">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="76792-324">**SBC**</span></span>|<span data-ttu-id="76792-325">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="76792-325">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76792-326">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-326">US only</span></span>|<span data-ttu-id="76792-327">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="76792-327">"Redmond 1"</span></span>|<span data-ttu-id="76792-328">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="76792-328">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="76792-329">1</span><span class="sxs-lookup"><span data-stu-id="76792-329">1</span></span>|<span data-ttu-id="76792-330">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-330">sbc1.contoso.biz</span></span><br/><span data-ttu-id="76792-331">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-331">sbc2.contoso.biz</span></span>|<span data-ttu-id="76792-332">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="76792-332">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="76792-333">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-333">US only</span></span>|<span data-ttu-id="76792-334">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="76792-334">"Redmond 2"</span></span>|<span data-ttu-id="76792-335">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="76792-335">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="76792-336">2</span><span class="sxs-lookup"><span data-stu-id="76792-336">2</span></span>|<span data-ttu-id="76792-337">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-337">sbc3.contoso.biz</span></span><br/><span data-ttu-id="76792-338">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-338">sbc4.contoso.biz</span></span>|<span data-ttu-id="76792-339">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="76792-339">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="76792-340">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-340">US only</span></span>|<span data-ttu-id="76792-341">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="76792-341">"Other +1"</span></span>|<span data-ttu-id="76792-342">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="76792-342">^\\+1(\d{10})$</span></span>|<span data-ttu-id="76792-343">3</span><span class="sxs-lookup"><span data-stu-id="76792-343">3</span></span>|<span data-ttu-id="76792-344">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-344">sbc5.contoso.biz</span></span><br/><span data-ttu-id="76792-345">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-345">sbc6.contoso.biz</span></span>|<span data-ttu-id="76792-346">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="76792-346">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="76792-347">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="76792-347">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="76792-348">In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-348">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="76792-349">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="76792-349">Examples of call routes</span></span>

<span data-ttu-id="76792-350">Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="76792-350">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="76792-351">**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="76792-351">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="76792-352">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-352">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="76792-353">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="76792-353">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="76792-354">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="76792-354">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="76792-355">Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="76792-355">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="76792-356">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76792-356">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="76792-357">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-357">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="76792-358">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="76792-358">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
<span data-ttu-id="76792-359">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-359">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="76792-360">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-360">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="76792-361">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="76792-361">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="76792-362">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="76792-362">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="76792-363">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="76792-363">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="76792-364">Alle Anrufe an denselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="76792-364">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="76792-365">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="76792-365">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="76792-366">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="76792-366">Which should return:</span></span>
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

<span data-ttu-id="76792-367">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-367">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="76792-368">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="76792-368">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="76792-369">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-369">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="76792-370">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="76792-370">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="76792-371">**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76792-371">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="76792-372">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-372">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="76792-373">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="76792-373">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="76792-374">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="76792-374">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="76792-375">Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="76792-375">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="76792-376">Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-376">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="76792-377">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="76792-377">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="76792-378">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="76792-378">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="76792-379">Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-379">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="76792-380">In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="76792-380">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="76792-381">Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="76792-381">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="76792-382">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76792-382">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="76792-383">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-383">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="76792-384">John Woods – Anrufe an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="76792-384">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="76792-385">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76792-385">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="76792-386">Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="76792-386">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="76792-388">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="76792-388">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="76792-389">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="76792-389">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="76792-390">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="76792-390">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="76792-392">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="76792-392">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="76792-393">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="76792-393">**PSTN usage**</span></span>|<span data-ttu-id="76792-394">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="76792-394">**Voice route**</span></span>|<span data-ttu-id="76792-395">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="76792-395">**Number pattern**</span></span>|<span data-ttu-id="76792-396">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="76792-396">**Priority**</span></span>|<span data-ttu-id="76792-397">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="76792-397">**SBC**</span></span>|<span data-ttu-id="76792-398">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="76792-398">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76792-399">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-399">US Only</span></span>|<span data-ttu-id="76792-400">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="76792-400">"Redmond 1"</span></span>|<span data-ttu-id="76792-401">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="76792-401">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="76792-402">1</span><span class="sxs-lookup"><span data-stu-id="76792-402">1</span></span>|<span data-ttu-id="76792-403">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-403">sbc1.contoso.biz</span></span><br/><span data-ttu-id="76792-404">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-404">sbc2.contoso.biz</span></span>|<span data-ttu-id="76792-405">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="76792-405">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="76792-406">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-406">US Only</span></span>|<span data-ttu-id="76792-407">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="76792-407">"Redmond 2"</span></span>|<span data-ttu-id="76792-408">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="76792-408">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="76792-409">2</span><span class="sxs-lookup"><span data-stu-id="76792-409">2</span></span>|<span data-ttu-id="76792-410">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-410">sbc3.contoso.biz</span></span><br/><span data-ttu-id="76792-411">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-411">sbc4.contoso.biz</span></span>|<span data-ttu-id="76792-412">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="76792-412">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="76792-413">Nur USA</span><span class="sxs-lookup"><span data-stu-id="76792-413">US Only</span></span>|<span data-ttu-id="76792-414">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="76792-414">"Other +1"</span></span>|<span data-ttu-id="76792-415">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="76792-415">^\\+1(\d{10})$</span></span>|<span data-ttu-id="76792-416">3</span><span class="sxs-lookup"><span data-stu-id="76792-416">3</span></span>|<span data-ttu-id="76792-417">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-417">sbc5.contoso.biz</span></span><br/><span data-ttu-id="76792-418">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-418">sbc6>.contoso.biz</span></span>|<span data-ttu-id="76792-419">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="76792-419">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="76792-420">International</span><span class="sxs-lookup"><span data-stu-id="76792-420">International</span></span>|<span data-ttu-id="76792-421">International</span><span class="sxs-lookup"><span data-stu-id="76792-421">International</span></span>|<span data-ttu-id="76792-422">\d +</span><span class="sxs-lookup"><span data-stu-id="76792-422">\d+</span></span>|<span data-ttu-id="76792-423">4</span><span class="sxs-lookup"><span data-stu-id="76792-423">4</span></span>|<span data-ttu-id="76792-424">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-424">sbc2.contoso.biz</span></span><br/><span data-ttu-id="76792-425">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="76792-425">sbc5.contoso.biz</span></span>|<span data-ttu-id="76792-426">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="76792-426">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="76792-427">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="76792-427">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="76792-428">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="76792-428">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="76792-429">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="76792-429">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="76792-430">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="76792-430">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="76792-431">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="76792-431">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="76792-432">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76792-432">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="76792-433">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="76792-433">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="76792-434">Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="76792-434">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="76792-435">Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="76792-435">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="76792-436">Erstellen Sie zunächst die PSTN-Nutzung "International".</span><span class="sxs-lookup"><span data-stu-id="76792-436">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="76792-437">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="76792-437">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="76792-438">Erstellen Sie als nächstes die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="76792-438">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="76792-439">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="76792-439">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. <span data-ttu-id="76792-440">Erstellen Sie als nächstes eine VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="76792-440">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="76792-441">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="76792-441">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="76792-442">Was zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="76792-442">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="76792-443">Weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="76792-443">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="76792-444">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="76792-444">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="76792-445">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="76792-445">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="76792-446">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="76792-446">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="76792-447">Microsoft Teams als bevorzugten Anruf Client für Benutzer einrichten</span><span class="sxs-lookup"><span data-stu-id="76792-447">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="76792-448">Beim direkten Routing werden Anrufe von und zu Benutzern nur weitergeleitet, wenn Sie den Team-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="76792-448">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="76792-449">Wenn in Ihrer Organisation nur Teams verwendet werden, wird empfohlen, den Modus "nur für Teams" in der Upgrade-Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="76792-449">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="76792-450">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um weitere Informationen zu erhalten, und wählen Sie die geeignete Option aus: Grund [Legendes zu Koexistenz und Upgrade-Reise für Skype for Business und Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="76792-450">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="76792-451">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76792-451">See also</span></span>

[<span data-ttu-id="76792-452">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="76792-452">Plan Direct Routing</span></span>](direct-routing-plan.md)
