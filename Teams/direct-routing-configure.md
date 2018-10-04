---
title: Konfigurieren der Weiterleitung von direkten
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Microsoft Phone System direkte Routing konfigurieren.
ms.openlocfilehash: 7e587c92e979c7985ccbd9f05bbb5ae1115d176a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374650"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="37891-103">Konfigurieren der Weiterleitung von direkten</span><span class="sxs-lookup"><span data-stu-id="37891-103">Configure Direct Routing</span></span>

<span data-ttu-id="37891-104">Wenn Sie dies nicht bereits geschehen ist, lesen [Planen direkten Routing](direct-routing-plan.md) für erforderliche Komponenten und zum Überprüfen der anderen Schritte müssen Sie ergreifen, bevor Sie das Telefonsystem Microsoft-Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="37891-104">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="37891-105">In diesem Artikel wird beschrieben, wie Microsoft Phone System direkten Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="37891-105">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="37891-106">Es werden wie eine unterstützte Session Border Controller (SBC) zum direkten Routing Kopplung und zum Konfigurieren von Microsoft-Teams, Benutzer zum direkten Routing Verbindung zu im Public Switched Telephone Network, (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="37891-106">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="37891-107">Um die in diesem Artikel erläuterten Schritte ausgeführt haben, benötigen Administratoren mit PowerShell-Cmdlets vertraut.</span><span class="sxs-lookup"><span data-stu-id="37891-107">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="37891-108">Weitere Informationen zum Verwenden von PowerShell finden Sie unter [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="37891-108">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="37891-109">Es wird empfohlen, dass Sie bestätigen, dass Ihre SBC bereits konfiguriert wurde, wie mithilfe des Herstellers Ihres SBC empfohlen:</span><span class="sxs-lookup"><span data-stu-id="37891-109">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="37891-110">Dokumentation zur Bereitstellung von AudioCodes</span><span class="sxs-lookup"><span data-stu-id="37891-110">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="37891-111">Menüband-Dokumentation zu Communications-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="37891-111">Ribbon Communications deployment documentation</span></span>

<span data-ttu-id="37891-112">Sie können Ihr Telefonsystem Microsoft konfigurieren und Aktivieren von Benutzern mithilfe von Direct Routing, und richten Sie Microsoft-Teams, als bevorzugte aufrufenden Clients anhand der folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="37891-112">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="37891-113">Den SBC mit einem Microsoft-Telefonsystem Kopplung und überprüfen die Verbindung</span><span class="sxs-lookup"><span data-stu-id="37891-113">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="37891-114">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="37891-114">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="37891-115">Sicherstellen Sie, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="37891-115">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="37891-116">Den SBC um Routingdienst von Telefonsystem leiten Kopplung</span><span class="sxs-lookup"><span data-stu-id="37891-116">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="37891-117">Es folgen drei allgemeinen Schritte ausführen, können Sie eine Verbindung herstellen oder Paaren Sie den SBC mit der direkten Routing-Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="37891-117">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="37891-118">Verbinden Sie mit **Skype für Business Online** -Verwaltungskonsole mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="37891-118">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="37891-119">Paar die SBC</span><span class="sxs-lookup"><span data-stu-id="37891-119">Pair the SBC</span></span> 
- <span data-ttu-id="37891-120">Überprüfen der Paarung</span><span class="sxs-lookup"><span data-stu-id="37891-120">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="37891-121">Herstellen einer Verbindung mit Skype für Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="37891-121">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="37891-122">Eine PowerShell-Sitzung mit dem Mandanten verbunden können Sie den SBC mit der direkten Routing-Schnittstelle Kopplung.</span><span class="sxs-lookup"><span data-stu-id="37891-122">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="37891-123">Um eine PowerShell-Sitzung zu öffnen, wenden Sie sich, befolgen Sie die Schritte in [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="37891-123">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="37891-124">Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, dass Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="37891-124">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="37891-125">Um die Befehle zu überprüfen, geben Sie ein oder kopieren und Einfügen in der folgenden in der PowerShell-Sitzung und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="37891-125">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="37891-126">Der Befehl gibt die hier gezeigten vier Funktionen zurück, mit der Sie die SBCs verwalten können.</span><span class="sxs-lookup"><span data-stu-id="37891-126">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="37891-127">Paar die SBC beziehen, um den Mandanten</span><span class="sxs-lookup"><span data-stu-id="37891-127">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="37891-128">So Paaren Sie die SBC beziehen, um den Mandanten in die PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="37891-128">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="37891-129">Es wird dringend empfohlen festlegen einen Grenzwert für den SBC mit Informationen, die in der Dokumentation SBC gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="37891-129">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="37891-130">Der Grenzwert wird eine Benachrichtigung auslösen, wenn SBC Ebene der Kapazität wird.</span><span class="sxs-lookup"><span data-stu-id="37891-130">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="37891-131">Sie können nur den SBC mit FQDN, bei denen der Domänenteil des Namens eine der in Ihrem Mandanten entspricht, außer registrierte Domänen Kopplung \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37891-131">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="37891-132">Mithilfe von \*. omicrosoft.com Domänennamen wird für die SBC-FQDN-Namen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37891-132">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="37891-133">Angenommen, Sie haben zwei Domänennamen:</span><span class="sxs-lookup"><span data-stu-id="37891-133">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="37891-134">wobei **ABC**".xyz"</span><span class="sxs-lookup"><span data-stu-id="37891-134">**abc**.xyz</span></span><br/><span data-ttu-id="37891-135">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37891-135">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="37891-136">Für den Namen SBC können Sie den Namen sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="37891-136">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="37891-137">Wenn Sie versuchen, den SBC mit einem Namen sbc.xyz.abc Kopplung, wird das System können Sie nicht, wie die Domäne nicht diesen Mandanten gehört.</span><span class="sxs-lookup"><span data-stu-id="37891-137">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="37891-138">Gibt:</span><span class="sxs-lookup"><span data-stu-id="37891-138">Returns:</span></span>
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
<span data-ttu-id="37891-139">Es sind zusätzliche Optionen, die während der Paarung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="37891-139">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="37891-140">Im vorherigen Beispiel jedoch nur die mindestens erforderlichen Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="37891-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="37891-141">Die folgende Tabelle enthält die zusätzlichen Parameter, die Sie beim Einrichten von Parametern für *Neu CsOnlinePstnGateway*verwenden können.</span><span class="sxs-lookup"><span data-stu-id="37891-141">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="37891-142">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="37891-142">Required?</span></span>|<span data-ttu-id="37891-143">Name</span><span class="sxs-lookup"><span data-stu-id="37891-143">Name</span></span>|<span data-ttu-id="37891-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37891-144">Description</span></span>|<span data-ttu-id="37891-145">Standard</span><span class="sxs-lookup"><span data-stu-id="37891-145">Default</span></span>|<span data-ttu-id="37891-146">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="37891-146">Possible values</span></span>|<span data-ttu-id="37891-147">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="37891-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37891-148">Ja</span><span class="sxs-lookup"><span data-stu-id="37891-148">Yes</span></span>|<span data-ttu-id="37891-149">FQDN</span><span class="sxs-lookup"><span data-stu-id="37891-149">FQDN</span></span>|<span data-ttu-id="37891-150">Den Vollqualifizierten Domänennamen der SBC</span><span class="sxs-lookup"><span data-stu-id="37891-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="37891-151">Keine</span><span class="sxs-lookup"><span data-stu-id="37891-151">None</span></span>|<span data-ttu-id="37891-152">NoneFQDN Name, Grenzwert 63 Zeichen</span><span class="sxs-lookup"><span data-stu-id="37891-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="37891-153">Zeichenfolge, die Liste der zulässigen / nicht zulässigen Zeichen auf [Namenskonventionen in Active Directory für Computer, Domänen, Sites und OUs](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="37891-153">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="37891-154">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-154">No</span></span>|<span data-ttu-id="37891-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="37891-155">MediaBypass</span></span> |<span data-ttu-id="37891-156">Der Parameter für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="37891-156">The parameter reserved for future use.</span></span> <span data-ttu-id="37891-157">Unterstützt die Medienumgehung der Parameter angegeben, der die SBC und der Administrator möchte, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="37891-157">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="37891-158">Keine</span><span class="sxs-lookup"><span data-stu-id="37891-158">None</span></span>|<span data-ttu-id="37891-159">True</span><span class="sxs-lookup"><span data-stu-id="37891-159">True</span></span><br/><span data-ttu-id="37891-160">False</span><span class="sxs-lookup"><span data-stu-id="37891-160">False</span></span>|<span data-ttu-id="37891-161">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="37891-161">Boolean</span></span>|
|<span data-ttu-id="37891-162">Ja</span><span class="sxs-lookup"><span data-stu-id="37891-162">Yes</span></span>|<span data-ttu-id="37891-163">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="37891-163">SipSignallingPort</span></span> |<span data-ttu-id="37891-164">Überwachungsport für die Kommunikation mit direktem Routing Services mithilfe des Protokolls Transport Layer Security (TLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="37891-164">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="37891-165">Keine</span><span class="sxs-lookup"><span data-stu-id="37891-165">None</span></span>|<span data-ttu-id="37891-166">Alle Ports</span><span class="sxs-lookup"><span data-stu-id="37891-166">Any port</span></span>|<span data-ttu-id="37891-167">zwischen 0 und 65535</span><span class="sxs-lookup"><span data-stu-id="37891-167">0 to 65535</span></span> |
|<span data-ttu-id="37891-168">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-168">No</span></span>|<span data-ttu-id="37891-169">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="37891-169">FailoverTimeSeconds</span></span> |<span data-ttu-id="37891-170">Bei Festlegung auf 10 (Standardwert), ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden an den nächsten verfügbaren Trunk weitergeleitet werden; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="37891-170">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="37891-171">In einer Organisation mit langsamen Netzwerken und Gateway Antworten möglich, die potenziell Anrufe unnötig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="37891-171">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="37891-172">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="37891-172">The default value is 10.</span></span>|<span data-ttu-id="37891-173">10</span><span class="sxs-lookup"><span data-stu-id="37891-173">10</span></span>|<span data-ttu-id="37891-174">Number</span><span class="sxs-lookup"><span data-stu-id="37891-174">Number</span></span>|<span data-ttu-id="37891-175">Int</span><span class="sxs-lookup"><span data-stu-id="37891-175">Int</span></span>|
|<span data-ttu-id="37891-176">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-176">No</span></span>|<span data-ttu-id="37891-177">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="37891-177">ForwardCallHistory</span></span> |<span data-ttu-id="37891-178">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-178">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="37891-179">Falls aktiviert, sendet der Office 365-PSTN-Proxy zwei Header: "History-Info" und weitergeleitet durch.</span><span class="sxs-lookup"><span data-stu-id="37891-179">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="37891-180">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="37891-180">The default value is **False** ($False).</span></span> |<span data-ttu-id="37891-181">False</span><span class="sxs-lookup"><span data-stu-id="37891-181">False</span></span>|<span data-ttu-id="37891-182">True</span><span class="sxs-lookup"><span data-stu-id="37891-182">True</span></span><br/><span data-ttu-id="37891-183">False</span><span class="sxs-lookup"><span data-stu-id="37891-183">False</span></span>|<span data-ttu-id="37891-184">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="37891-184">Boolean</span></span>|
|<span data-ttu-id="37891-185">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-185">No</span></span>|<span data-ttu-id="37891-186">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="37891-186">ForwardPAI</span></span>|<span data-ttu-id="37891-187">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="37891-187">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="37891-188">Mit dem PAI-Header lässt sich die Identität des Anrufers überprüfen.</span><span class="sxs-lookup"><span data-stu-id="37891-188">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="37891-189">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="37891-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="37891-190">False</span><span class="sxs-lookup"><span data-stu-id="37891-190">False</span></span>|<span data-ttu-id="37891-191">True</span><span class="sxs-lookup"><span data-stu-id="37891-191">True</span></span><br/><span data-ttu-id="37891-192">False</span><span class="sxs-lookup"><span data-stu-id="37891-192">False</span></span>|<span data-ttu-id="37891-193">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="37891-193">Boolean</span></span>|
|<span data-ttu-id="37891-194">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-194">No</span></span>|<span data-ttu-id="37891-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="37891-195">SendSIPOptions</span></span> |<span data-ttu-id="37891-196">Legt fest, ob ein SBC wird oder die SIP-Optionen wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="37891-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="37891-197">Wenn deaktiviert, wird der SBC aus der Überwachung und Warnung System ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="37891-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="37891-198">Es wird dringend empfohlen, dass Sie SIP-Optionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="37891-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="37891-199">Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="37891-199">Default value is **True**.</span></span> |<span data-ttu-id="37891-200">True</span><span class="sxs-lookup"><span data-stu-id="37891-200">True</span></span>|<span data-ttu-id="37891-201">True</span><span class="sxs-lookup"><span data-stu-id="37891-201">True</span></span><br/><span data-ttu-id="37891-202">False</span><span class="sxs-lookup"><span data-stu-id="37891-202">False</span></span>|<span data-ttu-id="37891-203">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="37891-203">Boolean</span></span>|
|<span data-ttu-id="37891-204">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-204">No</span></span>|<span data-ttu-id="37891-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="37891-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="37891-206">Wird vom System Warnungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="37891-206">Used by alerting system.</span></span> <span data-ttu-id="37891-207">Wenn Sie einen beliebigen Wert festgelegt ist, generieren Alarm System eine Benachrichtigung an den mandantenadministrator wird die Anzahl der gleichzeitigen Sitzung 90 % oder höher ist als dieser Wert.</span><span class="sxs-lookup"><span data-stu-id="37891-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="37891-208">Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert.</span><span class="sxs-lookup"><span data-stu-id="37891-208">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="37891-209">Jedoch meldet das System der Überwachung Anzahl gleichzeitiger Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="37891-209">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="37891-210">NULL</span><span class="sxs-lookup"><span data-stu-id="37891-210">Null</span></span>|<span data-ttu-id="37891-211">NULL</span><span class="sxs-lookup"><span data-stu-id="37891-211">Null</span></span><br/><span data-ttu-id="37891-212">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="37891-212">1 to 100,000</span></span> ||
|<span data-ttu-id="37891-213">Nein</span><span class="sxs-lookup"><span data-stu-id="37891-213">No</span></span>|<span data-ttu-id="37891-214">Aktiviert \*</span><span class="sxs-lookup"><span data-stu-id="37891-214">Enabled\*</span></span>|<span data-ttu-id="37891-215">Zum Aktivieren dieser SBC für ausgehende Anrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="37891-215">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="37891-216">Kann verwendet werden, um die SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="37891-216">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="37891-217">False</span><span class="sxs-lookup"><span data-stu-id="37891-217">False</span></span>|<span data-ttu-id="37891-218">True</span><span class="sxs-lookup"><span data-stu-id="37891-218">True</span></span><br/><span data-ttu-id="37891-219">False</span><span class="sxs-lookup"><span data-stu-id="37891-219">False</span></span>|<span data-ttu-id="37891-220">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="37891-220">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="37891-221">Überprüfen Sie die SBC-Verbindung</span><span class="sxs-lookup"><span data-stu-id="37891-221">Verify the SBC pairing</span></span> 

<span data-ttu-id="37891-222">Überprüfen Sie die Verbindung aus:</span><span class="sxs-lookup"><span data-stu-id="37891-222">Verify the connection:</span></span> 
- <span data-ttu-id="37891-223">Überprüfen Sie, ob in der Liste der kombinierte SBCs der SBC ist.</span><span class="sxs-lookup"><span data-stu-id="37891-223">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="37891-224">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="37891-224">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="37891-225">Überprüfen Sie, ob in der Liste der kombinierte SBCs SBC ist</span><span class="sxs-lookup"><span data-stu-id="37891-225">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="37891-226">Überprüfen Sie nachdem Sie die SBC Paar, dass der SBC mithilfe des folgenden Befehls in einer remote-PowerShell-Sitzung in der Liste der kombinierte SBCs vorhanden ist:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="37891-226">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="37891-227">Kombinierte Gateway sollte in der Liste angezeigt wird, wie im folgenden Beispiel dargestellt, und stellen Sie sicher, dass der Parameter *Enabled* gibt den Wert **True**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37891-227">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="37891-228">Geben Sie ein:</span><span class="sxs-lookup"><span data-stu-id="37891-228">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="37891-229">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="37891-229">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="37891-230">Überprüfen Sie die Optionen SIP-Fluss</span><span class="sxs-lookup"><span data-stu-id="37891-230">Validate SIP Options flow</span></span> 

<span data-ttu-id="37891-231">Um die Verbindung mit ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Management-Schnittstelle und sehen Sie, dass der SBC 200 OK-Antworten den ausgehenden Optionen abrufen.</span><span class="sxs-lookup"><span data-stu-id="37891-231">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="37891-232">Beim direkten Routing Optionen für eingehende Faxe erkennt, wird gestartet senden ausgehende Optionen auf den SBC-FQDN im Feld Kopfzeile Kontakt in der eingehenden Nachricht Optionen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="37891-232">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="37891-233">Um die Verbindung mit eingehenden SIP-Optionen zu validieren, verwenden Sie die SBC-Management-Schnittstelle und finden Sie, dass der SBC Antwort auf die Optionen für Nachrichten, die von direkten Routing wird und der Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="37891-233">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="37891-234">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="37891-234">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="37891-235">Wenn Sie so aktivieren Sie Benutzer für die direkte Routingdienst bereit sind, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="37891-235">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="37891-236">Erstellen eines Benutzers in Office 365 und eine Telefon-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="37891-236">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="37891-237">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="37891-237">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="37891-238">Konfigurieren Sie die Telefonnummer ein, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="37891-238">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="37891-239">Konfigurieren von VoIP-routing.</span><span class="sxs-lookup"><span data-stu-id="37891-239">Configure voice routing.</span></span> <span data-ttu-id="37891-240">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="37891-240">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="37891-241">Erstellen eines Benutzers in Office 365 und Lizenz zuweisen</span><span class="sxs-lookup"><span data-stu-id="37891-241">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="37891-242">Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="37891-242">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="37891-243">Jedoch wird empfohlen, dass Ihre Organisation wählen und verwenden eine Option, um routing Probleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="37891-243">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="37891-244">Erstellen Sie des Benutzers in Active Directory am Standort und synchronisieren Sie den Benutzer in die Cloud zu.</span><span class="sxs-lookup"><span data-stu-id="37891-244">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="37891-245">Finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="37891-245">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="37891-246">Erstellen Sie den Benutzer direkt in Office 365-Administrator-Portal.</span><span class="sxs-lookup"><span data-stu-id="37891-246">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="37891-247">Finden Sie unter [Benutzer einzeln oder in einer Sammeloperation zu Office 365 - Admin Hilfe hinzufügen](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="37891-247">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="37891-248">Wenn Sie das System, das mit Skype für Business 2015 oder Lync 2010/2013 lokal vorhanden ist erstellen, ist die einzige unterstützte Option den Benutzer im lokalen Active Directory erstellen und Synchronisieren des Benutzers in die Cloud (Option 1).</span><span class="sxs-lookup"><span data-stu-id="37891-248">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="37891-249">Lizenzen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="37891-249">Required licenses:</span></span> 

- <span data-ttu-id="37891-250">Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan2 und Teams) + Phone System</span><span class="sxs-lookup"><span data-stu-id="37891-250">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="37891-251">Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan2, Teams und Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="37891-251">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="37891-252">Optional Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="37891-252">Optional licenses:</span></span> 

- <span data-ttu-id="37891-253">Plan aufrufen</span><span class="sxs-lookup"><span data-stu-id="37891-253">Calling Plan</span></span> 
- <span data-ttu-id="37891-254">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="37891-254">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="37891-255">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="37891-255">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="37891-256">Direktes Routing bewirkt, dass den Benutzer in Skype für Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-256">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="37891-257">Sie können dies überprüfen, anhand des RegistrarPool-Parameters.</span><span class="sxs-lookup"><span data-stu-id="37891-257">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="37891-258">Es muss einen Wert in der Domäne infra.lync.com verfügen.</span><span class="sxs-lookup"><span data-stu-id="37891-258">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="37891-259">Verbinden Sie mit remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37891-259">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="37891-260">Geben Sie den Befehl:</span><span class="sxs-lookup"><span data-stu-id="37891-260">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="37891-261">Konfigurieren Sie die Telefonnummer ein, und Aktivieren von Enterprise-VoIP und voicemail</span><span class="sxs-lookup"><span data-stu-id="37891-261">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="37891-262">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt so konfigurieren Sie ihre Telefonnummer und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="37891-262">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="37891-263">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="37891-263">This can be done in one step.</span></span> 

<span data-ttu-id="37891-264">So fügen Sie die Telefonnummer, und für Voicemail aktivieren:</span><span class="sxs-lookup"><span data-stu-id="37891-264">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="37891-265">Verbinden Sie mit einer remote-PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="37891-265">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="37891-266">Geben Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="37891-266">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="37891-267">Um eine Rufnummer für den Benutzer "Software niedrig" hinzuzufügen, würden Sie beispielsweise Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="37891-267">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="37891-268">Die Rufnummer muss als eine vollständige e. 164-Rufnummer mit Ländercode konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="37891-268">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="37891-269">Wenn Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie lokale Skype für Business-Verwaltungsshell oder in der Systemsteuerung so konfigurieren Sie die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="37891-269">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="37891-270">Konfigurieren von VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="37891-270">Configure Voice Routing</span></span> 

<span data-ttu-id="37891-271">Microsoft Telefonsystem hat einen routing Mechanismus, der einen Anruf an eine bestimmte SBC basierend auf gesendet werden können:</span><span class="sxs-lookup"><span data-stu-id="37891-271">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="37891-272">Nummernmuster aufgerufen</span><span class="sxs-lookup"><span data-stu-id="37891-272">Called number pattern</span></span> 
- <span data-ttu-id="37891-273">Nummernmuster + bestimmte Benutzer, der den Anruf tätigt aufgerufen</span><span class="sxs-lookup"><span data-stu-id="37891-273">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="37891-274">SBCs können als aktiv und backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="37891-274">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="37891-275">Das bedeutet, wenn der SBC, der für diese Nummernmuster, oder Nummernmuster + bestimmten Benutzer als aktiv konfiguriert ist nicht verfügbar ist, und klicken Sie dann die Anrufe an eine Sicherung SBC weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-275">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="37891-276">Anrufrouting aus den folgenden Elementen besteht:</span><span class="sxs-lookup"><span data-stu-id="37891-276">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="37891-277">VoIP Routing-Richtlinie – Container für PSTN-Verwendungen; kann an einen Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="37891-277">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="37891-278">PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; können in unterschiedlichen VoIP-Routing-Richtlinien gemeinsam genutzt werden</span><span class="sxs-lookup"><span data-stu-id="37891-278">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="37891-279">VoIP-Routen-Muster und einen Satz von Online PSTN-Gateways für Anrufe verwendet, in dem anrufende Nummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="37891-279">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="37891-280">Online PSTN-Gateway - Zeiger SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Anruf über den SBC, wie P-Asserted-Identity (PAI) nach vorne oder bevorzugte Codecs platziert wird. VoIP-Routen können hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="37891-280">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="37891-281">Erstellen einer VoIP-Routingrichtlinie mit einem PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="37891-281">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="37891-282">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien zurückgegeben in Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="37891-282">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="37891-283">**Call Flow 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf weitergeleitet, um SBC sbc1<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="37891-283">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="37891-284">Wenn weder sbc1<span></span>. contoso.biz noch sbc2<span></span>. contoso.biz verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="37891-284">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="37891-285">**Call Flow 2 (auf der rechten Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf zuerst an SBC sbc1 weitergeleitet<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="37891-285">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="37891-286">Wenn weder SBC verfügbar ist, wird die Route mit niedrigere Priorität versucht (sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="37891-286">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="37891-287">Wenn keines der SBCs verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="37891-287">If none of the SBCs are available, the call is dropped.</span></span> 

![Beispiele für VoIP routing-Richtlinie](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="37891-289">Während der VoIP-Route Prioritäten zugewiesen wird, werden die SBCs in die Routen in beiden Beispielen in zufälliger Reihenfolge getestet.</span><span class="sxs-lookup"><span data-stu-id="37891-289">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="37891-290">Wenn der Benutzer auch eine Microsoft aufrufen planen Lizenz besitzt, werden Anrufe an eine andere Zahl mit Ausnahme der Zielrufnummer entsprechen die Muster + +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration gelöscht.</span><span class="sxs-lookup"><span data-stu-id="37891-290">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="37891-291">Wenn der Benutzer eine Lizenz aufrufen planen verfügt, wird der Anruf automatisch entsprechend den Richtlinien von Microsoft aufrufen planen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="37891-291">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="37891-292">Microsoft aufrufen planen automatisch als die letzte Route gilt für alle Benutzer mit der Lizenz Microsoft aufrufen planen und erfordert keine zusätzlichen Aufruf Routingkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="37891-292">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="37891-293">Im Beispiel in der folgenden Abbildung wird eine VoIP-Route zum Senden von Anrufen an alle anderen USA und Kanada Nummer (Anrufe, die an das gewählte übersetzende + 1 XXX XXX XX XX umgeleitet) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="37891-293">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt VoIP-routing-Richtlinie mit einer dritten route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="37891-295">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="37891-295">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="37891-296">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="37891-296">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="37891-297">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="37891-297">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="37891-298">Die Priorität die Wert für die Route "Andere + 1" ist in diesem Fall unerheblich, wie es ist nur eine Route, die dem Muster + 1 entspricht XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="37891-298">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="37891-299">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 herstellt und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="37891-299">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="37891-300">In der folgenden Tabelle werden die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="37891-300">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="37891-301">In diesem Beispiel werden alle drei Routen Teil der gleichen PSTN-Verwendung "Uns und Kanada" an.</span><span class="sxs-lookup"><span data-stu-id="37891-301">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="37891-302">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="37891-302">**PSTN usage**</span></span>|<span data-ttu-id="37891-303">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="37891-303">**Voice route**</span></span>|<span data-ttu-id="37891-304">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="37891-304">**Number pattern**</span></span>|<span data-ttu-id="37891-305">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="37891-305">**Priority**</span></span>|<span data-ttu-id="37891-306">**SBC**</span><span class="sxs-lookup"><span data-stu-id="37891-306">**SBC**</span></span>|<span data-ttu-id="37891-307">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37891-307">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37891-308">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-308">US only</span></span>|<span data-ttu-id="37891-309">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="37891-309">“Redmond 1”</span></span>|<span data-ttu-id="37891-310">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="37891-310">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="37891-311">1</span><span class="sxs-lookup"><span data-stu-id="37891-311">1</span></span>|<span data-ttu-id="37891-312">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-312">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-313">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-313">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-314">Aktive Route für gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="37891-314">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="37891-315">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-315">US only</span></span>|<span data-ttu-id="37891-316">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="37891-316">“Redmond 2”</span></span>|<span data-ttu-id="37891-317">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="37891-317">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="37891-318">2</span><span class="sxs-lookup"><span data-stu-id="37891-318">2</span></span>|<span data-ttu-id="37891-319">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-319">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-320">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-320">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-321">Backup Route für die gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="37891-321">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="37891-322">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-322">US only</span></span>|<span data-ttu-id="37891-323">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="37891-323">"Other +1”</span></span>|<span data-ttu-id="37891-324">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="37891-324">^\\+1(\d{10})$</span></span>|<span data-ttu-id="37891-325">3</span><span class="sxs-lookup"><span data-stu-id="37891-325">3</span></span>|<span data-ttu-id="37891-326">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-326">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-327">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-327">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-328">Weiterleiten von zur gewählte Nummern + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="37891-328">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="37891-329">Alle Routen die PSTN-Verwendung "Uns und Kanada" zugeordnet sind, und die PSTN-Verwendung der VoIP-Routing-Richtlinie "Nur in den USA." zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="37891-329">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="37891-330">In diesem Beispiel wird der Benutzer Spencer Low VoIP-routing-Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="37891-330">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="37891-331">Beispiele für anrufrouten</span><span class="sxs-lookup"><span data-stu-id="37891-331">Examples of call routes</span></span>

<span data-ttu-id="37891-332">Im folgenden Beispiel wir wird gezeigt, wie Routen, PSTN-Verwendungen und Routing Richtlinien konfigurieren, und weisen wir die Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="37891-332">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="37891-333">**Schritt 1:** Erstellen Sie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="37891-333">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="37891-334">Geben Sie in einer Skype für Business Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-334">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="37891-335">Überprüfen Sie, dass die Verwendung durch Eingabe erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="37891-335">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="37891-336">Die eine Liste mit Namen zurückgibt, der abgeschnitten werden kann:</span><span class="sxs-lookup"><span data-stu-id="37891-336">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="37891-337">Im folgenden Beispiel sehen Sie das Ergebnis der Ausführung der PowerShell-Befehl *`(Get-CSOnlinePSTNUsage).usage`* vollständige Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37891-337">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="37891-338">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype für Business Online drei Routen: 1, 2 und andere + 1, Redmond "Redmond", wie in der vorherigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37891-338">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="37891-339">Wenn Sie um die Route "" Redmond "1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-339">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="37891-340">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="37891-340">Which returns:</span></span>
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
<span data-ttu-id="37891-341">Um die Route für Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-341">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="37891-342">Um die anderen + 1-Route zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-342">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="37891-343">Stellen Sie sicher, dass es sich bei Ihren reguläre Ausdruck in das Attribut NumberPattern Ausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="37891-343">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="37891-344">Sie können mithilfe dieser Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="37891-344">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="37891-345">In einigen Fällen besteht Bedarf für alle Anrufe an den gleichen SBC weitergeleitet. Verwenden Sie - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="37891-345">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="37891-346">Alle Anrufe an demselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="37891-346">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="37891-347">Überprüfen Sie, ob Sie die Route durch Ausführen von ordnungsgemäß konfiguriert haben die `Get-CSOnlineVoiceRoute` Powershell-Befehl mit der Optionen wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="37891-347">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="37891-348">Die zurückgegeben werden soll:</span><span class="sxs-lookup"><span data-stu-id="37891-348">Which should return:</span></span>
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
NumberPattern       : ^\\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="37891-349">Im Beispiel die Route, dass "Andere + 1" automatisch Priorität zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="37891-349">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="37891-350">**Schritt 3:** Erstellen einer VoIP-Routing-Richtlinie "Nur USA" und Hinzufügen der Richtlinie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="37891-350">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="37891-351">Geben Sie in einer PowerShell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-351">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="37891-352">In diesem Beispiel wird das Ergebnis gezeigt:</span><span class="sxs-lookup"><span data-stu-id="37891-352">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="37891-353">**Schritt 4:** Dem Benutzer erteilen Sie Spence Low eine VoIP-routing-Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37891-353">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="37891-354">Geben Sie in einer Powershell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-354">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="37891-355">Überprüfen Sie die Zuordnung der Richtlinie, indem Sie folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="37891-355">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="37891-356">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="37891-356">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="37891-357">Erstellen einer VoIP-Routing-Richtlinie mit mehreren PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="37891-357">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="37891-358">Die VoIP-Routing-Richtlinie erstellt ermöglicht zuvor nur Anrufe an externe Telefonnummern in den USA und Kanada –, es sei denn, die Lizenz Microsoft aufrufen planen auch dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="37891-358">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="37891-359">Im folgenden Beispiel wird, können Sie die VoIP-Routing-Richtlinie "Ohne Einschränkungen." erstellen</span><span class="sxs-lookup"><span data-stu-id="37891-359">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="37891-360">Die Richtlinie verwendet die PSTN-Verwendung "Uns und Kanada" erstellt, die im vorherigen Beispiel als auch die neuen PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="37891-360">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="37891-361">Dies leitet alle anderen Aufrufe der SBCs sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="37891-361">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="37891-362">In den Beispielen, die angezeigt werden Zuweisen von uns nur die Richtlinie für Benutzer "Software niedrig" und keine Einschränkungen für den Benutzer "John Woods".</span><span class="sxs-lookup"><span data-stu-id="37891-362">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="37891-363">Software niedrig – zulässig Anrufe nur für die USA und Kanada Zahlen.</span><span class="sxs-lookup"><span data-stu-id="37891-363">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="37891-364">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-364">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="37891-365">Außerhalb der USA Zahlen werden nicht weitergeleitet werden, es sei denn, die Lizenz planen aufrufen, das dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="37891-365">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="37891-366">John Woods – Anrufe an eine beliebige Anzahl zulässig.</span><span class="sxs-lookup"><span data-stu-id="37891-366">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="37891-367">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-367">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="37891-368">Außerhalb der USA Rufnummern weitergeleitet werden über sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="37891-368">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer Spencer Low zugewiesen ist](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="37891-370">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="37891-370">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="37891-371">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="37891-371">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="37891-372">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="37891-372">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer John Woods zugewiesen ist](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="37891-374">In der folgenden Tabelle werden die routing Richtlinie "No Einschränkungen" Usage Bezeichnungen und VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="37891-374">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="37891-375">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="37891-375">**PSTN usage**</span></span>|<span data-ttu-id="37891-376">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="37891-376">**Voice route**</span></span>|<span data-ttu-id="37891-377">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="37891-377">**Number pattern**</span></span>|<span data-ttu-id="37891-378">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="37891-378">**Priority**</span></span>|<span data-ttu-id="37891-379">**SBC**</span><span class="sxs-lookup"><span data-stu-id="37891-379">**SBC**</span></span>|<span data-ttu-id="37891-380">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37891-380">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37891-381">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-381">US Only</span></span>|<span data-ttu-id="37891-382">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="37891-382">“Redmond 1”</span></span>|<span data-ttu-id="37891-383">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="37891-383">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="37891-384">1</span><span class="sxs-lookup"><span data-stu-id="37891-384">1</span></span>|<span data-ttu-id="37891-385">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-385">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-386">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-386">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-387">Aktive Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="37891-387">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="37891-388">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-388">US Only</span></span>|<span data-ttu-id="37891-389">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="37891-389">“Redmond 2”</span></span>|<span data-ttu-id="37891-390">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="37891-390">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="37891-391">2</span><span class="sxs-lookup"><span data-stu-id="37891-391">2</span></span>|<span data-ttu-id="37891-392">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-392">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-393">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-393">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-394">Backup Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="37891-394">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="37891-395">UNS nur</span><span class="sxs-lookup"><span data-stu-id="37891-395">US Only</span></span>|<span data-ttu-id="37891-396">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="37891-396">“Other +1”</span></span>|<span data-ttu-id="37891-397">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="37891-397">^+1(\d{10})$</span></span>|<span data-ttu-id="37891-398">3</span><span class="sxs-lookup"><span data-stu-id="37891-398">3</span></span>|<span data-ttu-id="37891-399">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-399">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-400">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-400">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-401">Route für angerufenen Zahlen + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="37891-401">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="37891-402">International</span><span class="sxs-lookup"><span data-stu-id="37891-402">International</span></span>|<span data-ttu-id="37891-403">International</span><span class="sxs-lookup"><span data-stu-id="37891-403">International</span></span>|<span data-ttu-id="37891-404">\d+</span><span class="sxs-lookup"><span data-stu-id="37891-404">\d+</span></span>|<span data-ttu-id="37891-405">4</span><span class="sxs-lookup"><span data-stu-id="37891-405">4</span></span>|<span data-ttu-id="37891-406">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-406">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="37891-407">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="37891-407">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="37891-408">Route für alle Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="37891-408">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="37891-409">Die Reihenfolge der PSTN-Verwendungen in VoIP-Routing-Richtlinien ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="37891-409">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="37891-410">Die Verwendungen in Reihenfolge angewendet werden, und wenn in der ersten Verwendung eine Übereinstimmung gefunden wird, klicken Sie dann andere Verwendungen werden nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="37891-410">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="37891-411">Die PSTN-Verwendung "International" muss nach der PSTN-Verwendung "Uns nur." platziert werden</span><span class="sxs-lookup"><span data-stu-id="37891-411">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="37891-412">Führen Sie zum Ändern der Reihenfolge der PSTN-Verwendungen, die `Set-CSOnlineRouteRoutingPolicy` Befehl.</span><span class="sxs-lookup"><span data-stu-id="37891-412">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="37891-413">Ändern die Reihenfolge von "Uns und Kanada" beispielsweise vor- und "International" Sekunde bis zu der umgekehrten Reihenfolge ausführen:</span><span class="sxs-lookup"><span data-stu-id="37891-413">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="37891-414">Die Priorität für "Andere + 1" und "International" VoIP-Routen werden automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="37891-414">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="37891-415">Diese nicht von Bedeutung sind, solange sie niedrigere Prioritäten als "" Redmond "1" und "Redmond 2" besitzen</span><span class="sxs-lookup"><span data-stu-id="37891-415">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="37891-416">Beispiel für VoIP-Routing-Richtlinie für den Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="37891-416">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="37891-417">Die Schritte zum Erstellen von PSTN-Verwendung "International", VoIP-Route "International", VoIP-Routing-Richtlinie "No Einschränkungen,", und klicken Sie dann den Benutzer "John Woods" zuweisen lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="37891-417">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1. <span data-ttu-id="37891-418">Erstellen Sie zunächst die PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="37891-418">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="37891-419">Geben Sie in einer PowerShell-Remotesitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="37891-419">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="37891-420">Im nächsten Schritt erstellen Sie die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="37891-420">Next, create the new voice route “International.”</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="37891-421">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="37891-421">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : \d+
   OnlinePstnUsages          : {International}    
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="37891-422">Im nächsten Schritt erstellen Sie eine VoIP-Routing-Richtlinie "Ohne Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="37891-422">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="37891-423">Die PSTN-Verwendung "" Redmond "1" und "Redmond" werden in dieser VoIP-Routingrichtlinie besondere Behandlung für Aufrufe von "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder am Standort Aufrufe nummerieren beibehalten wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37891-423">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="37891-424">Die zurückgibt</span><span class="sxs-lookup"><span data-stu-id="37891-424">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="37891-425">Weisen Sie die VoIP-routing-Richtlinie für den Benutzer "John Woods" mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="37891-425">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="37891-426">Überprüfen Sie anschließend die Zuordnung mit dem Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="37891-426">Then verify the assignment using the command:</span></span>   

   ```
   Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="37891-427">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="37891-427">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="37891-428">Das Ergebnis ist, dass die VoIP-Richtlinie auf John Woods Anrufe angewendet werden nicht eingeschränkt, und die Logik des Routings ausgehender Anrufe für den Aufruf von USA, Kanada und International verfügbaren vor.</span><span class="sxs-lookup"><span data-stu-id="37891-428">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="37891-429">Festlegen Sie Microsoft-Teams als bevorzugter Client aufrufende für Benutzer</span><span class="sxs-lookup"><span data-stu-id="37891-429">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="37891-430">Direktes Routing nur weiterleiten Anrufe an und von Benutzern, wenn sie die Verwendung des Teams-Clients.</span><span class="sxs-lookup"><span data-stu-id="37891-430">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="37891-431">Wenn Ihre Organisation nur Teams verwendet, wird "Nur Teams"-Modus in Upgrade Richtlinie empfohlen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="37891-431">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="37891-432">Wenn Ihre Organisation für Business Online Skype für Business Server oder Skype verwendet wird, finden Sie im folgenden Artikel Weitere Informationen und die entsprechende Option: [Verstehen der Koexistenz und Durchführen eines Upgrades Weg für Skype für Unternehmen und Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="37891-432">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option:  [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="37891-433">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37891-433">See also</span></span>

[<span data-ttu-id="37891-434">Planen der direkten Routing</span><span class="sxs-lookup"><span data-stu-id="37891-434">Plan Direct Routing</span></span>](direct-routing-plan.md)
