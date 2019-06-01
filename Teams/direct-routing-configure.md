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
ms.openlocfilehash: 5835357a283c80c4dc5a99310ab2d527e55a8bdb
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "34667498"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="4c70b-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="4c70b-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="4c70b-104">Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des direkten Routings, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="4c70b-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="4c70b-105">Wenn Sie dies noch nicht getan haben, lesen Sie [Planen des direkten Routings](direct-routing-plan.md) für Voraussetzungen und zum Überprüfen weiterer Schritte, die Sie ausführen müssen, bevor Sie Ihr Microsoft Phone-System Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="4c70b-106">In diesem Artikel wird beschrieben, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="4c70b-107">Sie erfahren, wie Sie einen unterstützten Session Border Controller (SBC) mit Direct Routing koppeln und wie Microsoft Teams-Benutzer so konfiguriert werden, dass Sie die direkte Weiterleitung zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4c70b-108">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4c70b-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="4c70b-109">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c70b-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="4c70b-110">Wir empfehlen, dass Sie sicherstellen, dass Ihr SBC bereits gemäß den Empfehlungen Ihres SBC-Herstellers konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="4c70b-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="4c70b-111">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="4c70b-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4c70b-112">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="4c70b-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="4c70b-113">Sie können Ihr Microsoft Phone-System konfigurieren und Benutzern die Verwendung des direkten Routings ermöglichen und anschließend Microsoft Teams als bevorzugten Anruf Client einrichten, indem Sie die folgenden Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="4c70b-114">Koppeln des SBC mit einem Microsoft Phone-System und Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="4c70b-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="4c70b-115">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="4c70b-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="4c70b-116">Sicherstellen, dass Microsoft Teams der bevorzugte Anruf Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="4c70b-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="4c70b-117">Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems</span><span class="sxs-lookup"><span data-stu-id="4c70b-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="4c70b-118">Im folgenden werden die drei allgemeinen Schritte beschrieben, mit denen Sie den SBC mit der direkten Routing Schnittstelle verbinden oder koppeln können:</span><span class="sxs-lookup"><span data-stu-id="4c70b-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="4c70b-119">Herstellen einer Verbindung mit dem **Skype for Business Online** Admin Center mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c70b-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="4c70b-120">Koppeln des SBC</span><span class="sxs-lookup"><span data-stu-id="4c70b-120">Pair the SBC</span></span> 
- <span data-ttu-id="4c70b-121">Überprüfen der Kopplung</span><span class="sxs-lookup"><span data-stu-id="4c70b-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="4c70b-122">Herstellen einer Verbindung mit Skype for Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c70b-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="4c70b-123">Sie können eine mit dem Mandanten verbundene PowerShell-Sitzung verwenden, um den SBC mit der direkten Routing Schnittstelle zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="4c70b-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="4c70b-124">Wenn Sie eine PowerShell-Sitzung öffnen möchten, führen Sie die Schritte unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)aus.</span><span class="sxs-lookup"><span data-stu-id="4c70b-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="4c70b-125">Nachdem Sie eine Remote-PowerShell-Sitzung erstellt haben, überprüfen Sie, ob Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="4c70b-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="4c70b-126">Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung Folgendes ein, oder kopieren/fügen Sie Sie ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4c70b-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="4c70b-127">Ihr Befehl gibt die vier hier gezeigten Funktionen zurück, mit denen Sie den SBC verwalten können.</span><span class="sxs-lookup"><span data-stu-id="4c70b-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="4c70b-128">Koppeln des SBC mit dem Mandanten</span><span class="sxs-lookup"><span data-stu-id="4c70b-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="4c70b-129">Wenn Sie den SBC mit dem Mandanten koppeln möchten, geben Sie in der PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4c70b-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="4c70b-130">Es wird dringend empfohlen, im SBC eine maximale Anruf Grenze zu verwenden, die Informationen enthält, die in der SBC-Dokumentation zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="4c70b-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="4c70b-131">Der Grenzwert löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitäts Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="4c70b-132">Sie können den SBC nur koppeln, wenn der Domänenteil des FQDN mit einer der in Ihrem Mandanten registrierten Domänen übereinstimmt \*, mit Ausnahme von onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4c70b-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="4c70b-133">Die \*Verwendung von onmicrosoft.com-Domänennamen wird für den Namen des SBC-FQDN nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c70b-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="4c70b-134">Wenn Sie beispielsweise über zwei Domänennamen verfügen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="4c70b-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="4c70b-135">**contoso**.com</span></span><br/><span data-ttu-id="4c70b-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4c70b-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="4c70b-137">Für den SBC-Namen können Sie den Namen SBC.contoso.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="4c70b-138">Wenn Sie versuchen, den SBC mit einem Namen SBC. contoso. ABC zu koppeln, lässt das System Sie nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="4c70b-139">Gibt</span><span class="sxs-lookup"><span data-stu-id="4c70b-139">Returns:</span></span>
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
<span data-ttu-id="4c70b-140">Es gibt weitere Optionen, die während des kopplungsvorgangs festgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4c70b-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="4c70b-141">Im vorherigen Beispiel werden jedoch nur die erforderlichen Mindestparameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c70b-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="4c70b-142">In der folgenden Tabelle sind die zusätzlichen Parameter aufgeführt, die Sie beim Festlegen von Parametern für verwenden können.`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="4c70b-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="4c70b-143">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="4c70b-143">Required?</span></span>|<span data-ttu-id="4c70b-144">Name</span><span class="sxs-lookup"><span data-stu-id="4c70b-144">Name</span></span>|<span data-ttu-id="4c70b-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c70b-145">Description</span></span>|<span data-ttu-id="4c70b-146">Standard</span><span class="sxs-lookup"><span data-stu-id="4c70b-146">Default</span></span>|<span data-ttu-id="4c70b-147">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="4c70b-147">Possible values</span></span>|<span data-ttu-id="4c70b-148">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4c70b-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c70b-149">Ja</span><span class="sxs-lookup"><span data-stu-id="4c70b-149">Yes</span></span>|<span data-ttu-id="4c70b-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="4c70b-150">FQDN</span></span>|<span data-ttu-id="4c70b-151">Der FQDN-Name des SBC</span><span class="sxs-lookup"><span data-stu-id="4c70b-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="4c70b-152">Keine</span><span class="sxs-lookup"><span data-stu-id="4c70b-152">None</span></span>|<span data-ttu-id="4c70b-153">NoneFQDN-Name, 63-Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="4c70b-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="4c70b-154">Zeichenfolge, Liste der zulässigen und nicht zulässigen Zeichen für Benennungs [Konventionen in Active Directory für Computer, Domänen, Websites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="4c70b-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="4c70b-155">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-155">No</span></span>|<span data-ttu-id="4c70b-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="4c70b-156">MediaBypass</span></span> |<span data-ttu-id="4c70b-157">Der Parameter, der für die spätere Verwendung reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-157">The parameter reserved for future use.</span></span> <span data-ttu-id="4c70b-158">Der vom SBC angegebene Parameter unterstützt die medienumgehung, und der Administrator möchte ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="4c70b-159">Keine</span><span class="sxs-lookup"><span data-stu-id="4c70b-159">None</span></span>|<span data-ttu-id="4c70b-160">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-160">True</span></span><br/><span data-ttu-id="4c70b-161">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-161">False</span></span>|<span data-ttu-id="4c70b-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="4c70b-162">Boolean</span></span>|
|<span data-ttu-id="4c70b-163">Ja</span><span class="sxs-lookup"><span data-stu-id="4c70b-163">Yes</span></span>|<span data-ttu-id="4c70b-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="4c70b-164">SipSignallingPort</span></span> |<span data-ttu-id="4c70b-165">Der für die Kommunikation mit Direct Routing Services verwendete Überwachungs Port mithilfe des TLS-Protokolls (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="4c70b-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="4c70b-166">Keine</span><span class="sxs-lookup"><span data-stu-id="4c70b-166">None</span></span>|<span data-ttu-id="4c70b-167">Beliebiger Port</span><span class="sxs-lookup"><span data-stu-id="4c70b-167">Any port</span></span>|<span data-ttu-id="4c70b-168">0 bis 65535</span><span class="sxs-lookup"><span data-stu-id="4c70b-168">0 to 65535</span></span> |
|<span data-ttu-id="4c70b-169">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-169">No</span></span>|<span data-ttu-id="4c70b-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="4c70b-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="4c70b-171">Bei Festlegung auf 10 (Standardwert) werden ausgehende Anrufe, die nicht innerhalb von 10 Sekunden vom Gateway beantwortet werden, an den nächsten verfügbaren trunk weitergeleitet; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4c70b-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="4c70b-172">In einer Organisation mit langsamen Netzwerken und Gateway-Antworten kann dies potenziell dazu führen, dass Anrufe unnötig fallen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="4c70b-173">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="4c70b-173">The default value is 10.</span></span>|<span data-ttu-id="4c70b-174">10</span><span class="sxs-lookup"><span data-stu-id="4c70b-174">10</span></span>|<span data-ttu-id="4c70b-175">Nummer</span><span class="sxs-lookup"><span data-stu-id="4c70b-175">Number</span></span>|<span data-ttu-id="4c70b-176">Int</span><span class="sxs-lookup"><span data-stu-id="4c70b-176">Int</span></span>|
|<span data-ttu-id="4c70b-177">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-177">No</span></span>|<span data-ttu-id="4c70b-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="4c70b-178">ForwardCallHistory</span></span> |<span data-ttu-id="4c70b-179">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="4c70b-180">Wenn diese Option aktiviert ist, sendet der Office 365-PSTN-Proxy zwei Überschriften: Verlaufsinformationen und weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="4c70b-181">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="4c70b-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="4c70b-182">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-182">False</span></span>|<span data-ttu-id="4c70b-183">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-183">True</span></span><br/><span data-ttu-id="4c70b-184">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-184">False</span></span>|<span data-ttu-id="4c70b-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="4c70b-185">Boolean</span></span>|
|<span data-ttu-id="4c70b-186">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-186">No</span></span>|<span data-ttu-id="4c70b-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="4c70b-187">ForwardPAI</span></span>|<span data-ttu-id="4c70b-188">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="4c70b-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="4c70b-189">Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="4c70b-190">Wenn aktiviert, wird auch der Datenschutz: ID-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="4c70b-191">Der Standardwert ist **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="4c70b-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="4c70b-192">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-192">False</span></span>|<span data-ttu-id="4c70b-193">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-193">True</span></span><br/><span data-ttu-id="4c70b-194">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-194">False</span></span>|<span data-ttu-id="4c70b-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="4c70b-195">Boolean</span></span>|
|<span data-ttu-id="4c70b-196">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-196">No</span></span>|<span data-ttu-id="4c70b-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="4c70b-197">SendSIPOptions</span></span> |<span data-ttu-id="4c70b-198">Definiert, ob die SIP-Optionen von einem SBC gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="4c70b-199">Wenn diese Option deaktiviert ist, wird der SBC vom Überwachungs-und Warnungssystem ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="4c70b-200">Wir empfehlen dringend, SIP-Optionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="4c70b-201">Der Standardwert ist **wahr**.</span><span class="sxs-lookup"><span data-stu-id="4c70b-201">Default value is **True**.</span></span> |<span data-ttu-id="4c70b-202">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-202">True</span></span>|<span data-ttu-id="4c70b-203">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-203">True</span></span><br/><span data-ttu-id="4c70b-204">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-204">False</span></span>|<span data-ttu-id="4c70b-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="4c70b-205">Boolean</span></span>|
|<span data-ttu-id="4c70b-206">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-206">No</span></span>|<span data-ttu-id="4c70b-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="4c70b-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="4c70b-208">Wird vom Warnungssystem verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-208">Used by alerting system.</span></span> <span data-ttu-id="4c70b-209">Wenn ein beliebiger Wert gesetzt ist, generiert das Warnungssystem eine Benachrichtigung an den mandantenadministrator, wenn die Anzahl der gleichzeitigen Sitzungen 90% oder höher als dieser Wert ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="4c70b-210">Wenn Parameter nicht gesetzt ist, werden die Benachrichtigungen nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="4c70b-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="4c70b-211">Das Überwachungssystem meldet jedoch die Anzahl der gleichzeitigen Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="4c70b-212">NULL</span><span class="sxs-lookup"><span data-stu-id="4c70b-212">Null</span></span>|<span data-ttu-id="4c70b-213">NULL</span><span class="sxs-lookup"><span data-stu-id="4c70b-213">Null</span></span><br/><span data-ttu-id="4c70b-214">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="4c70b-214">1 to 100,000</span></span> ||
|<span data-ttu-id="4c70b-215">Nein</span><span class="sxs-lookup"><span data-stu-id="4c70b-215">No</span></span>|<span data-ttu-id="4c70b-216">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="4c70b-216">Enabled\*</span></span>|<span data-ttu-id="4c70b-217">Wird verwendet, um diesen SBC für ausgehende Anrufe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="4c70b-218">Kann verwendet werden, um den SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="4c70b-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="4c70b-219">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-219">False</span></span>|<span data-ttu-id="4c70b-220">True</span><span class="sxs-lookup"><span data-stu-id="4c70b-220">True</span></span><br/><span data-ttu-id="4c70b-221">Falsch</span><span class="sxs-lookup"><span data-stu-id="4c70b-221">False</span></span>|<span data-ttu-id="4c70b-222">Boolean</span><span class="sxs-lookup"><span data-stu-id="4c70b-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="4c70b-223">Überprüfen der SBC-Kopplung</span><span class="sxs-lookup"><span data-stu-id="4c70b-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="4c70b-224">Überprüfen Sie die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="4c70b-224">Verify the connection:</span></span> 
- <span data-ttu-id="4c70b-225">Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCS befindet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="4c70b-226">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="4c70b-227">Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCS befindet</span><span class="sxs-lookup"><span data-stu-id="4c70b-227">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="4c70b-228">Nachdem Sie den SBC gekoppelt haben, überprüfen Sie, ob der SBC in der Liste der gekoppelten SBCS vorhanden ist, indem Sie den folgenden Befehl in einer Remote-PowerShell-Sitzung ausführen:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="4c70b-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="4c70b-229">Das gekoppelte Gateway sollte in der Liste angezeigt werden, wie im folgenden Beispiel gezeigt, und überprüfen, ob der Parameter *Enabled* den Wert **true**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4c70b-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="4c70b-230">Eingeben</span><span class="sxs-lookup"><span data-stu-id="4c70b-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="4c70b-231">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4c70b-231">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="4c70b-232">Überprüfen des SIP-Options Flusses</span><span class="sxs-lookup"><span data-stu-id="4c70b-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="4c70b-233">Um die Kopplung mithilfe der ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200-OK-Antworten auf die Nachrichten der ausgehenden Optionen erhält.</span><span class="sxs-lookup"><span data-stu-id="4c70b-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="4c70b-234">Wenn für das direkte Routing eingehende Optionen angezeigt werden, wird das Senden von ausgehenden SIP-Optionen Nachrichten an den SBC-FQDN gesendet, der im Feld Kontakt Kopf in der Nachricht eingehende Optionen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="4c70b-235">Wenn Sie die Kopplung mithilfe der eingehenden SIP-Optionen überprüfen möchten, verwenden Sie die SBC-Verwaltungsschnittstelle, und sehen Sie, dass der SBC eine Antwort auf die Options Nachrichten sendet, die vom direkten Routing eingehen, und dass der von ihm gesendete Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="4c70b-236">Aktivieren von Benutzern für Direct Routing Service</span><span class="sxs-lookup"><span data-stu-id="4c70b-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="4c70b-237">Wenn Sie bereit sind, Benutzer für den direkt Routing Dienst zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4c70b-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="4c70b-238">Erstellen Sie einen Benutzer in Office 365, und weisen Sie eine Telefonsystem Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="4c70b-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="4c70b-239">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4c70b-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="4c70b-240">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="4c70b-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="4c70b-241">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="4c70b-241">Configure voice routing.</span></span> <span data-ttu-id="4c70b-242">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="4c70b-242">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="4c70b-243">Erstellen eines Benutzers in Office 365 und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="4c70b-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="4c70b-244">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c70b-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="4c70b-245">Es wird jedoch empfohlen, dass Ihre Organisation eine Option auswählen und verwenden, um Routingprobleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="4c70b-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="4c70b-246">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="4c70b-246">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="4c70b-247">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="4c70b-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="4c70b-248">Erstellen Sie den Benutzer direkt im Office 365-Administrator Portal.</span><span class="sxs-lookup"><span data-stu-id="4c70b-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="4c70b-249">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Office 365 – Hilfe für Administratoren](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="4c70b-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="4c70b-250">Wenn Ihre Skype for Business Online-Bereitstellung zusammen mit Skype for Business 2015 oder lync 2010/2013 lokal vorhanden ist, besteht die einzige unterstützte Option darin, den Benutzer in lokales Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="4c70b-250">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="4c70b-251">Erforderliche Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-251">Required licenses:</span></span> 

- <span data-ttu-id="4c70b-252">Office 365 Enterprise E3 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2 und Teams) + Telefon System</span><span class="sxs-lookup"><span data-stu-id="4c70b-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="4c70b-253">Office 365 Enterprise E5 (einschließlich SFB Aktionsplan2, Exchange Aktionsplan2, Teams und Telefon System)</span><span class="sxs-lookup"><span data-stu-id="4c70b-253">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="4c70b-254">Optionale Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-254">Optional licenses:</span></span> 

- <span data-ttu-id="4c70b-255">Anrufplan</span><span class="sxs-lookup"><span data-stu-id="4c70b-255">Calling Plan</span></span> 
- <span data-ttu-id="4c70b-256">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="4c70b-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="4c70b-257">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4c70b-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="4c70b-258">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="4c70b-259">Sie können dies überprüfen, indem Sie den RegistrarPool-Parameter betrachten.</span><span class="sxs-lookup"><span data-stu-id="4c70b-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="4c70b-260">Sie muss einen Wert in der Infra.lync.com-Domäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="4c70b-261">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c70b-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="4c70b-262">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="4c70b-263">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="4c70b-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="4c70b-264">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, Ihre Telefonnummer und Voicemail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="4c70b-265">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-265">This can be done in one step.</span></span> 

<span data-ttu-id="4c70b-266">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="4c70b-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="4c70b-267">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="4c70b-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="4c70b-268">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-268">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="4c70b-269">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-269">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="4c70b-270">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4c70b-271">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c70b-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="4c70b-272">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="4c70b-272">Configure Voice Routing</span></span> 

<span data-ttu-id="4c70b-273">Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten SBC basierend auf folgenden Informationen gesendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="4c70b-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="4c70b-274">Als Zahlenmuster bezeichnet</span><span class="sxs-lookup"><span data-stu-id="4c70b-274">Called number pattern</span></span> 
- <span data-ttu-id="4c70b-275">Namens Zahlenmuster + bestimmter Nutzer, der den Anruf tätigt</span><span class="sxs-lookup"><span data-stu-id="4c70b-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="4c70b-276">SBCS kann als aktiv und als Backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="4c70b-277">Das bedeutet, wenn der SBC, der für dieses Zahlenmuster oder Zahlenmuster + bestimmten Benutzer als aktiv konfiguriert ist, nicht verfügbar ist, werden die Anrufe an eine Sicherungs-SBC weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="4c70b-278">Das Anrufrouting besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="4c70b-279">VoIP-Routing Richtlinie – Container für PSTN-Nutzungen; kann einem Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="4c70b-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="4c70b-280">PSTN-Nutzungen – Container für sprach Routen und PSTN-Nutzungen; kann in verschiedenen VoIP-Routing Richtlinien freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="4c70b-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="4c70b-281">VoIP-Routen – Nummernmuster und Satz von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="4c70b-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="4c70b-282">Online-PSTN-Gateway – Zeiger auf einen SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Aufruf über den SBC erfolgt, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="4c70b-282">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="4c70b-283">Erstellen einer VoIP-Routing Richtlinie mit einer PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="4c70b-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="4c70b-284">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien im Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="4c70b-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="4c70b-285">**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-285">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4c70b-286">Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-286">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="4c70b-287">**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-287">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="4c70b-288">Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="4c70b-288">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="4c70b-289">Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="4c70b-291">In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c70b-292">Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4c70b-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="4c70b-293">Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="4c70b-294">Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.</span><span class="sxs-lookup"><span data-stu-id="4c70b-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="4c70b-295">In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).</span><span class="sxs-lookup"><span data-stu-id="4c70b-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="4c70b-297">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="4c70b-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4c70b-298">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="4c70b-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4c70b-299">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4c70b-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c70b-300">Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da es nur eine Route gibt, die dem Muster + 1 XXX XXX XX XX entspricht.</span><span class="sxs-lookup"><span data-stu-id="4c70b-300">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="4c70b-301">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="4c70b-302">In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4c70b-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="4c70b-303">In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="4c70b-303">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="4c70b-304">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="4c70b-304">**PSTN usage**</span></span>|<span data-ttu-id="4c70b-305">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="4c70b-305">**Voice route**</span></span>|<span data-ttu-id="4c70b-306">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="4c70b-306">**Number pattern**</span></span>|<span data-ttu-id="4c70b-307">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="4c70b-307">**Priority**</span></span>|<span data-ttu-id="4c70b-308">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="4c70b-308">**SBC**</span></span>|<span data-ttu-id="4c70b-309">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4c70b-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c70b-310">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-310">US only</span></span>|<span data-ttu-id="4c70b-311">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4c70b-311">"Redmond 1"</span></span>|<span data-ttu-id="4c70b-312">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4c70b-313">1</span><span class="sxs-lookup"><span data-stu-id="4c70b-313">1</span></span>|<span data-ttu-id="4c70b-314">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-314">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4c70b-315">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-315">sbc2.contoso.biz</span></span>|<span data-ttu-id="4c70b-316">Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4c70b-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4c70b-317">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-317">US only</span></span>|<span data-ttu-id="4c70b-318">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4c70b-318">"Redmond 2"</span></span>|<span data-ttu-id="4c70b-319">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4c70b-320">2</span><span class="sxs-lookup"><span data-stu-id="4c70b-320">2</span></span>|<span data-ttu-id="4c70b-321">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-321">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4c70b-322">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-322">sbc4.contoso.biz</span></span>|<span data-ttu-id="4c70b-323">Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4c70b-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4c70b-324">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-324">US only</span></span>|<span data-ttu-id="4c70b-325">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="4c70b-325">"Other +1"</span></span>|<span data-ttu-id="4c70b-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4c70b-327">3</span><span class="sxs-lookup"><span data-stu-id="4c70b-327">3</span></span>|<span data-ttu-id="4c70b-328">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-328">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4c70b-329">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-329">sbc6.contoso.biz</span></span>|<span data-ttu-id="4c70b-330">Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4c70b-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="4c70b-331">Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-331">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="4c70b-332">In diesem Beispiel wird die VoIP-Routing Richtlinie Benutzer Spencer Low zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="4c70b-333">Beispiele für Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="4c70b-333">Examples of call routes</span></span>

<span data-ttu-id="4c70b-334">Im folgenden Beispiel wird gezeigt, wie Sie Routen, PSTN-Nutzungen und Routing Richtlinien konfigurieren, und wir weisen die Richtlinie dem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="4c70b-334">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="4c70b-335">**Schritt 1:** Erstellen Sie die PSTN-Nutzung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="4c70b-335">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="4c70b-336">Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-336">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="4c70b-337">Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="4c70b-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="4c70b-338">Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="4c70b-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="4c70b-339">Im folgenden Beispiel wird das Ergebnis der Ausführung des PowerShell-Befehls `(Get-CSOnlinePSTNUsage).usage` zum Anzeigen von vollständigen Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c70b-339">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="4c70b-340">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c70b-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="4c70b-341">Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-341">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="4c70b-342">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4c70b-342">Which returns:</span></span>
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
<span data-ttu-id="4c70b-343">Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4c70b-344">Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="4c70b-345">Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="4c70b-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="4c70b-346">Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="4c70b-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="4c70b-347">In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. Verwenden Sie bitte-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="4c70b-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="4c70b-348">Alle Anrufe an denselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="4c70b-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="4c70b-349">Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="4c70b-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="4c70b-350">Was zurückgegeben werden sollte:</span><span class="sxs-lookup"><span data-stu-id="4c70b-350">Which should return:</span></span>
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

<span data-ttu-id="4c70b-351">Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-351">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="4c70b-352">**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.</span><span class="sxs-lookup"><span data-stu-id="4c70b-352">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="4c70b-353">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4c70b-354">Das Ergebnis wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4c70b-354">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="4c70b-355">**Schritt 4:** Erteilen Sie dem Benutzer Spencer Low eine VoIP-Routing Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c70b-355">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="4c70b-356">Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-356">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="4c70b-357">Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="4c70b-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="4c70b-358">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4c70b-358">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="4c70b-359">Erstellen einer VoIP-Routing Richtlinie mit mehreren PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="4c70b-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="4c70b-360">Die zuvor erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada, es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="4c70b-361">Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-361">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="4c70b-362">Die Richtlinie verwendet die im vorherigen Beispiel erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.</span><span class="sxs-lookup"><span data-stu-id="4c70b-362">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="4c70b-363">Damit werden alle weiteren Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-363">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="4c70b-364">In den Beispielen, die angezeigt werden, weisen Sie den Benutzern nur die Richtlinie "Spencer Low" und keine Einschränkungen für den Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="4c70b-364">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="4c70b-365">Spencer Low – Anrufe, die nur für US-und kanadische Rufnummern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="4c70b-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="4c70b-366">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-366">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4c70b-367">Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="4c70b-368">John Woods – Anrufe an beliebige Rufnummern zulässig.</span><span class="sxs-lookup"><span data-stu-id="4c70b-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="4c70b-369">Beim Anrufen in den Redmond-Nummernbereich muss der spezifische SBC-Satz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-369">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4c70b-370">Nicht-US-Nummern werden über sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-370">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="4c70b-372">Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan).</span><span class="sxs-lookup"><span data-stu-id="4c70b-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4c70b-373">Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, Route über den Microsoft-Anrufplan.</span><span class="sxs-lookup"><span data-stu-id="4c70b-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4c70b-374">Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4c70b-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="4c70b-376">Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-376">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="4c70b-377">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="4c70b-377">**PSTN usage**</span></span>|<span data-ttu-id="4c70b-378">**VoIP-Route**</span><span class="sxs-lookup"><span data-stu-id="4c70b-378">**Voice route**</span></span>|<span data-ttu-id="4c70b-379">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="4c70b-379">**Number pattern**</span></span>|<span data-ttu-id="4c70b-380">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="4c70b-380">**Priority**</span></span>|<span data-ttu-id="4c70b-381">**Sbchttps**</span><span class="sxs-lookup"><span data-stu-id="4c70b-381">**SBC**</span></span>|<span data-ttu-id="4c70b-382">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4c70b-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c70b-383">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-383">US Only</span></span>|<span data-ttu-id="4c70b-384">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="4c70b-384">"Redmond 1"</span></span>|<span data-ttu-id="4c70b-385">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-385">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4c70b-386">1</span><span class="sxs-lookup"><span data-stu-id="4c70b-386">1</span></span>|<span data-ttu-id="4c70b-387">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-387">sbc1.contoso.biz</span></span><br/><span data-ttu-id="4c70b-388">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-388">sbc2.contoso.biz</span></span>|<span data-ttu-id="4c70b-389">Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4c70b-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4c70b-390">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-390">US Only</span></span>|<span data-ttu-id="4c70b-391">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="4c70b-391">"Redmond 2"</span></span>|<span data-ttu-id="4c70b-392">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-392">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4c70b-393">2</span><span class="sxs-lookup"><span data-stu-id="4c70b-393">2</span></span>|<span data-ttu-id="4c70b-394">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-394">sbc3.contoso.biz</span></span><br/><span data-ttu-id="4c70b-395">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-395">sbc4.contoso.biz</span></span>|<span data-ttu-id="4c70b-396">Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="4c70b-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4c70b-397">Nur USA</span><span class="sxs-lookup"><span data-stu-id="4c70b-397">US Only</span></span>|<span data-ttu-id="4c70b-398">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="4c70b-398">"Other +1"</span></span>|<span data-ttu-id="4c70b-399">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4c70b-399">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4c70b-400">3</span><span class="sxs-lookup"><span data-stu-id="4c70b-400">3</span></span>|<span data-ttu-id="4c70b-401">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-401">sbc5.contoso.biz</span></span><br/><span data-ttu-id="4c70b-402">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-402">sbc6>.contoso.biz</span></span>|<span data-ttu-id="4c70b-403">Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="4c70b-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="4c70b-404">International</span><span class="sxs-lookup"><span data-stu-id="4c70b-404">International</span></span>|<span data-ttu-id="4c70b-405">International</span><span class="sxs-lookup"><span data-stu-id="4c70b-405">International</span></span>|<span data-ttu-id="4c70b-406">\d +</span><span class="sxs-lookup"><span data-stu-id="4c70b-406">\d+</span></span>|<span data-ttu-id="4c70b-407">4</span><span class="sxs-lookup"><span data-stu-id="4c70b-407">4</span></span>|<span data-ttu-id="4c70b-408">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-408">sbc2.contoso.biz</span></span><br/><span data-ttu-id="4c70b-409">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4c70b-409">sbc5.contoso.biz</span></span>|<span data-ttu-id="4c70b-410">Route für beliebige Zahlenmuster</span><span class="sxs-lookup"><span data-stu-id="4c70b-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="4c70b-411">Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch.</span><span class="sxs-lookup"><span data-stu-id="4c70b-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="4c70b-412">Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4c70b-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="4c70b-413">Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-413">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="4c70b-414">Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4c70b-414">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="4c70b-415">Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4c70b-415">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="4c70b-416">Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-416">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="4c70b-417">Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.</span><span class="sxs-lookup"><span data-stu-id="4c70b-417">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="4c70b-418">Beispiel für eine VoIP-Routing Richtlinie für Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="4c70b-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="4c70b-419">Die Schritte zum Erstellen der PSTN-Nutzung "International", VoIP-Route "International", "VoIP-Routing-Richtlinie" ohne Einschränkungen, und dann dem Benutzer "John Woods" zuweisen, sind wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4c70b-419">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="4c70b-420">Erstellen Sie zunächst die PSTN-Nutzung "International".</span><span class="sxs-lookup"><span data-stu-id="4c70b-420">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="4c70b-421">Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4c70b-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="4c70b-422">Erstellen Sie als nächstes die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="4c70b-422">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="4c70b-423">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4c70b-423">Which returns:</span></span>

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
3. <span data-ttu-id="4c70b-424">Erstellen Sie als nächstes eine VoIP-Routing Richtlinie "keine Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="4c70b-424">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="4c70b-425">Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4c70b-425">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="4c70b-426">Was zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="4c70b-426">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="4c70b-427">Weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.</span><span class="sxs-lookup"><span data-stu-id="4c70b-427">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="4c70b-428">Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="4c70b-428">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="4c70b-429">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4c70b-429">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="4c70b-430">Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.</span><span class="sxs-lookup"><span data-stu-id="4c70b-430">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="4c70b-431">Microsoft Teams als bevorzugten Anruf Client für Benutzer einrichten</span><span class="sxs-lookup"><span data-stu-id="4c70b-431">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="4c70b-432">Beim direkten Routing werden Anrufe von und zu Benutzern nur weitergeleitet, wenn Sie den Team-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c70b-432">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="4c70b-433">Wenn in Ihrer Organisation nur Teams verwendet werden, wird empfohlen, den Modus "nur für Teams" in der Upgrade-Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4c70b-433">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="4c70b-434">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um weitere Informationen zu erhalten, und wählen Sie die geeignete Option aus: Grund [Legendes zu Koexistenz und Upgrade-Reise für Skype for Business und Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="4c70b-434">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="4c70b-435">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c70b-435">See also</span></span>

[<span data-ttu-id="4c70b-436">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="4c70b-436">Plan Direct Routing</span></span>](direct-routing-plan.md)
