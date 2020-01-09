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
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: 8cdebcf9ae01a362c883ed5e51b0c883c4ea0d44
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992592"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="a39ee-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="a39ee-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="a39ee-104">Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a39ee-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="a39ee-105">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="a39ee-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="a39ee-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a39ee-108">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a39ee-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="a39ee-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a39ee-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="a39ee-110">Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="a39ee-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="a39ee-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="a39ee-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a39ee-112">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="a39ee-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a39ee-113">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="a39ee-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a39ee-114">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="a39ee-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="a39ee-115">Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="a39ee-116">Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="a39ee-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="a39ee-117">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="a39ee-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="a39ee-118">Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="a39ee-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="a39ee-119">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="a39ee-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="a39ee-120">Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="a39ee-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="a39ee-121">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a39ee-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="a39ee-122">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="a39ee-122">Pair the SBC</span></span> 
- <span data-ttu-id="a39ee-123">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="a39ee-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="a39ee-124">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a39ee-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="a39ee-125">Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="a39ee-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="a39ee-126">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.</span><span class="sxs-lookup"><span data-stu-id="a39ee-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="a39ee-127">Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="a39ee-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="a39ee-128">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a39ee-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="a39ee-129">Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="a39ee-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="a39ee-130">Koppeln des SBC mit dem Mandanten</span><span class="sxs-lookup"><span data-stu-id="a39ee-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="a39ee-131">Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a39ee-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="a39ee-132">Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="a39ee-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="a39ee-133">Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="a39ee-134">Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="a39ee-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="a39ee-135">Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="a39ee-136">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="a39ee-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="a39ee-137">**contoso**.com</span></span><br/><span data-ttu-id="a39ee-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="a39ee-139">Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="a39ee-140">Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="a39ee-141">Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass ein Benutzer mit dieser Domäne und eine zugewiesene E3-oder E5-Lizenz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="a39ee-142">Wenn dies nicht der Fall ist, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a39ee-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="a39ee-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="a39ee-143"></span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="a39ee-144">Gibt</span><span class="sxs-lookup"><span data-stu-id="a39ee-144">Returns:</span></span>
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
<span data-ttu-id="a39ee-145">Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="a39ee-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="a39ee-146">Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="a39ee-147">In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie zum Festlegen von ```New-CsOnlinePstnGateway```Parametern für verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a39ee-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="a39ee-148">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="a39ee-148">Required?</span></span>|<span data-ttu-id="a39ee-149">Name</span><span class="sxs-lookup"><span data-stu-id="a39ee-149">Name</span></span>|<span data-ttu-id="a39ee-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a39ee-150">Description</span></span>|<span data-ttu-id="a39ee-151">Standard</span><span class="sxs-lookup"><span data-stu-id="a39ee-151">Default</span></span>|<span data-ttu-id="a39ee-152">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="a39ee-152">Possible values</span></span>|<span data-ttu-id="a39ee-153">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a39ee-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a39ee-154">Ja</span><span class="sxs-lookup"><span data-stu-id="a39ee-154">Yes</span></span>|<span data-ttu-id="a39ee-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="a39ee-155">FQDN</span></span>|<span data-ttu-id="a39ee-156">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="a39ee-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="a39ee-157">Keine</span><span class="sxs-lookup"><span data-stu-id="a39ee-157">None</span></span>|<span data-ttu-id="a39ee-158">NoneFQDN-Name, 63-Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="a39ee-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="a39ee-159">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für [Benennungskonventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="a39ee-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="a39ee-160">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-160">No</span></span>|<span data-ttu-id="a39ee-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="a39ee-161">MediaBypass</span></span> |<span data-ttu-id="a39ee-162">Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="a39ee-163">Keine</span><span class="sxs-lookup"><span data-stu-id="a39ee-163">None</span></span>|<span data-ttu-id="a39ee-164">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-164">True</span></span><br/><span data-ttu-id="a39ee-165">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-165">False</span></span>|<span data-ttu-id="a39ee-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="a39ee-166">Boolean</span></span>|
|<span data-ttu-id="a39ee-167">Ja</span><span class="sxs-lookup"><span data-stu-id="a39ee-167">Yes</span></span>|<span data-ttu-id="a39ee-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="a39ee-168">SipSignallingPort</span></span> |<span data-ttu-id="a39ee-169">Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="a39ee-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="a39ee-170">Keine</span><span class="sxs-lookup"><span data-stu-id="a39ee-170">None</span></span>|<span data-ttu-id="a39ee-171">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="a39ee-171">Any port</span></span>|<span data-ttu-id="a39ee-172">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="a39ee-172">0 to 65535</span></span> |
|<span data-ttu-id="a39ee-173">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-173">No</span></span>|<span data-ttu-id="a39ee-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="a39ee-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="a39ee-175">Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a39ee-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="a39ee-176">In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="a39ee-177">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="a39ee-177">The default value is 10.</span></span>|<span data-ttu-id="a39ee-178">10</span><span class="sxs-lookup"><span data-stu-id="a39ee-178">10</span></span>|<span data-ttu-id="a39ee-179">Nummer</span><span class="sxs-lookup"><span data-stu-id="a39ee-179">Number</span></span>|<span data-ttu-id="a39ee-180">Int</span><span class="sxs-lookup"><span data-stu-id="a39ee-180">Int</span></span>|
|<span data-ttu-id="a39ee-181">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-181">No</span></span>|<span data-ttu-id="a39ee-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="a39ee-182">ForwardCallHistory</span></span> |<span data-ttu-id="a39ee-183">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="a39ee-184">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="a39ee-185">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="a39ee-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="a39ee-186">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-186">False</span></span>|<span data-ttu-id="a39ee-187">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-187">True</span></span><br/><span data-ttu-id="a39ee-188">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-188">False</span></span>|<span data-ttu-id="a39ee-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="a39ee-189">Boolean</span></span>|
|<span data-ttu-id="a39ee-190">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-190">No</span></span>|<span data-ttu-id="a39ee-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="a39ee-191">ForwardPAI</span></span>|<span data-ttu-id="a39ee-192">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a39ee-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="a39ee-193">Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="a39ee-194">Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="a39ee-195">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="a39ee-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="a39ee-196">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-196">False</span></span>|<span data-ttu-id="a39ee-197">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-197">True</span></span><br/><span data-ttu-id="a39ee-198">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-198">False</span></span>|<span data-ttu-id="a39ee-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="a39ee-199">Boolean</span></span>|
|<span data-ttu-id="a39ee-200">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-200">No</span></span>|<span data-ttu-id="a39ee-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="a39ee-201">SendSIPOptions</span></span> |<span data-ttu-id="a39ee-202">Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="a39ee-203">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="a39ee-204">Wir empfehlen dringend, SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="a39ee-205">Der Standardwert ist **wahr**.</span><span class="sxs-lookup"><span data-stu-id="a39ee-205">Default value is **True**.</span></span> |<span data-ttu-id="a39ee-206">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-206">True</span></span>|<span data-ttu-id="a39ee-207">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-207">True</span></span><br/><span data-ttu-id="a39ee-208">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-208">False</span></span>|<span data-ttu-id="a39ee-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="a39ee-209">Boolean</span></span>|
|<span data-ttu-id="a39ee-210">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-210">No</span></span>|<span data-ttu-id="a39ee-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="a39ee-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="a39ee-212">Wird vom Warnungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-212">Used by alerting system.</span></span> <span data-ttu-id="a39ee-213">Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="a39ee-214">Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="a39ee-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="a39ee-215">Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="a39ee-216">NULL</span><span class="sxs-lookup"><span data-stu-id="a39ee-216">Null</span></span>|<span data-ttu-id="a39ee-217">NULL</span><span class="sxs-lookup"><span data-stu-id="a39ee-217">Null</span></span><br/><span data-ttu-id="a39ee-218">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="a39ee-218">1 to 100,000</span></span> ||
|<span data-ttu-id="a39ee-219">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-219">No</span></span>|<span data-ttu-id="a39ee-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="a39ee-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="a39ee-221">Ermöglicht das manuelle auswählen von Pfad für Medien.</span><span class="sxs-lookup"><span data-stu-id="a39ee-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="a39ee-222">Beim direkten Routing wird ein Datacenter für Medienpfad basierend auf der öffentlichen IP-Adresse des SBC zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="a39ee-223">Wir wählen immer am nächsten zum SBC-Rechenzentrum aus.</span><span class="sxs-lookup"><span data-stu-id="a39ee-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="a39ee-224">In einigen Fällen kann eine öffentliche IP-Adresse beispielsweise aus dem US-Bereich einem SBC in Europa zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="a39ee-225">In diesem Fall wird kein optimaler Medienpfad verwendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="a39ee-226">Mit diesem Parameter kann der bevorzugte Bereich für den Mediendatenverkehr manuell eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="a39ee-227">Wir empfehlen, diesen Parameter nur dann festzulegen, wenn die Anrufprotokolle eindeutig darauf hinweisen, dass die automatische Zuweisung des Rechenzentrums für Medienpfad dem SBC-Rechenzentrum nicht am nächsten kommt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="a39ee-228">Keine</span><span class="sxs-lookup"><span data-stu-id="a39ee-228">None</span></span>|<span data-ttu-id="a39ee-229">Landesvorwahl im ISO-Format</span><span class="sxs-lookup"><span data-stu-id="a39ee-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="a39ee-230">Nein</span><span class="sxs-lookup"><span data-stu-id="a39ee-230">No</span></span>|<span data-ttu-id="a39ee-231">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a39ee-231">Enabled</span></span>|<span data-ttu-id="a39ee-232">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="a39ee-233">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="a39ee-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="a39ee-234">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-234">False</span></span>|<span data-ttu-id="a39ee-235">Wahr</span><span class="sxs-lookup"><span data-stu-id="a39ee-235">True</span></span><br/><span data-ttu-id="a39ee-236">Falsch</span><span class="sxs-lookup"><span data-stu-id="a39ee-236">False</span></span>|<span data-ttu-id="a39ee-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="a39ee-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="a39ee-238">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="a39ee-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="a39ee-239">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="a39ee-239">Verify the connection:</span></span> 
- <span data-ttu-id="a39ee-240">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="a39ee-241">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="a39ee-242">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet</span><span class="sxs-lookup"><span data-stu-id="a39ee-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="a39ee-243">Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="a39ee-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="a39ee-244">Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter **Enabled** den Wert **true**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="a39ee-245">Eingeben</span><span class="sxs-lookup"><span data-stu-id="a39ee-245">Enter:</span></span>

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="a39ee-246">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a39ee-246">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="a39ee-247">Überprüfen des SIP-Options Flusses</span><span class="sxs-lookup"><span data-stu-id="a39ee-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="a39ee-248">Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.</span><span class="sxs-lookup"><span data-stu-id="a39ee-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="a39ee-249">Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="a39ee-250">Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="a39ee-251">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="a39ee-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="a39ee-252">Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a39ee-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="a39ee-253">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="a39ee-254">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="a39ee-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="a39ee-255">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="a39ee-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="a39ee-256">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="a39ee-256">Configure voice routing.</span></span> <span data-ttu-id="a39ee-257">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="a39ee-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="a39ee-258">Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="a39ee-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="a39ee-259">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="a39ee-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="a39ee-260">Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="a39ee-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="a39ee-261">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="a39ee-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="a39ee-262">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="a39ee-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="a39ee-263">Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal.</span><span class="sxs-lookup"><span data-stu-id="a39ee-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="a39ee-264">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="a39ee-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="a39ee-265">Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="a39ee-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="a39ee-266">Erforderliche Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-266">Required licenses:</span></span> 

- <span data-ttu-id="a39ee-267">Office 365 Enterprise E3 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2 und Teams) + Telefon System</span><span class="sxs-lookup"><span data-stu-id="a39ee-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="a39ee-268">Office 365 Enterprise E5 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2, Teams und Telefon System)</span><span class="sxs-lookup"><span data-stu-id="a39ee-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="a39ee-269">Optionale Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-269">Optional licenses:</span></span> 

- <span data-ttu-id="a39ee-270">Anrufplan</span><span class="sxs-lookup"><span data-stu-id="a39ee-270">Calling Plan</span></span> 
- <span data-ttu-id="a39ee-271">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="a39ee-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="a39ee-272">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="a39ee-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="a39ee-273">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="a39ee-274">Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten.</span><span class="sxs-lookup"><span data-stu-id="a39ee-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="a39ee-275">Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="a39ee-276">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="a39ee-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="a39ee-277">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-277">Issue the command:</span></span> 

```PowerShell
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="a39ee-278">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="a39ee-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="a39ee-279">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="a39ee-280">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-280">This can be done in one step.</span></span> 

<span data-ttu-id="a39ee-281">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="a39ee-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="a39ee-282">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="a39ee-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="a39ee-283">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-283">Enter the command:</span></span> 
 
```PowerShell
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="a39ee-284">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="a39ee-285">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="a39ee-286">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a39ee-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="a39ee-287">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="a39ee-287">Configure Voice Routing</span></span> 

<span data-ttu-id="a39ee-288">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="a39ee-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="a39ee-289">Als Zahlenmuster bezeichnet</span><span class="sxs-lookup"><span data-stu-id="a39ee-289">Called number pattern</span></span> 
- <span data-ttu-id="a39ee-290">Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="a39ee-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="a39ee-291">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="a39ee-292">Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="a39ee-293">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="a39ee-294">VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="a39ee-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="a39ee-295">PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="a39ee-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="a39ee-296">VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="a39ee-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="a39ee-297">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="a39ee-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="a39ee-298">Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="a39ee-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="a39ee-299">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="a39ee-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="a39ee-300">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a39ee-301">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="a39ee-302">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="a39ee-303">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="a39ee-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="a39ee-304">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-304">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="a39ee-306">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a39ee-307">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a39ee-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="a39ee-308">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="a39ee-309">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="a39ee-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="a39ee-310">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="a39ee-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="a39ee-312">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="a39ee-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="a39ee-313">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="a39ee-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="a39ee-314">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a39ee-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a39ee-315">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="a39ee-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="a39ee-316">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="a39ee-317">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="a39ee-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="a39ee-318">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="a39ee-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="a39ee-319">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="a39ee-319">**PSTN usage**</span></span>|<span data-ttu-id="a39ee-320">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="a39ee-320">**Voice route**</span></span>|<span data-ttu-id="a39ee-321">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="a39ee-321">**Number pattern**</span></span>|<span data-ttu-id="a39ee-322">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a39ee-322">**Priority**</span></span>|<span data-ttu-id="a39ee-323">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="a39ee-323">**SBC**</span></span>|<span data-ttu-id="a39ee-324">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a39ee-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a39ee-325">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-325">US only</span></span>|<span data-ttu-id="a39ee-326">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a39ee-326">"Redmond 1"</span></span>|<span data-ttu-id="a39ee-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a39ee-328">1</span><span class="sxs-lookup"><span data-stu-id="a39ee-328">1</span></span>|<span data-ttu-id="a39ee-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a39ee-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="a39ee-331">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a39ee-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a39ee-332">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-332">US only</span></span>|<span data-ttu-id="a39ee-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a39ee-333">"Redmond 2"</span></span>|<span data-ttu-id="a39ee-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a39ee-335">2</span><span class="sxs-lookup"><span data-stu-id="a39ee-335">2</span></span>|<span data-ttu-id="a39ee-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a39ee-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="a39ee-338">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a39ee-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a39ee-339">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-339">US only</span></span>|<span data-ttu-id="a39ee-340">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="a39ee-340">"Other +1"</span></span>|<span data-ttu-id="a39ee-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a39ee-342">3</span><span class="sxs-lookup"><span data-stu-id="a39ee-342">3</span></span>|<span data-ttu-id="a39ee-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a39ee-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="a39ee-345">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a39ee-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="a39ee-346">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="a39ee-347">In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="a39ee-348">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="a39ee-348">Examples of call routes</span></span>

<span data-ttu-id="a39ee-349">Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="a39ee-350">**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="a39ee-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="a39ee-351">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="a39ee-352">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="a39ee-352">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="a39ee-353">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="a39ee-353">Which returns a list of names that may be truncated:</span></span>
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="a39ee-354">Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

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

<span data-ttu-id="a39ee-355">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a39ee-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="a39ee-356">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-356">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a39ee-357">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a39ee-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="a39ee-358">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-358">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a39ee-359">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-359">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="a39ee-360">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="a39ee-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="a39ee-361">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="a39ee-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="a39ee-362">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="a39ee-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="a39ee-363">Alle Anrufe an denselben SBC weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="a39ee-363">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="a39ee-364">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="a39ee-365">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="a39ee-365">Which should return:</span></span>
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

<span data-ttu-id="a39ee-366">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="a39ee-367">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="a39ee-368">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="a39ee-369">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a39ee-369">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="a39ee-370">**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a39ee-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="a39ee-371">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-371">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="a39ee-372">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="a39ee-372">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a39ee-373">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a39ee-373">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="a39ee-374">Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="a39ee-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="a39ee-375">Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="a39ee-376">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="a39ee-377">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="a39ee-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="a39ee-378">Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="a39ee-379">In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="a39ee-380">Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a39ee-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="a39ee-381">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="a39ee-382">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="a39ee-383">John Woods – Anrufe an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="a39ee-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="a39ee-384">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="a39ee-385">Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="a39ee-387">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="a39ee-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="a39ee-388">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="a39ee-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="a39ee-389">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a39ee-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="a39ee-391">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="a39ee-392">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="a39ee-392">**PSTN usage**</span></span>|<span data-ttu-id="a39ee-393">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="a39ee-393">**Voice route**</span></span>|<span data-ttu-id="a39ee-394">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="a39ee-394">**Number pattern**</span></span>|<span data-ttu-id="a39ee-395">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a39ee-395">**Priority**</span></span>|<span data-ttu-id="a39ee-396">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="a39ee-396">**SBC**</span></span>|<span data-ttu-id="a39ee-397">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a39ee-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a39ee-398">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-398">US Only</span></span>|<span data-ttu-id="a39ee-399">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="a39ee-399">"Redmond 1"</span></span>|<span data-ttu-id="a39ee-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a39ee-401">1</span><span class="sxs-lookup"><span data-stu-id="a39ee-401">1</span></span>|<span data-ttu-id="a39ee-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="a39ee-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="a39ee-404">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a39ee-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a39ee-405">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-405">US Only</span></span>|<span data-ttu-id="a39ee-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="a39ee-406">"Redmond 2"</span></span>|<span data-ttu-id="a39ee-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="a39ee-408">2</span><span class="sxs-lookup"><span data-stu-id="a39ee-408">2</span></span>|<span data-ttu-id="a39ee-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="a39ee-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="a39ee-411">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="a39ee-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="a39ee-412">Nur USA</span><span class="sxs-lookup"><span data-stu-id="a39ee-412">US Only</span></span>|<span data-ttu-id="a39ee-413">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="a39ee-413">"Other +1"</span></span>|<span data-ttu-id="a39ee-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="a39ee-415">3</span><span class="sxs-lookup"><span data-stu-id="a39ee-415">3</span></span>|<span data-ttu-id="a39ee-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="a39ee-417">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="a39ee-418">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="a39ee-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="a39ee-419">International</span><span class="sxs-lookup"><span data-stu-id="a39ee-419">International</span></span>|<span data-ttu-id="a39ee-420">International</span><span class="sxs-lookup"><span data-stu-id="a39ee-420">International</span></span>|<span data-ttu-id="a39ee-421">\d +</span><span class="sxs-lookup"><span data-stu-id="a39ee-421">\d+</span></span>|<span data-ttu-id="a39ee-422">4</span><span class="sxs-lookup"><span data-stu-id="a39ee-422">4</span></span>|<span data-ttu-id="a39ee-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="a39ee-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="a39ee-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="a39ee-425">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="a39ee-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="a39ee-426">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="a39ee-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="a39ee-427">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="a39ee-428">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="a39ee-429">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a39ee-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="a39ee-430">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a39ee-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="a39ee-431">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="a39ee-432">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="a39ee-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="a39ee-433">Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="a39ee-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="a39ee-434">Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


<span data-ttu-id="a39ee-435">**Schritt 1**: Erstellen der PSTN-Nutzung "International"</span><span class="sxs-lookup"><span data-stu-id="a39ee-435">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="a39ee-436">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="a39ee-437">**Schritt 2**: Erstellen der neuen VoIP-Route "International"</span><span class="sxs-lookup"><span data-stu-id="a39ee-437">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="a39ee-438">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a39ee-438">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="a39ee-439">**Schritt 3**: Erstellen einer VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="a39ee-439">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="a39ee-440">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="a39ee-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

<span data-ttu-id="a39ee-441">Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-441">Take note of the order of PSTN Usages:</span></span>

<span data-ttu-id="a39ee-442">a.</span><span class="sxs-lookup"><span data-stu-id="a39ee-442">a.</span></span> <span data-ttu-id="a39ee-443">Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-443">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="a39ee-444">Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a39ee-444">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

<span data-ttu-id="a39ee-445">b.</span><span class="sxs-lookup"><span data-stu-id="a39ee-445">b.</span></span> <span data-ttu-id="a39ee-446">Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-446">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="a39ee-447">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="a39ee-447">Enter the command:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

<span data-ttu-id="a39ee-448">Was zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="a39ee-448">Which returns</span></span>

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

<span data-ttu-id="a39ee-449">**Schritt 4**: weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-449">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="a39ee-450">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="a39ee-450">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="a39ee-451">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a39ee-451">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="a39ee-452">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="a39ee-452">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="a39ee-453">Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen</span><span class="sxs-lookup"><span data-stu-id="a39ee-453">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="a39ee-454">Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-454">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="a39ee-455">Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="a39ee-455">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="a39ee-456">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel zur Interoperabilität von Informationen zwischen Skype und Teams: [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business nutzen](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="a39ee-456">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="a39ee-457">Konfigurieren des direkten Sendens von Anrufen an Voicemail</span><span class="sxs-lookup"><span data-stu-id="a39ee-457">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="a39ee-458">Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-458">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="a39ee-459">Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an.</span><span class="sxs-lookup"><span data-stu-id="a39ee-459">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="a39ee-460">Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail".</span><span class="sxs-lookup"><span data-stu-id="a39ee-460">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="a39ee-461">In diesem Fall erhält der Nutzer der Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit dem Anrufbeantworter des Benutzers verbunden.</span><span class="sxs-lookup"><span data-stu-id="a39ee-461">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="a39ee-462">Übersetzen von Rufnummern für Anrufer und Anrufer für ausgehende und eingehende Anrufe in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="a39ee-462">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="a39ee-463">Manchmal möchten mandantenadministratoren die Anrufer-oder Rufnummernanzeige für ausgehende und/oder eingehende Anrufe basierend auf den von Ihnen erstellten Mustern ändern, um die Interoperabilität mit SBCS zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a39ee-463">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="a39ee-464">Sie können eine Richtlinie für die Übersetzungsregeln festlegen, um die Anrufer-oder Rufnummernanzeige in ein alternatives Format zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-464">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="a39ee-465">Sie können die Richtlinie verwenden, um Zahlen für Folgendes zu übersetzen:</span><span class="sxs-lookup"><span data-stu-id="a39ee-465">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="a39ee-466">Eingehende Anrufe: Anrufe von einem PSTN-Endpunkt (Anrufer) an einen Teams-Client (angerufener).</span><span class="sxs-lookup"><span data-stu-id="a39ee-466">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="a39ee-467">Ausgehende Anrufe: Anrufe von einem Team-Client (Anrufer) an einen PSTN-Endpunkt (angerufener).</span><span class="sxs-lookup"><span data-stu-id="a39ee-467">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="a39ee-468">Die Richtlinie wird auf der SBC-Ebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-468">The policy is applied at the SBC level.</span></span> <span data-ttu-id="a39ee-469">Sie können einem SBC mehrere Übersetzungsregeln zuweisen, die in der Reihenfolge angewendet werden, in der Sie angezeigt werden, wenn Sie Sie in PowerShell auflisten.</span><span class="sxs-lookup"><span data-stu-id="a39ee-469">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="a39ee-470">Sie können auch die Reihenfolge der Regeln in der Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="a39ee-470">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="a39ee-471">Zum Erstellen, ändern, anzeigen und Löschen von Regeln für die Nummern Manipulation verwenden Sie die Cmdlets New-CsTeamsTranslationRule, Sets-CsTeamsTranslationRule, Get-CsTeamsTranslationRule und Remove-CsTeamsTranslationRule.</span><span class="sxs-lookup"><span data-stu-id="a39ee-471">To create, modify, view, and delete number manipulation rules, use the New-CsTeamsTranslationRule, Set-CsTeamsTranslationRule, Get-CsTeamsTranslationRule, and Remove-CsTeamsTranslationRule cmdlets.</span></span>

<span data-ttu-id="a39ee-472">Zum zuweisen, konfigurieren und Auflisten von Regeln für die Nummern Manipulation auf SBCS verwenden Sie die Cmdlets [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) und [setCSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) zusammen ```InboundPSTNNumberTranslationRules```mit ```OutboundTeamsNumberTranslationRules```den ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList``` ```InboundTeamsNumberTranslationRules```,,,,, ```OutboundPSTNNumberTranslationRulesList``` ,, und Parametern.</span><span class="sxs-lookup"><span data-stu-id="a39ee-472">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="a39ee-473">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a39ee-473">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="a39ee-474">Beispiel-SBC-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a39ee-474">Example SBC configuration</span></span>

<span data-ttu-id="a39ee-475">In den Beispielszenarien führen wir das ```New-CsOnlinePSTNGateway``` Cmdlet aus, um die folgende SBC-Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-475">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="a39ee-476">Die dem SBC zugewiesenen Übersetzungsregeln sind in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="a39ee-476">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="a39ee-477">Name</span><span class="sxs-lookup"><span data-stu-id="a39ee-477">Name</span></span>  |<span data-ttu-id="a39ee-478">Muster</span><span class="sxs-lookup"><span data-stu-id="a39ee-478">Pattern</span></span> |<span data-ttu-id="a39ee-479">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="a39ee-479">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a39ee-480">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="a39ee-480">AddPlus1</span></span>     |<span data-ttu-id="a39ee-481">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-481">^(\d{10})$</span></span>          |<span data-ttu-id="a39ee-482">+1$1</span><span class="sxs-lookup"><span data-stu-id="a39ee-482">+1$1</span></span>          |
|<span data-ttu-id="a39ee-483">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="a39ee-483">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="a39ee-484">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-484">^(\d{4})$</span></span>          | <span data-ttu-id="a39ee-485">+ 1206555 $1</span><span class="sxs-lookup"><span data-stu-id="a39ee-485">+1206555$1</span></span>         |
|<span data-ttu-id="a39ee-486">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="a39ee-486">AddSeattleAreaCode</span></span>    |<span data-ttu-id="a39ee-487">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-487">^(\d{4})$</span></span>          | <span data-ttu-id="a39ee-488">425555 $1</span><span class="sxs-lookup"><span data-stu-id="a39ee-488">425555$1</span></span>         |
|<span data-ttu-id="a39ee-489">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="a39ee-489">StripPlus1</span></span>    |<span data-ttu-id="a39ee-490">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a39ee-490">^+1(\d{10})$</span></span>          | <span data-ttu-id="a39ee-491">$1</span><span class="sxs-lookup"><span data-stu-id="a39ee-491">$1</span></span>         |

<span data-ttu-id="a39ee-492">In diesen Beispielszenarien haben wir zwei Benutzer, Alice und Bob.</span><span class="sxs-lookup"><span data-stu-id="a39ee-492">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="a39ee-493">Alice ist ein Team Benutzer und Ihre Nummer ist + 1 206 555 0100.</span><span class="sxs-lookup"><span data-stu-id="a39ee-493">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="a39ee-494">Bob ist ein PSTN-Benutzer und seine Nummer ist + 1 425 555 0100.</span><span class="sxs-lookup"><span data-stu-id="a39ee-494">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="a39ee-495">Beispiel 1: eingehender Anruf an eine zehnstellige Zahl</span><span class="sxs-lookup"><span data-stu-id="a39ee-495">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="a39ee-496">Bob ruft Alice mit einer nicht-E. 164-zehnstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="a39ee-496">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="a39ee-497">Bob wählt 2065550100, um Alice zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-497">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="a39ee-498">SBC verwendet 2065550100 in den RequestURI und den Headern und 4255550100 im from-Header.</span><span class="sxs-lookup"><span data-stu-id="a39ee-498">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="a39ee-499">Header</span><span class="sxs-lookup"><span data-stu-id="a39ee-499">Header</span></span>  |<span data-ttu-id="a39ee-500">Original</span><span class="sxs-lookup"><span data-stu-id="a39ee-500">Original</span></span> |<span data-ttu-id="a39ee-501">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="a39ee-501">Translated header</span></span> |<span data-ttu-id="a39ee-502">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="a39ee-502">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a39ee-503">RequestURI</span><span class="sxs-lookup"><span data-stu-id="a39ee-503">RequestURI</span></span>  |<span data-ttu-id="a39ee-504">Einladen von SIP:2065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-504">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="a39ee-505">Einladen von SIP:+12065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-505">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="a39ee-506">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-506">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="a39ee-507">An</span><span class="sxs-lookup"><span data-stu-id="a39ee-507">TO</span></span>    |<span data-ttu-id="a39ee-508">An: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-508">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-509">An: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-509">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-510">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-510">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="a39ee-511">Von</span><span class="sxs-lookup"><span data-stu-id="a39ee-511">FROM</span></span>   |<span data-ttu-id="a39ee-512">Von: \<SIP:4255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-512">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-513">Von: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-513">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-514">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-514">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="a39ee-515">Beispiel 2: eingehende Anrufe an eine vierstellige Zahl</span><span class="sxs-lookup"><span data-stu-id="a39ee-515">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="a39ee-516">Bob ruft Alice mit einer vierstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="a39ee-516">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="a39ee-517">Bob wählt 0100, um Alice zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-517">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="a39ee-518">SBC verwendet 0100 in den RequestURI und den Headern und 4255550100 im from-Header.</span><span class="sxs-lookup"><span data-stu-id="a39ee-518">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="a39ee-519">Header</span><span class="sxs-lookup"><span data-stu-id="a39ee-519">Header</span></span>  |<span data-ttu-id="a39ee-520">Original</span><span class="sxs-lookup"><span data-stu-id="a39ee-520">Original</span></span> |<span data-ttu-id="a39ee-521">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="a39ee-521">Translated header</span></span> |<span data-ttu-id="a39ee-522">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="a39ee-522">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a39ee-523">RequestURI</span><span class="sxs-lookup"><span data-stu-id="a39ee-523">RequestURI</span></span>  |<span data-ttu-id="a39ee-524">Einladen von SIP:0100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-524">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="a39ee-525">Einladen von SIP:+12065550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-525">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="a39ee-526">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="a39ee-526">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="a39ee-527">An</span><span class="sxs-lookup"><span data-stu-id="a39ee-527">TO</span></span>    |<span data-ttu-id="a39ee-528">An: \<SIP:0100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-528">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-529">An: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-529">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-530">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="a39ee-530">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="a39ee-531">Von</span><span class="sxs-lookup"><span data-stu-id="a39ee-531">FROM</span></span>   |<span data-ttu-id="a39ee-532">Von: \<SIP:4255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-532">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-533">Von: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-533">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-534">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-534">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="a39ee-535">Beispiel 3: ausgehender Anruf mit einer zehnstelligen nicht-E. 164-Nummer</span><span class="sxs-lookup"><span data-stu-id="a39ee-535">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="a39ee-536">Alice ruft Bob mit einer zehnstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="a39ee-536">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="a39ee-537">Alice wählt 425 555 0100, um Bob zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-537">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="a39ee-538">SBC ist für die Verwendung von nicht-E. 164-Nummern für Teams und PSTN-Benutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a39ee-538">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="a39ee-539">In diesem Szenario übersetzt ein Wählplan die Nummer vor dem Senden an die direkte Routing Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a39ee-539">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="a39ee-540">Wenn Alice in den Teams-Client 425 555 0100 eingibt, wird die Nummer im Länder Wählplan in + 14255550100 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="a39ee-540">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="a39ee-541">Bei den resultierenden Zahlen handelt es sich um eine kumulative Normalisierung der Wähl Plan Regeln und der Übersetzungsregeln für Teams.</span><span class="sxs-lookup"><span data-stu-id="a39ee-541">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="a39ee-542">Die Übersetzungsregeln für Teams entfernen das "+ 1", das vom Wählplan hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="a39ee-542">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="a39ee-543">Header</span><span class="sxs-lookup"><span data-stu-id="a39ee-543">Header</span></span>  |<span data-ttu-id="a39ee-544">Original</span><span class="sxs-lookup"><span data-stu-id="a39ee-544">Original</span></span> |<span data-ttu-id="a39ee-545">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="a39ee-545">Translated header</span></span> |<span data-ttu-id="a39ee-546">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="a39ee-546">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a39ee-547">RequestURI</span><span class="sxs-lookup"><span data-stu-id="a39ee-547">RequestURI</span></span>  |<span data-ttu-id="a39ee-548">Einladen von SIP:+14255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-548">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="a39ee-549">Einladen von SIP:4255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-549">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="a39ee-550">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-550">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="a39ee-551">An</span><span class="sxs-lookup"><span data-stu-id="a39ee-551">TO</span></span>    |<span data-ttu-id="a39ee-552">An: \<SIP:+14255550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-552">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-553">An: \<SIP:4255555555@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-553">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-554">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-554">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="a39ee-555">Von</span><span class="sxs-lookup"><span data-stu-id="a39ee-555">FROM</span></span>   |<span data-ttu-id="a39ee-556">Von: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-556">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-557">Von: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-557">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-558">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-558">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="a39ee-559">Beispiel 4: Outbound-Anruf mit einer vierstelligen nicht-E. 164-Nummer</span><span class="sxs-lookup"><span data-stu-id="a39ee-559">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="a39ee-560">Alice ruft Bob mit einer vierstelligen Zahl an.</span><span class="sxs-lookup"><span data-stu-id="a39ee-560">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="a39ee-561">Alice verwendet 0100, um Bob von anrufen oder über einen Kontakt zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a39ee-561">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="a39ee-562">SBC ist für die Verwendung von nicht-E. 164-vierstelligen Zahlen für Teams-Benutzer und zehnstellige Zahlen für PSTN-Benutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a39ee-562">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="a39ee-563">In diesem Szenario wird der Wählplan nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="a39ee-563">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="a39ee-564">Header</span><span class="sxs-lookup"><span data-stu-id="a39ee-564">Header</span></span>  |<span data-ttu-id="a39ee-565">Original</span><span class="sxs-lookup"><span data-stu-id="a39ee-565">Original</span></span> |<span data-ttu-id="a39ee-566">Übersetzte Kopfzeile</span><span class="sxs-lookup"><span data-stu-id="a39ee-566">Translated header</span></span> |<span data-ttu-id="a39ee-567">Parameter und Regel angewendet</span><span class="sxs-lookup"><span data-stu-id="a39ee-567">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a39ee-568">RequestURI</span><span class="sxs-lookup"><span data-stu-id="a39ee-568">RequestURI</span></span>  |<span data-ttu-id="a39ee-569">Einladen von SIP:0100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-569">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="a39ee-570">Einladen von SIP:4255550100@SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a39ee-570">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="a39ee-571">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="a39ee-571">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="a39ee-572">An</span><span class="sxs-lookup"><span data-stu-id="a39ee-572">TO</span></span>    |<span data-ttu-id="a39ee-573">An: \<SIP:0100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-573">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-574">An: \<SIP:4255555555@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-574">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-575">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="a39ee-575">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="a39ee-576">Von</span><span class="sxs-lookup"><span data-stu-id="a39ee-576">FROM</span></span>   |<span data-ttu-id="a39ee-577">Von: \<SIP:+12065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-577">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="a39ee-578">Von: \<SIP:2065550100@SBC.contoso.com></span><span class="sxs-lookup"><span data-stu-id="a39ee-578">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="a39ee-579">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="a39ee-579">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="a39ee-580">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a39ee-580">See also</span></span>

[<span data-ttu-id="a39ee-581">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="a39ee-581">Plan Direct Routing</span></span>](direct-routing-plan.md)
