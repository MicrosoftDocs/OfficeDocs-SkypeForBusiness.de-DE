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
ms.openlocfilehash: 1c93d8b028da3fb1aaf68241a974170d0045b950
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "35116017"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="4e203-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="4e203-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="4e203-104">Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="4e203-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="4e203-105">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="4e203-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="4e203-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e203-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4e203-108">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4e203-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="4e203-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4e203-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="4e203-110">Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="4e203-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="4e203-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="4e203-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4e203-112">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="4e203-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="4e203-113">Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="4e203-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="4e203-114">Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="4e203-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="4e203-115">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="4e203-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="4e203-116">Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="4e203-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="4e203-117">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="4e203-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="4e203-118">Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="4e203-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="4e203-119">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e203-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="4e203-120">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="4e203-120">Pair the SBC</span></span> 
- <span data-ttu-id="4e203-121">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="4e203-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="4e203-122">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e203-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="4e203-123">Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="4e203-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="4e203-124">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.</span><span class="sxs-lookup"><span data-stu-id="4e203-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="4e203-125">Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="4e203-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="4e203-126">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4e203-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="4e203-127">Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="4e203-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="4e203-128">Koppeln des SBC mit dem Mandanten</span><span class="sxs-lookup"><span data-stu-id="4e203-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="4e203-129">Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4e203-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="4e203-130">Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="4e203-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="4e203-131">Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="4e203-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="4e203-132">Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e203-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="4e203-133">Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e203-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="4e203-134">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="4e203-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="4e203-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="4e203-135">**contoso**.com</span></span><br/><span data-ttu-id="4e203-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4e203-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="4e203-137">Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e203-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="4e203-138">Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="4e203-139">Gibt</span><span class="sxs-lookup"><span data-stu-id="4e203-139">Returns:</span></span>
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
<span data-ttu-id="4e203-140">Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4e203-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="4e203-141">Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e203-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="4e203-142">In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie beim Festlegen von Parametern für verwenden können.`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="4e203-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="4e203-143">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="4e203-143">Required?</span></span>|<span data-ttu-id="4e203-144">Name</span><span class="sxs-lookup"><span data-stu-id="4e203-144">Name</span></span>|<span data-ttu-id="4e203-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e203-145">Description</span></span>|<span data-ttu-id="4e203-146">Standard</span><span class="sxs-lookup"><span data-stu-id="4e203-146">Default</span></span>|<span data-ttu-id="4e203-147">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="4e203-147">Possible values</span></span>|<span data-ttu-id="4e203-148">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4e203-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e203-149">Ja</span><span class="sxs-lookup"><span data-stu-id="4e203-149">Yes</span></span>|<span data-ttu-id="4e203-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="4e203-150">FQDN</span></span>|<span data-ttu-id="4e203-151">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="4e203-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="4e203-152">Keine</span><span class="sxs-lookup"><span data-stu-id="4e203-152">None</span></span>|<span data-ttu-id="4e203-153">NoneFQDN-Name, 63-Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="4e203-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="4e203-154">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für Benennungs [Konventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="4e203-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="4e203-155">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-155">No</span></span>|<span data-ttu-id="4e203-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="4e203-156">MediaBypass</span></span> |<span data-ttu-id="4e203-157">Der Parameter, der für die spätere Verwendung reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-157">The parameter reserved for future use.</span></span> <span data-ttu-id="4e203-158">Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e203-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="4e203-159">Keine</span><span class="sxs-lookup"><span data-stu-id="4e203-159">None</span></span>|<span data-ttu-id="4e203-160">True</span><span class="sxs-lookup"><span data-stu-id="4e203-160">True</span></span><br/><span data-ttu-id="4e203-161">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-161">False</span></span>|<span data-ttu-id="4e203-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e203-162">Boolean</span></span>|
|<span data-ttu-id="4e203-163">Ja</span><span class="sxs-lookup"><span data-stu-id="4e203-163">Yes</span></span>|<span data-ttu-id="4e203-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="4e203-164">SipSignallingPort</span></span> |<span data-ttu-id="4e203-165">Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="4e203-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="4e203-166">Keine</span><span class="sxs-lookup"><span data-stu-id="4e203-166">None</span></span>|<span data-ttu-id="4e203-167">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="4e203-167">Any port</span></span>|<span data-ttu-id="4e203-168">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="4e203-168">0 to 65535</span></span> |
|<span data-ttu-id="4e203-169">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-169">No</span></span>|<span data-ttu-id="4e203-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="4e203-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="4e203-171">Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4e203-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="4e203-172">In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.</span><span class="sxs-lookup"><span data-stu-id="4e203-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="4e203-173">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="4e203-173">The default value is 10.</span></span>|<span data-ttu-id="4e203-174">10</span><span class="sxs-lookup"><span data-stu-id="4e203-174">10</span></span>|<span data-ttu-id="4e203-175">Nummer</span><span class="sxs-lookup"><span data-stu-id="4e203-175">Number</span></span>|<span data-ttu-id="4e203-176">Int</span><span class="sxs-lookup"><span data-stu-id="4e203-176">Int</span></span>|
|<span data-ttu-id="4e203-177">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-177">No</span></span>|<span data-ttu-id="4e203-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="4e203-178">ForwardCallHistory</span></span> |<span data-ttu-id="4e203-179">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="4e203-180">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="4e203-181">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="4e203-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="4e203-182">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-182">False</span></span>|<span data-ttu-id="4e203-183">True</span><span class="sxs-lookup"><span data-stu-id="4e203-183">True</span></span><br/><span data-ttu-id="4e203-184">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-184">False</span></span>|<span data-ttu-id="4e203-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e203-185">Boolean</span></span>|
|<span data-ttu-id="4e203-186">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-186">No</span></span>|<span data-ttu-id="4e203-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="4e203-187">ForwardPAI</span></span>|<span data-ttu-id="4e203-188">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="4e203-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="4e203-189">Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4e203-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="4e203-190">Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="4e203-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="4e203-191">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="4e203-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="4e203-192">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-192">False</span></span>|<span data-ttu-id="4e203-193">True</span><span class="sxs-lookup"><span data-stu-id="4e203-193">True</span></span><br/><span data-ttu-id="4e203-194">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-194">False</span></span>|<span data-ttu-id="4e203-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e203-195">Boolean</span></span>|
|<span data-ttu-id="4e203-196">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-196">No</span></span>|<span data-ttu-id="4e203-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="4e203-197">SendSIPOptions</span></span> |<span data-ttu-id="4e203-198">Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4e203-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="4e203-199">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4e203-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="4e203-200">Wir empfehlen dringend, SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="4e203-201">Der Standardwert ist **wahr**.</span><span class="sxs-lookup"><span data-stu-id="4e203-201">Default value is **True**.</span></span> |<span data-ttu-id="4e203-202">True</span><span class="sxs-lookup"><span data-stu-id="4e203-202">True</span></span>|<span data-ttu-id="4e203-203">True</span><span class="sxs-lookup"><span data-stu-id="4e203-203">True</span></span><br/><span data-ttu-id="4e203-204">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-204">False</span></span>|<span data-ttu-id="4e203-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e203-205">Boolean</span></span>|
|<span data-ttu-id="4e203-206">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-206">No</span></span>|<span data-ttu-id="4e203-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="4e203-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="4e203-208">Wird vom Warnungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e203-208">Used by alerting system.</span></span> <span data-ttu-id="4e203-209">Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="4e203-210">Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="4e203-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="4e203-211">Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="4e203-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="4e203-212">NULL</span><span class="sxs-lookup"><span data-stu-id="4e203-212">Null</span></span>|<span data-ttu-id="4e203-213">NULL</span><span class="sxs-lookup"><span data-stu-id="4e203-213">Null</span></span><br/><span data-ttu-id="4e203-214">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="4e203-214">1 to 100,000</span></span> ||
|<span data-ttu-id="4e203-215">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-215">No</span></span>|<span data-ttu-id="4e203-216">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="4e203-216">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="4e203-217">Ermöglicht das manuelle auswählen von Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="4e203-217">Allows selecting path for media manually.</span></span> <span data-ttu-id="4e203-218">Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-218">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="4e203-219">Wir wählen immer am nächsten zum SBC-Rechenzentrum aus.</span><span class="sxs-lookup"><span data-stu-id="4e203-219">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="4e203-220">In einigen Fällen kann eine öffentliche IP-Adresse beispielsweise aus dem US-Bereich einem SBC in Europa zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-220">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="4e203-221">In diesem Fall wird kein optimaler Medienpfad verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e203-221">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="4e203-222">Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-222">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="4e203-223">Wir empfehlen, diesen Parameter nur dann festzulegen, wenn die Anrufprotokolle eindeutig darauf hinweisen, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="4e203-223">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="4e203-224">Keine</span><span class="sxs-lookup"><span data-stu-id="4e203-224">None</span></span>|<span data-ttu-id="4e203-225">Landesvorwahl im ISO-Format</span><span class="sxs-lookup"><span data-stu-id="4e203-225">Country codes in ISO format</span></span>||
|<span data-ttu-id="4e203-226">Nein</span><span class="sxs-lookup"><span data-stu-id="4e203-226">No</span></span>|<span data-ttu-id="4e203-227">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="4e203-227">Enabled</span></span>|<span data-ttu-id="4e203-228">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-228">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="4e203-229">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="4e203-229">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="4e203-230">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-230">False</span></span>|<span data-ttu-id="4e203-231">True</span><span class="sxs-lookup"><span data-stu-id="4e203-231">True</span></span><br/><span data-ttu-id="4e203-232">Falsch</span><span class="sxs-lookup"><span data-stu-id="4e203-232">False</span></span>|<span data-ttu-id="4e203-233">Boolean</span><span class="sxs-lookup"><span data-stu-id="4e203-233">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="4e203-234">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="4e203-234">Verify the SBC pairing</span></span> 

<span data-ttu-id="4e203-235">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="4e203-235">Verify the connection:</span></span> 
- <span data-ttu-id="4e203-236">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.</span><span class="sxs-lookup"><span data-stu-id="4e203-236">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="4e203-237">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="4e203-237">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="4e203-238">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet</span><span class="sxs-lookup"><span data-stu-id="4e203-238">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="4e203-239">Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="4e203-239">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="4e203-240">Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter *Enabled* den Wert **true**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4e203-240">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="4e203-241">Eingeben</span><span class="sxs-lookup"><span data-stu-id="4e203-241">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="4e203-242">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4e203-242">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="4e203-243">Überprüfen des SIP-Options Flusses</span><span class="sxs-lookup"><span data-stu-id="4e203-243">Validate SIP Options flow</span></span> 

<span data-ttu-id="4e203-244">Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.</span><span class="sxs-lookup"><span data-stu-id="4e203-244">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="4e203-245">Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-245">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="4e203-246">Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-246">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="4e203-247">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="4e203-247">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="4e203-248">Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4e203-248">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="4e203-249">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="4e203-249">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="4e203-250">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4e203-250">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="4e203-251">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="4e203-251">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="4e203-252">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="4e203-252">Configure voice routing.</span></span> <span data-ttu-id="4e203-253">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="4e203-253">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="4e203-254">Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="4e203-254">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="4e203-255">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e203-255">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="4e203-256">Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="4e203-256">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="4e203-257">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="4e203-257">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="4e203-258">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="4e203-258">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="4e203-259">Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal.</span><span class="sxs-lookup"><span data-stu-id="4e203-259">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="4e203-260">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="4e203-260">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="4e203-261">Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="4e203-261">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="4e203-262">Erforderliche Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="4e203-262">Required licenses:</span></span> 

- <span data-ttu-id="4e203-263">Office 365 Enterprise E3 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2 und Teams) + Telefon System</span><span class="sxs-lookup"><span data-stu-id="4e203-263">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="4e203-264">Office 365 Enterprise E5 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2, Teams und Telefon System)</span><span class="sxs-lookup"><span data-stu-id="4e203-264">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="4e203-265">Optionale Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="4e203-265">Optional licenses:</span></span> 

- <span data-ttu-id="4e203-266">Anrufplan</span><span class="sxs-lookup"><span data-stu-id="4e203-266">Calling Plan</span></span> 
- <span data-ttu-id="4e203-267">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4e203-267">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="4e203-268">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4e203-268">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="4e203-269">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-269">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="4e203-270">Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten.</span><span class="sxs-lookup"><span data-stu-id="4e203-270">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="4e203-271">Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4e203-271">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="4e203-272">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e203-272">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="4e203-273">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-273">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="4e203-274">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="4e203-274">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="4e203-275">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-275">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="4e203-276">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4e203-276">This can be done in one step.</span></span> 

<span data-ttu-id="4e203-277">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="4e203-277">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="4e203-278">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="4e203-278">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="4e203-279">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-279">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="4e203-280">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-280">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="4e203-281">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-281">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4e203-282">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e203-282">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="4e203-283">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="4e203-283">Configure Voice Routing</span></span> 

<span data-ttu-id="4e203-284">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="4e203-284">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="4e203-285">Als Zahlenmuster bezeichnet</span><span class="sxs-lookup"><span data-stu-id="4e203-285">Called number pattern</span></span> 
- <span data-ttu-id="4e203-286">Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="4e203-286">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="4e203-287">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-287">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="4e203-288">Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-288">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="4e203-289">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="4e203-289">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="4e203-290">VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="4e203-290">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="4e203-291">PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="4e203-291">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="4e203-292">VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="4e203-292">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="4e203-293">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="4e203-293">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="4e203-294">Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="4e203-294">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="4e203-295">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="4e203-295">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="4e203-296">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-296">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4e203-297">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4e203-297">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="4e203-298">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-298">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4e203-299">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="4e203-299">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="4e203-300">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4e203-300">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="4e203-302">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-302">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4e203-303">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4e203-303">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="4e203-304">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-304">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="4e203-305">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="4e203-305">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="4e203-306">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="4e203-306">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="4e203-308">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="4e203-308">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4e203-309">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="4e203-309">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4e203-310">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4e203-310">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4e203-311">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="4e203-311">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="4e203-312">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4e203-312">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="4e203-313">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4e203-313">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="4e203-314">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="4e203-314">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="4e203-315">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="4e203-315">**PSTN usage**</span></span>|<span data-ttu-id="4e203-316">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="4e203-316">**Voice route**</span></span>|<span data-ttu-id="4e203-317">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="4e203-317">**Number pattern**</span></span>|<span data-ttu-id="4e203-318">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="4e203-318">**Priority**</span></span>|<span data-ttu-id="4e203-319">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="4e203-319">**SBC**</span></span>|<span data-ttu-id="4e203-320">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4e203-320">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e203-321">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-321">US only</span></span>|<span data-ttu-id="4e203-322">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4e203-322">"Redmond 1"</span></span>|<span data-ttu-id="4e203-323">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-323">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4e203-324">1</span><span class="sxs-lookup"><span data-stu-id="4e203-324">1</span></span>|<span data-ttu-id="4e203-325">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-325">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4e203-326">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-326">sbc2.contoso.biz</span></span>|<span data-ttu-id="4e203-327">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4e203-327">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4e203-328">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-328">US only</span></span>|<span data-ttu-id="4e203-329">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4e203-329">"Redmond 2"</span></span>|<span data-ttu-id="4e203-330">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-330">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4e203-331">2</span><span class="sxs-lookup"><span data-stu-id="4e203-331">2</span></span>|<span data-ttu-id="4e203-332">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-332">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4e203-333">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-333">sbc4.contoso.biz</span></span>|<span data-ttu-id="4e203-334">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4e203-334">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4e203-335">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-335">US only</span></span>|<span data-ttu-id="4e203-336">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="4e203-336">"Other +1"</span></span>|<span data-ttu-id="4e203-337">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-337">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4e203-338">3</span><span class="sxs-lookup"><span data-stu-id="4e203-338">3</span></span>|<span data-ttu-id="4e203-339">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-339">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4e203-340">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-340">sbc6.contoso.biz</span></span>|<span data-ttu-id="4e203-341">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4e203-341">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="4e203-342">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="4e203-342">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="4e203-343">In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-343">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="4e203-344">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="4e203-344">Examples of call routes</span></span>

<span data-ttu-id="4e203-345">Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="4e203-345">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="4e203-346">**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="4e203-346">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="4e203-347">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-347">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="4e203-348">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="4e203-348">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="4e203-349">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="4e203-349">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="4e203-350">Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e203-350">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="4e203-351">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e203-351">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="4e203-352">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-352">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="4e203-353">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4e203-353">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="4e203-354">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-354">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4e203-355">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-355">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="4e203-356">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="4e203-356">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="4e203-357">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="4e203-357">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="4e203-358">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="4e203-358">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="4e203-359">Alle Anrufe an denselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="4e203-359">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="4e203-360">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="4e203-360">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="4e203-361">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="4e203-361">Which should return:</span></span>
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

<span data-ttu-id="4e203-362">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-362">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="4e203-363">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e203-363">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="4e203-364">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-364">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4e203-365">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4e203-365">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="4e203-366">**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e203-366">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="4e203-367">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-367">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="4e203-368">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="4e203-368">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="4e203-369">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4e203-369">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="4e203-370">Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="4e203-370">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="4e203-371">Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-371">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="4e203-372">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e203-372">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="4e203-373">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="4e203-373">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="4e203-374">Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-374">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="4e203-375">In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="4e203-375">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="4e203-376">Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="4e203-376">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="4e203-377">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-377">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4e203-378">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-378">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="4e203-379">John Woods – Anrufe an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e203-379">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="4e203-380">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e203-380">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4e203-381">Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4e203-381">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="4e203-383">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="4e203-383">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4e203-384">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="4e203-384">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4e203-385">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4e203-385">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="4e203-387">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="4e203-387">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="4e203-388">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="4e203-388">**PSTN usage**</span></span>|<span data-ttu-id="4e203-389">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="4e203-389">**Voice route**</span></span>|<span data-ttu-id="4e203-390">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="4e203-390">**Number pattern**</span></span>|<span data-ttu-id="4e203-391">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="4e203-391">**Priority**</span></span>|<span data-ttu-id="4e203-392">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="4e203-392">**SBC**</span></span>|<span data-ttu-id="4e203-393">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4e203-393">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e203-394">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-394">US Only</span></span>|<span data-ttu-id="4e203-395">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4e203-395">"Redmond 1"</span></span>|<span data-ttu-id="4e203-396">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-396">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4e203-397">1</span><span class="sxs-lookup"><span data-stu-id="4e203-397">1</span></span>|<span data-ttu-id="4e203-398">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-398">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4e203-399">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-399">sbc2.contoso.biz</span></span>|<span data-ttu-id="4e203-400">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4e203-400">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4e203-401">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-401">US Only</span></span>|<span data-ttu-id="4e203-402">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4e203-402">"Redmond 2"</span></span>|<span data-ttu-id="4e203-403">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-403">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4e203-404">2</span><span class="sxs-lookup"><span data-stu-id="4e203-404">2</span></span>|<span data-ttu-id="4e203-405">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-405">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4e203-406">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-406">sbc4.contoso.biz</span></span>|<span data-ttu-id="4e203-407">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4e203-407">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4e203-408">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4e203-408">US Only</span></span>|<span data-ttu-id="4e203-409">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="4e203-409">"Other +1"</span></span>|<span data-ttu-id="4e203-410">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4e203-410">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4e203-411">3</span><span class="sxs-lookup"><span data-stu-id="4e203-411">3</span></span>|<span data-ttu-id="4e203-412">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-412">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4e203-413">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-413">sbc6>.contoso.biz</span></span>|<span data-ttu-id="4e203-414">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4e203-414">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="4e203-415">International</span><span class="sxs-lookup"><span data-stu-id="4e203-415">International</span></span>|<span data-ttu-id="4e203-416">International</span><span class="sxs-lookup"><span data-stu-id="4e203-416">International</span></span>|<span data-ttu-id="4e203-417">\d +</span><span class="sxs-lookup"><span data-stu-id="4e203-417">\d+</span></span>|<span data-ttu-id="4e203-418">4</span><span class="sxs-lookup"><span data-stu-id="4e203-418">4</span></span>|<span data-ttu-id="4e203-419">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-419">sbc2.contoso.biz</span></span><br/><span data-ttu-id="4e203-420">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4e203-420">sbc5.contoso.biz</span></span>|<span data-ttu-id="4e203-421">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="4e203-421">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="4e203-422">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="4e203-422">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="4e203-423">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4e203-423">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="4e203-424">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4e203-424">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="4e203-425">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4e203-425">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="4e203-426">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4e203-426">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="4e203-427">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4e203-427">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="4e203-428">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="4e203-428">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="4e203-429">Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="4e203-429">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="4e203-430">Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4e203-430">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="4e203-431">Erstellen Sie zunächst die PSTN-Nutzung "International".</span><span class="sxs-lookup"><span data-stu-id="4e203-431">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="4e203-432">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4e203-432">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="4e203-433">Erstellen Sie als nächstes die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="4e203-433">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="4e203-434">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4e203-434">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="4e203-435">Erstellen Sie als nächstes eine VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="4e203-435">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="4e203-436">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4e203-436">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="4e203-437">Was zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="4e203-437">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="4e203-438">Weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="4e203-438">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="4e203-439">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="4e203-439">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="4e203-440">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4e203-440">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="4e203-441">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="4e203-441">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="4e203-442">Microsoft Teams als bevorzugten Anruf Client für Benutzer einrichten</span><span class="sxs-lookup"><span data-stu-id="4e203-442">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="4e203-443">Beim direkten Routing werden Anrufe von und zu Benutzern nur weitergeleitet, wenn Sie den Team-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e203-443">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="4e203-444">Wenn in Ihrer Organisation nur Teams verwendet werden, wird empfohlen, den Modus "nur für Teams" in der Upgrade-Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4e203-444">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="4e203-445">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um weitere Informationen zu erhalten, und wählen Sie die geeignete Option aus: Grund [Legendes zu Koexistenz und Upgrade-Reise für Skype for Business und Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="4e203-445">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="4e203-446">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e203-446">See also</span></span>

[<span data-ttu-id="4e203-447">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="4e203-447">Plan Direct Routing</span></span>](direct-routing-plan.md)
