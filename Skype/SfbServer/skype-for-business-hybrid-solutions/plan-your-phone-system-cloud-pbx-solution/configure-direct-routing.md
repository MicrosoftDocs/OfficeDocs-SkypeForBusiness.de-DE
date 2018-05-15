---
title: Konfigurieren der Weiterleitung von direkten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/15/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Erfahren Sie, wie Microsoft Phone System direkte Routing konfigurieren.
ms.openlocfilehash: e2f9629de713c363de02124a922b21882853d54d
ms.sourcegitcommit: 92f2fa97c8870f8ad86c6001f2240a74261e2600
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2018
---
# <a name="configure-direct-routing"></a><span data-ttu-id="fd6ec-103">Konfigurieren der Weiterleitung von direkten</span><span class="sxs-lookup"><span data-stu-id="fd6ec-103">Configure Direct Routing</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd6ec-104">Dies ist eine Vorabversion der Microsoft Phone System direkten Routing.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-104">This is a preview release of Microsoft Phone System Direct Routing.</span></span>  <span data-ttu-id="fd6ec-105">Produktfunktionen und Dokumentation werden können geändert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-105">Product functionality and documentation are subject to change.</span></span>

<span data-ttu-id="fd6ec-106">Wenn Sie dies nicht bereits geschehen ist, lesen [Planen direkten Routing](plan-direct-routing.md) für erforderliche Komponenten und zum Überprüfen der anderen Schritte müssen Sie ergreifen, bevor Sie das Telefonsystem Microsoft-Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-106">If you have not already done so, read [Plan Direct Routing](plan-direct-routing.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="fd6ec-107">Dieses Dokument ist für IT-Experten vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-107">This document is intended for IT professionals.</span></span>  

<span data-ttu-id="fd6ec-108">In diesem Artikel wird beschrieben, wie Microsoft Phone System direkten Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-108">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="fd6ec-109">Es werden wie eine unterstützte Session Border Controller (SBC) zum direkten Routing Kopplung und zum Konfigurieren von Microsoft-Teams, Benutzer zum direkten Routing Verbindung zu im Public Switched Telephone Network, (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-109">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="fd6ec-110">Um die in diesem Artikel erläuterten Schritte ausgeführt haben, benötigen Administratoren mit PowerShell-Cmdlets vertraut.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="fd6ec-111">Weitere Informationen zum Verwenden von PowerShell finden Sie unter [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 

<span data-ttu-id="fd6ec-112">Es wird empfohlen, dass Sie bestätigen, dass Ihre SBC bereits konfiguriert wurde, wie mithilfe des Herstellers Ihres SBC empfohlen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-112">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="fd6ec-113">Dokumentation zur Bereitstellung von AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fd6ec-113">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="fd6ec-114">Dokumentation zur Bereitstellung von Menüband</span><span class="sxs-lookup"><span data-stu-id="fd6ec-114">Ribbon deployment documentation</span></span>

<span data-ttu-id="fd6ec-115">Sie können Ihr Telefonsystem Microsoft konfigurieren und Aktivieren von Benutzern mithilfe von Direct Routing, und richten Sie Microsoft-Teams, als bevorzugte aufrufenden Clients anhand der folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-115">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="fd6ec-116">Den SBC mit einem Microsoft-Telefonsystem Kopplung und überprüfen die Verbindung</span><span class="sxs-lookup"><span data-stu-id="fd6ec-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="fd6ec-117">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="fd6ec-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="fd6ec-118">Sicherstellen Sie, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="fd6ec-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-the-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="fd6ec-119">Den SBC um Routingdienst von Telefonsystem leiten Kopplung</span><span class="sxs-lookup"><span data-stu-id="fd6ec-119">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="fd6ec-120">Es folgen drei allgemeinen Schritte ausführen, können Sie eine Verbindung herstellen oder Paaren Sie den SBC mit der direkten Routing-Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="fd6ec-121">Verbinden Sie mit **Skype für Business Online** -Verwaltungskonsole mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd6ec-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="fd6ec-122">Paar die SBC</span><span class="sxs-lookup"><span data-stu-id="fd6ec-122">Pair the SBC</span></span> 
- <span data-ttu-id="fd6ec-123">Überprüfen der Paarung</span><span class="sxs-lookup"><span data-stu-id="fd6ec-123">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="fd6ec-124">Herstellen einer Verbindung mit Skype für Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd6ec-124">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="fd6ec-125">Eine PowerShell-Sitzung mit dem Mandanten verbunden können Sie den SBC mit der direkten Routing-Schnittstelle Kopplung.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="fd6ec-126">Um eine PowerShell-Sitzung zu öffnen, wenden Sie sich, befolgen Sie die Schritte in [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 
 
<span data-ttu-id="fd6ec-127">Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, dass Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="fd6ec-128">Um die Befehle zu überprüfen, geben Sie ein oder kopieren und Einfügen in der folgenden in der PowerShell-Sitzung und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="fd6ec-129">Der Befehl gibt die hier gezeigten vier Funktionen zurück, mit der Sie die SBCs verwalten können.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-129">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

```
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
```   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="fd6ec-130">Paar die SBC beziehen, um den Mandanten</span><span class="sxs-lookup"><span data-stu-id="fd6ec-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="fd6ec-131">So Paaren Sie die SBC beziehen, um den Mandanten in die PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="fd6ec-132">Es wird dringend empfohlen festlegen einen Grenzwert für den SBC mit Informationen, die in der Dokumentation SBC gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-132">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="fd6ec-133">Der Grenzwert wird eine Benachrichtigung auslösen, wenn SBC Ebene der Kapazität wird.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-133">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="fd6ec-134">Sie können nur den SBC mit FQDN, bei denen der Domänenteil des Namens eine der in Ihrem Mandanten entspricht, außer registrierte Domänen Kopplung \*. onmicrosoft.com. Mithilfe von \*. omicrosoft.com Domänennamen wird für die SBC-FQDN-Namen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-134">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com. Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="fd6ec-135">Angenommen, Sie haben zwei Domänennamen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-135">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="fd6ec-136">wobei **ABC**".xyz"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-136">**abc**.xyz</span></span><br/><span data-ttu-id="fd6ec-137">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="fd6ec-137">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="fd6ec-138">Für den Namen SBC können Sie den Namen sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-138">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="fd6ec-139">Wenn Sie versuchen, den SBC mit einem Namen sbc.xyz.abc Kopplung, wird das System können Sie nicht, wie die Domäne nicht diesen Mandanten gehört.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-139">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="fd6ec-140">Gibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-140">Returns:</span></span>
``` 
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
```
<span data-ttu-id="fd6ec-141">Es sind zusätzliche Optionen, die während der Paarung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-141">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="fd6ec-142">Im vorherigen Beispiel jedoch nur die mindestens erforderlichen Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-142">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="fd6ec-143">Die folgende Tabelle enthält die zusätzlichen Parameter, die Sie beim Einrichten von Parametern für *Neu CsOnlinePstnGateway*verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-143">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="fd6ec-144">**Erforderlich?**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-144">**Required?**</span></span>|<span data-ttu-id="fd6ec-145">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-145">**Name**</span></span>|<span data-ttu-id="fd6ec-146">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-146">**Description**</span></span>|<span data-ttu-id="fd6ec-147">**Standard**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-147">**Default**</span></span>|<span data-ttu-id="fd6ec-148">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-148">**Possible values**</span></span>|<span data-ttu-id="fd6ec-149">**Typ und Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-149">**Type and restrictions**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd6ec-150">Ja</span><span class="sxs-lookup"><span data-stu-id="fd6ec-150">Yes</span></span>|<span data-ttu-id="fd6ec-151">FQDN</span><span class="sxs-lookup"><span data-stu-id="fd6ec-151">FQDN</span></span>|<span data-ttu-id="fd6ec-152">Den Vollqualifizierten Domänennamen der SBC</span><span class="sxs-lookup"><span data-stu-id="fd6ec-152">The FQDN name of the SBC</span></span> |<span data-ttu-id="fd6ec-153">Keine</span><span class="sxs-lookup"><span data-stu-id="fd6ec-153">None</span></span>|<span data-ttu-id="fd6ec-154">NoneFQDN Name, Grenzwert 63 Zeichen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-154">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="fd6ec-155">Zeichenfolge, die Liste der zulässigen / nicht zulässigen Zeichen auf [Namenskonventionen in Active Directory für Computer, Domänen, Sites und OUs](https://support.microsoft.com/en-us/help/909264)</span><span class="sxs-lookup"><span data-stu-id="fd6ec-155">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/en-us/help/909264)</span></span>|
|<span data-ttu-id="fd6ec-156">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-156">No</span></span>|<span data-ttu-id="fd6ec-157">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="fd6ec-157">MediaBypass</span></span> |<span data-ttu-id="fd6ec-158">Der Parameter für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-158">The parameter reserved for future use.</span></span> <span data-ttu-id="fd6ec-159">Unterstützt die Medienumgehung der Parameter angegeben, der die SBC und der Administrator möchte, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-159">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="fd6ec-160">Keine</span><span class="sxs-lookup"><span data-stu-id="fd6ec-160">None</span></span>|<span data-ttu-id="fd6ec-161">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-161">True</span></span><br/><span data-ttu-id="fd6ec-162">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-162">False</span></span>|<span data-ttu-id="fd6ec-163">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fd6ec-163">Boolean</span></span>|
|<span data-ttu-id="fd6ec-164">Ja</span><span class="sxs-lookup"><span data-stu-id="fd6ec-164">Yes</span></span>|<span data-ttu-id="fd6ec-165">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="fd6ec-165">SipSignallingPort</span></span> |<span data-ttu-id="fd6ec-166">Überwachungsport für die Kommunikation mit direktem Routing Services mithilfe des Protokolls Transport Layer Security (TLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-166">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="fd6ec-167">Keine</span><span class="sxs-lookup"><span data-stu-id="fd6ec-167">None</span></span>|<span data-ttu-id="fd6ec-168">Alle Ports</span><span class="sxs-lookup"><span data-stu-id="fd6ec-168">Any port</span></span>|<span data-ttu-id="fd6ec-169">zwischen 0 und 65535</span><span class="sxs-lookup"><span data-stu-id="fd6ec-169">0 to 65535</span></span> |
|<span data-ttu-id="fd6ec-170">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-170">No</span></span>|<span data-ttu-id="fd6ec-171">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="fd6ec-171">FailoverTimeSeconds</span></span> |<span data-ttu-id="fd6ec-172">Bei Festlegung auf 10 (Standardwert), ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden an den nächsten verfügbaren Trunk weitergeleitet werden; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-172">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="fd6ec-173">In einer Organisation mit langsamen Netzwerken und Gateway Antworten möglich, die potenziell Anrufe unnötig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-173">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="fd6ec-174">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-174">The default value is 10.</span></span>|<span data-ttu-id="fd6ec-175">10</span><span class="sxs-lookup"><span data-stu-id="fd6ec-175">10</span></span>|<span data-ttu-id="fd6ec-176">Number</span><span class="sxs-lookup"><span data-stu-id="fd6ec-176">Number</span></span>|<span data-ttu-id="fd6ec-177">Int</span><span class="sxs-lookup"><span data-stu-id="fd6ec-177">Int</span></span>|
|<span data-ttu-id="fd6ec-178">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-178">No</span></span>|<span data-ttu-id="fd6ec-179">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="fd6ec-179">ForwardCallHistory</span></span> |<span data-ttu-id="fd6ec-180">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-180">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="fd6ec-181">Falls aktiviert, sendet der Office 365-PSTN-Proxy zwei Header: "History-Info" und weitergeleitet durch.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-181">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="fd6ec-182">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-182">The default value is **False** ($False).</span></span> |<span data-ttu-id="fd6ec-183">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-183">False</span></span>|<span data-ttu-id="fd6ec-184">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-184">True</span></span><br/><span data-ttu-id="fd6ec-185">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-185">False</span></span>|<span data-ttu-id="fd6ec-186">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fd6ec-186">Boolean</span></span>|
|<span data-ttu-id="fd6ec-187">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-187">No</span></span>|<span data-ttu-id="fd6ec-188">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="fd6ec-188">ForwardPAI</span></span>|<span data-ttu-id="fd6ec-189">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-189">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="fd6ec-190">Mit dem PAI-Header lässt sich die Identität des Anrufers überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-190">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="fd6ec-191">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="fd6ec-192">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-192">False</span></span>|<span data-ttu-id="fd6ec-193">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-193">True</span></span><br/><span data-ttu-id="fd6ec-194">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-194">False</span></span>|<span data-ttu-id="fd6ec-195">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fd6ec-195">Boolean</span></span>|
|<span data-ttu-id="fd6ec-196">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-196">No</span></span>|<span data-ttu-id="fd6ec-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="fd6ec-197">SendSIPOptions</span></span> |<span data-ttu-id="fd6ec-198">Legt fest, ob ein SBC wird oder die SIP-Optionen wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="fd6ec-199">Wenn deaktiviert, wird der SBC aus der Überwachung und Warnung System ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="fd6ec-200">Es wird dringend empfohlen, dass Sie SIP-Optionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="fd6ec-201">Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-201">Default value is **True**.</span></span> |<span data-ttu-id="fd6ec-202">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-202">True</span></span>|<span data-ttu-id="fd6ec-203">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-203">True</span></span><br/><span data-ttu-id="fd6ec-204">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-204">False</span></span>|<span data-ttu-id="fd6ec-205">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fd6ec-205">Boolean</span></span>|
|<span data-ttu-id="fd6ec-206">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-206">No</span></span>|<span data-ttu-id="fd6ec-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="fd6ec-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="fd6ec-208">Wird vom System Warnungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-208">Used by alerting system.</span></span> <span data-ttu-id="fd6ec-209">Wenn Sie einen beliebigen Wert festgelegt ist, generieren Alarm System eine Benachrichtigung an den mandantenadministrator wird die Anzahl der gleichzeitigen Sitzung 90 % oder höher ist als dieser Wert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="fd6ec-210">Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="fd6ec-211">Jedoch meldet das System der Überwachung Anzahl gleichzeitiger Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="fd6ec-212">NULL</span><span class="sxs-lookup"><span data-stu-id="fd6ec-212">Null</span></span>|<span data-ttu-id="fd6ec-213">NULL</span><span class="sxs-lookup"><span data-stu-id="fd6ec-213">Null</span></span><br/><span data-ttu-id="fd6ec-214">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="fd6ec-214">1 to 100,000</span></span> ||
|<span data-ttu-id="fd6ec-215">Nein</span><span class="sxs-lookup"><span data-stu-id="fd6ec-215">No</span></span>|<span data-ttu-id="fd6ec-216">Aktiviert \*</span><span class="sxs-lookup"><span data-stu-id="fd6ec-216">Enabled\*</span></span>|<span data-ttu-id="fd6ec-217">Zum Aktivieren dieser SBC für ausgehende Anrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="fd6ec-218">Kann verwendet werden, um die SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="fd6ec-219">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-219">False</span></span>|<span data-ttu-id="fd6ec-220">True</span><span class="sxs-lookup"><span data-stu-id="fd6ec-220">True</span></span><br/><span data-ttu-id="fd6ec-221">False</span><span class="sxs-lookup"><span data-stu-id="fd6ec-221">False</span></span>|<span data-ttu-id="fd6ec-222">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="fd6ec-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="fd6ec-223">Überprüfen Sie die SBC-Verbindung</span><span class="sxs-lookup"><span data-stu-id="fd6ec-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="fd6ec-224">Überprüfen Sie die Verbindung aus:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-224">Verify the connection:</span></span> 
- <span data-ttu-id="fd6ec-225">Überprüfen Sie, ob in der Liste der kombinierte SBCs der SBC ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="fd6ec-226">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="fd6ec-227">Überprüfen Sie, ob in der Liste der kombinierte SBCs SBC ist</span><span class="sxs-lookup"><span data-stu-id="fd6ec-227">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="fd6ec-228">Überprüfen Sie nachdem Sie die SBC Paar, dass der SBC mithilfe des folgenden Befehls in einer remote-PowerShell-Sitzung in der Liste der kombinierte SBCs vorhanden ist:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="fd6ec-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="fd6ec-229">Kombinierte Gateway sollte in der Liste angezeigt wird, wie im folgenden Beispiel dargestellt, und stellen Sie sicher, dass der Parameter *Enabled* gibt den Wert **True**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="fd6ec-230">Geben Sie ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="fd6ec-231">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-231">Which returns:</span></span>
``` 
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
```

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="fd6ec-232">Überprüfen Sie die Optionen SIP-Fluss</span><span class="sxs-lookup"><span data-stu-id="fd6ec-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="fd6ec-233">Um die Verbindung mit ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Management-Schnittstelle und sehen Sie, dass der SBC 200 OK-Antworten den ausgehenden Optionen abrufen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="fd6ec-234">Beim direkten Routing Optionen für eingehende Faxe erkennt, wird gestartet senden ausgehende Optionen auf den SBC-FQDN im Feld Kopfzeile Kontakt in der eingehenden Nachricht Optionen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="fd6ec-235">Um die Verbindung mit eingehenden SIP-Optionen zu validieren, verwenden Sie die SBC-Management-Schnittstelle und finden Sie, dass der SBC Antwort auf die Optionen für Nachrichten, die von direkten Routing wird und der Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="fd6ec-236">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="fd6ec-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="fd6ec-237">Wenn Sie so aktivieren Sie Benutzer für die direkte Routingdienst bereit sind, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="fd6ec-238">Erstellen eines Benutzers in Office 365 und eine Telefon-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="fd6ec-239">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="fd6ec-240">Konfigurieren Sie die Telefonnummer ein, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="fd6ec-241">Konfigurieren von VoIP-routing.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-241">Configure voice routing.</span></span> <span data-ttu-id="fd6ec-242">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-242">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="fd6ec-243">Erstellen eines Benutzers in Office 365 und Lizenz zuweisen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="fd6ec-244">Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="fd6ec-245">Jedoch wird empfohlen, dass Ihre Organisation wählen und verwenden eine Option, um routing Probleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="fd6ec-246">Erstellen Sie des Benutzers in Active Directory am Standort und synchronisieren Sie den Benutzer in die Cloud zu.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-246">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="fd6ec-247">Finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="fd6ec-248">Erstellen Sie den Benutzer direkt in Office 365-Administrator-Portal.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="fd6ec-249">Finden Sie unter [Benutzer einzeln oder in einer Sammeloperation zu Office 365 - Admin Hilfe hinzufügen](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="fd6ec-250">Wenn Sie das System, das mit Skype für Business 2015 oder Lync 2010/2013 lokal vorhanden ist erstellen, ist die einzige unterstützte Option den Benutzer im lokalen Active Directory erstellen und Synchronisieren des Benutzers in die Cloud (Option 1).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-250">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="fd6ec-251">Lizenzen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-251">Required licenses:</span></span> 

- <span data-ttu-id="fd6ec-252">Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan2 und Teams) + Phone System</span><span class="sxs-lookup"><span data-stu-id="fd6ec-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="fd6ec-253">Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan2, Teams und Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="fd6ec-253">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="fd6ec-254">Optional Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-254">Optional licenses:</span></span> 

- <span data-ttu-id="fd6ec-255">Plan aufrufen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-255">Calling Plan</span></span> 
- <span data-ttu-id="fd6ec-256">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="fd6ec-257">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="fd6ec-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="fd6ec-258">Direktes Routing bewirkt, dass den Benutzer in Skype für Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="fd6ec-259">Sie können dies überprüfen, anhand des RegistrarPool-Parameters.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="fd6ec-260">Es muss einen Wert in der Domäne infra.lync.com verfügen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="fd6ec-261">Verbinden Sie mit remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="fd6ec-262">Geben Sie den Befehl:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="fd6ec-263">Konfigurieren Sie die Telefonnummer ein, und Aktivieren von Enterprise-VoIP und voicemail</span><span class="sxs-lookup"><span data-stu-id="fd6ec-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="fd6ec-264">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt so konfigurieren Sie ihre Telefonnummer und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="fd6ec-265">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-265">This can be done in one step.</span></span> 

<span data-ttu-id="fd6ec-266">So fügen Sie die Telefonnummer, und für Voicemail aktivieren:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="fd6ec-267">Verbinden Sie mit einer remote-PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="fd6ec-268">Geben Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-268">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="fd6ec-269">Um eine Rufnummer für den Benutzer "Software niedrig" hinzuzufügen, würden Sie beispielsweise Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-269">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremisLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="fd6ec-270">Die Rufnummer muss als eine vollständige e. 164-Rufnummer mit Ländercode konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="fd6ec-271">Wenn Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie lokale Skype für Business-Verwaltungsshell oder in der Systemsteuerung so konfigurieren Sie die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="fd6ec-272">Konfigurieren von VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="fd6ec-272">Configure Voice Routing</span></span> 

<span data-ttu-id="fd6ec-273">Microsoft Telefonsystem hat einen routing Mechanismus, der einen Anruf an eine bestimmte SBC basierend auf gesendet werden können:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="fd6ec-274">Nummernmuster aufgerufen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-274">Called number pattern</span></span> 
- <span data-ttu-id="fd6ec-275">Nummernmuster + bestimmte Benutzer, der den Anruf tätigt aufgerufen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="fd6ec-276">SBCs können als aktiv und backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="fd6ec-277">Das bedeutet, wenn der SBC, der für diese Nummernmuster, oder Nummernmuster + bestimmten Benutzer als aktiv konfiguriert ist nicht verfügbar ist, und klicken Sie dann die Anrufe an eine Sicherung SBC weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="fd6ec-278">Anrufrouting aus den folgenden Elementen besteht:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="fd6ec-279">VoIP Routing-Richtlinie – Container für PSTN-Verwendungen; kann an einen Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="fd6ec-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="fd6ec-280">PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; können in unterschiedlichen VoIP-Routing-Richtlinien gemeinsam genutzt werden</span><span class="sxs-lookup"><span data-stu-id="fd6ec-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="fd6ec-281">VoIP-Routen-Muster und einen Satz von Online PSTN-Gateways für Anrufe verwendet, in dem anrufende Nummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="fd6ec-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="fd6ec-282">Online PSTN-Gateway - Zeiger SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Anruf über den SBC, wie P-Asserted-Identity (PAI) nach vorne oder bevorzugte Codecs platziert wird. VoIP-Routen können hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="fd6ec-282">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="fd6ec-283">Erstellen einer VoIP-Routingrichtlinie mit einem PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="fd6ec-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="fd6ec-284">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien zurückgegeben in Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="fd6ec-285">**Call Flow 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf weitergeleitet, um SBC sbc1<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-285">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="fd6ec-286">Wenn weder sbc1<span></span>. contoso.biz noch sbc2<span></span>. contoso.biz verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-286">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="fd6ec-287">**Call Flow 2 (auf der rechten Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf zuerst an SBC sbc1 weitergeleitet<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-287">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="fd6ec-288">Wenn weder SBC verfügbar ist, wird die Route mit niedrigere Priorität versucht (sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="fd6ec-288">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="fd6ec-289">Wenn keines der SBCs verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Beispiele für VoIP routing-Richtlinie](../../media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="fd6ec-291">Während der VoIP-Route Prioritäten zugewiesen wird, werden die SBCs in die Routen in beiden Beispielen in zufälliger Reihenfolge getestet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd6ec-292">Wenn der Benutzer auch eine Microsoft aufrufen planen Lizenz besitzt, werden Anrufe an eine andere Zahl mit Ausnahme der Zielrufnummer entsprechen die Muster + +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="fd6ec-293">Wenn der Benutzer eine Lizenz aufrufen planen verfügt, wird der Anruf automatisch entsprechend den Richtlinien von Microsoft aufrufen planen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="fd6ec-294">Microsoft aufrufen planen automatisch als die letzte Route gilt für alle Benutzer mit der Lizenz Microsoft aufrufen planen und erfordert keine zusätzlichen Aufruf Routingkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="fd6ec-295">Im Beispiel in der folgenden Abbildung wird eine VoIP-Route zum Senden von Anrufen an alle anderen USA und Kanada Nummer (Anrufe, die an das gewählte übersetzende + 1 XXX XXX XX XX umgeleitet) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt VoIP-routing-Richtlinie mit einer dritten route](../../media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="fd6ec-297">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="fd6ec-298">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="fd6ec-299">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd6ec-300">Die Priorität die Wert für die Route "Andere + 1" ist in diesem Fall unerheblich, wie es ist nur eine Route, die dem Muster + 1 entspricht XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-300">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="fd6ec-301">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 herstellt und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="fd6ec-302">In der folgenden Tabelle werden die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="fd6ec-303">In diesem Beispiel werden alle drei Routen Teil der gleichen PSTN-Verwendung "Uns und Kanada" an.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-303">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="fd6ec-304">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-304">**PSTN usage**</span></span>|<span data-ttu-id="fd6ec-305">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-305">**Voice route**</span></span>|<span data-ttu-id="fd6ec-306">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-306">**Number pattern**</span></span>|<span data-ttu-id="fd6ec-307">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-307">**Priority**</span></span>|<span data-ttu-id="fd6ec-308">**SBC**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-308">**SBC**</span></span>|<span data-ttu-id="fd6ec-309">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd6ec-310">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-310">US only</span></span>|<span data-ttu-id="fd6ec-311">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-311">“Redmond 1”</span></span>|<span data-ttu-id="fd6ec-312">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="fd6ec-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="fd6ec-313">1</span><span class="sxs-lookup"><span data-stu-id="fd6ec-313">1</span></span>|<span data-ttu-id="fd6ec-314">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-314">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-315">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-315">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-316">Aktive Route für gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="fd6ec-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="fd6ec-317">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-317">US only</span></span>|<span data-ttu-id="fd6ec-318">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-318">“Redmond 2”</span></span>|<span data-ttu-id="fd6ec-319">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="fd6ec-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="fd6ec-320">2</span><span class="sxs-lookup"><span data-stu-id="fd6ec-320">2</span></span>|<span data-ttu-id="fd6ec-321">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-321">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-322">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-322">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-323">Backup Route für die gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="fd6ec-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="fd6ec-324">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-324">US only</span></span>|<span data-ttu-id="fd6ec-325">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-325">"Other +1”</span></span>|<span data-ttu-id="fd6ec-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fd6ec-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="fd6ec-327">3</span><span class="sxs-lookup"><span data-stu-id="fd6ec-327">3</span></span>|<span data-ttu-id="fd6ec-328">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-328">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-329">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-329">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-330">Weiterleiten von zur gewählte Nummern + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="fd6ec-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="fd6ec-331">Alle Routen die PSTN-Verwendung "Uns und Kanada" zugeordnet sind, und die PSTN-Verwendung der VoIP-Routing-Richtlinie "Nur in den USA." zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="fd6ec-331">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="fd6ec-332">In diesem Beispiel wird der Benutzer Spencer Low VoIP-routing-Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="fd6ec-333">Beispiele für anrufrouten</span><span class="sxs-lookup"><span data-stu-id="fd6ec-333">Examples of call routes</span></span>

<span data-ttu-id="fd6ec-334">Im folgenden Beispiel wir wird gezeigt, wie Routen, PSTN-Verwendungen und Routing Richtlinien konfigurieren, und weisen wir die Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-334">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="fd6ec-335">**Schritt 1:** Erstellen Sie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-335">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="fd6ec-336">Geben Sie in einer Skype für Business Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-336">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="fd6ec-337">Überprüfen Sie, dass die Verwendung durch Eingabe erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="fd6ec-338">Die eine Liste mit Namen zurückgibt, der abgeschnitten werden kann:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="fd6ec-339">Im folgenden Beispiel sehen Sie das Ergebnis der Ausführung der PowerShell-Befehl *`(Get-CSOnlinePSTNUsage).usage`* vollständige Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-339">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
```
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
  ```

<span data-ttu-id="fd6ec-340">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype für Business Online drei Routen: 1, 2 und andere + 1, Redmond "Redmond", wie in der vorherigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="fd6ec-341">Wenn Sie um die Route "" Redmond "1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-341">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="fd6ec-342">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-342">Which returns:</span></span>
```
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
```
<span data-ttu-id="fd6ec-343">Um die Route für Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="fd6ec-344">Um die anderen + 1-Route zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="fd6ec-345">Stellen Sie sicher, dass es sich bei Ihren reguläre Ausdruck in das Attribut NumberPattern Ausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="fd6ec-346">Sie können mithilfe dieser Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="fd6ec-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="fd6ec-347">In einigen Fällen besteht Bedarf für alle Anrufe an den gleichen SBC weitergeleitet. Verwenden Sie - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="fd6ec-348">Alle Anrufe an demselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="fd6ec-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern "." 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="fd6ec-349">Überprüfen Sie, ob Sie die Route durch Ausführen von ordnungsgemäß konfiguriert haben die `Get-CSOnlineVoiceRoute` Powershell-Befehl mit der Optionen wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="fd6ec-350">Die zurückgegeben werden soll:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-350">Which should return:</span></span>
```
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
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
```

<span data-ttu-id="fd6ec-351">Im Beispiel die Route, dass "Andere + 1" automatisch Priorität zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-351">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="fd6ec-352">**Schritt 3:** Erstellen einer VoIP-Routing-Richtlinie "Nur USA" und Hinzufügen der Richtlinie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-352">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="fd6ec-353">Geben Sie in einer PowerShell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="fd6ec-354">In diesem Beispiel wird das Ergebnis gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-354">The result is shown in this example:</span></span>

```
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

<span data-ttu-id="fd6ec-355">**Schritt 4:** Dem Benutzer erteilen Sie Spence Low eine VoIP-routing-Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-355">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="fd6ec-356">Geben Sie in einer Powershell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-356">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="fd6ec-357">Überprüfen Sie die Zuordnung der Richtlinie, indem Sie folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="fd6ec-358">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-358">Which returns:</span></span>
```
OnlineVoiceRoutingPolicy
------------------------
US Only

```

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="fd6ec-359">Erstellen einer VoIP-Routing-Richtlinie mit mehreren PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="fd6ec-360">Die VoIP-Routing-Richtlinie erstellt ermöglicht zuvor nur Anrufe an externe Telefonnummern in den USA und Kanada –, es sei denn, die Lizenz Microsoft aufrufen planen auch dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="fd6ec-361">Im folgenden Beispiel wird, können Sie die VoIP-Routing-Richtlinie "Ohne Einschränkungen." erstellen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-361">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="fd6ec-362">Die Richtlinie verwendet die PSTN-Verwendung "Uns und Kanada" erstellt, die im vorherigen Beispiel als auch die neuen PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-362">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="fd6ec-363">Dies leitet alle anderen Aufrufe der SBCs sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-363">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="fd6ec-364">In den Beispielen, die angezeigt werden Zuweisen von uns nur die Richtlinie für Benutzer "Software niedrig" und keine Einschränkungen für den Benutzer "John Woods".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-364">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="fd6ec-365">Software niedrig – zulässig Anrufe nur für die USA und Kanada Zahlen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="fd6ec-366">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-366">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="fd6ec-367">Außerhalb der USA Zahlen werden nicht weitergeleitet werden, es sei denn, die Lizenz planen aufrufen, das dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="fd6ec-368">John Woods – Anrufe an eine beliebige Anzahl zulässig.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="fd6ec-369">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-369">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="fd6ec-370">Außerhalb der USA Rufnummern weitergeleitet werden über sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-370">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer Spencer Low zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="fd6ec-372">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="fd6ec-373">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="fd6ec-374">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer John Woods zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="fd6ec-376">In der folgenden Tabelle werden die routing Richtlinie "No Einschränkungen" Usage Bezeichnungen und VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-376">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="fd6ec-377">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-377">**PSTN usage**</span></span>|<span data-ttu-id="fd6ec-378">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-378">**Voice route**</span></span>|<span data-ttu-id="fd6ec-379">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-379">**Number pattern**</span></span>|<span data-ttu-id="fd6ec-380">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-380">**Priority**</span></span>|<span data-ttu-id="fd6ec-381">**SBC**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-381">**SBC**</span></span>|<span data-ttu-id="fd6ec-382">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fd6ec-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd6ec-383">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-383">US Only</span></span>|<span data-ttu-id="fd6ec-384">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-384">“Redmond 1”</span></span>|<span data-ttu-id="fd6ec-385">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="fd6ec-385">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="fd6ec-386">1</span><span class="sxs-lookup"><span data-stu-id="fd6ec-386">1</span></span>|<span data-ttu-id="fd6ec-387">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-387">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-388">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-388">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-389">Aktive Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="fd6ec-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="fd6ec-390">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-390">US Only</span></span>|<span data-ttu-id="fd6ec-391">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-391">“Redmond 2”</span></span>|<span data-ttu-id="fd6ec-392">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="fd6ec-392">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="fd6ec-393">2</span><span class="sxs-lookup"><span data-stu-id="fd6ec-393">2</span></span>|<span data-ttu-id="fd6ec-394">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-394">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-395">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-395">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-396">Backup Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="fd6ec-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="fd6ec-397">UNS nur</span><span class="sxs-lookup"><span data-stu-id="fd6ec-397">US Only</span></span>|<span data-ttu-id="fd6ec-398">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="fd6ec-398">“Other +1”</span></span>|<span data-ttu-id="fd6ec-399">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fd6ec-399">^+1(\d{10})$</span></span>|<span data-ttu-id="fd6ec-400">3</span><span class="sxs-lookup"><span data-stu-id="fd6ec-400">3</span></span>|<span data-ttu-id="fd6ec-401">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-401">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-402">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-402">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-403">Route für angerufenen Zahlen + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="fd6ec-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="fd6ec-404">International</span><span class="sxs-lookup"><span data-stu-id="fd6ec-404">International</span></span>|<span data-ttu-id="fd6ec-405">International</span><span class="sxs-lookup"><span data-stu-id="fd6ec-405">International</span></span>|<span data-ttu-id="fd6ec-406">\d+</span><span class="sxs-lookup"><span data-stu-id="fd6ec-406">\d+</span></span>|<span data-ttu-id="fd6ec-407">4</span><span class="sxs-lookup"><span data-stu-id="fd6ec-407">4</span></span>|<span data-ttu-id="fd6ec-408">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-408">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="fd6ec-409">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="fd6ec-409">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="fd6ec-410">Route für alle Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="fd6ec-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="fd6ec-411">Die Reihenfolge der PSTN-Verwendungen in VoIP-Routing-Richtlinien ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="fd6ec-412">Die Verwendungen in Reihenfolge angewendet werden, und wenn in der ersten Verwendung eine Übereinstimmung gefunden wird, klicken Sie dann andere Verwendungen werden nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="fd6ec-413">Die PSTN-Verwendung "International" muss nach der PSTN-Verwendung "Uns nur." platziert werden</span><span class="sxs-lookup"><span data-stu-id="fd6ec-413">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="fd6ec-414">Führen Sie zum Ändern der Reihenfolge der PSTN-Verwendungen, die `Set-CSOnlineRouteRoutingPolicy` Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-414">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="fd6ec-415">Ändern die Reihenfolge von "Uns und Kanada" beispielsweise vor- und "International" Sekunde bis zu der umgekehrten Reihenfolge ausführen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-415">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="fd6ec-416">Die Priorität für "Andere + 1" und "International" VoIP-Routen werden automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-416">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="fd6ec-417">Diese nicht von Bedeutung sind, solange sie niedrigere Prioritäten als "" Redmond "1" und "Redmond 2" besitzen</span><span class="sxs-lookup"><span data-stu-id="fd6ec-417">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="fd6ec-418">Beispiel für VoIP-Routing-Richtlinie für den Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="fd6ec-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="fd6ec-419">Die Schritte zum Erstellen von PSTN-Verwendung "International", VoIP-Route "International", VoIP-Routing-Richtlinie "No Einschränkungen,", und klicken Sie dann den Benutzer "John Woods" zuweisen lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-419">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1.  <span data-ttu-id="fd6ec-420">Erstellen Sie zunächst die PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-420">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="fd6ec-421">Geben Sie in einer PowerShell-Remotesitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  <span data-ttu-id="fd6ec-422">Im nächsten Schritt erstellen Sie die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-422">Next, create the new voice route “International.”</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  <span data-ttu-id="fd6ec-423">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-423">Which returns:</span></span>

  ```
  Identity                  : International 
  Priority                      : 5
  Description                   : 
  NumberPattern                 : \d+
  OnlinePstnUsages          : {International}    
  OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
  Name                            : International
  SupressCallerId           :
  AlternateCallerId         :
  ```
3.  <span data-ttu-id="fd6ec-424">Im nächsten Schritt erstellen Sie eine VoIP-Routing-Richtlinie "Ohne Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="fd6ec-424">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="fd6ec-425">Die PSTN-Verwendung "" Redmond "1" und "Redmond" werden in dieser VoIP-Routingrichtlinie besondere Behandlung für Aufrufe von "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder am Standort Aufrufe nummerieren beibehalten wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-425">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

    <span data-ttu-id="fd6ec-426">Beachten Sie Reihenfolge PSTN-Verwendungen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-426">Take note of the order of PSTN Usages:</span></span>

    <span data-ttu-id="fd6ec-427">a.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-427">a.</span></span> <span data-ttu-id="fd6ec-428">Wenn der Anruf an "+ 1425 XXX XX XX" mit der Verwendungen wie im folgenden Beispiel konfiguriert, den Aufruf folgt die Route in Verwendung "Uns und Kanada" festgelegt und die spezielle Routinglogik angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-428">If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied.</span></span> <span data-ttu-id="fd6ec-429">Das heißt, wird der Anruf über sbc1 weitergeleitet<span></span>. contoso.biz und sbc2<span></span>. contoso.biz und anschließend sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz als die Sicherungen Routen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-429">That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes.</span></span> 

    <span data-ttu-id="fd6ec-430">b.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-430">b.</span></span>  <span data-ttu-id="fd6ec-431">Ist "International" PSTN-Verwendung vor "Uns und Kanada", Anrufe an + 1425 XXX XX XX werden an weitergeleitet, sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz als Teil der Routinglogik.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-431">If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="fd6ec-432">Geben Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-432">Enter the command:</span></span>

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="fd6ec-433">Die zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd6ec-433">Which returns</span></span>

   ```
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
   ```

4.  <span data-ttu-id="fd6ec-434">Weisen Sie die VoIP-routing-Richtlinie für den Benutzer "John Woods" mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-434">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  <span data-ttu-id="fd6ec-435">Überprüfen Sie anschließend die Zuordnung mit dem Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-435">Then verify the assignment using the command:</span></span>   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  <span data-ttu-id="fd6ec-436">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-436">Which returns:</span></span>

  ```
  OnlineVoiceRoutingPolicy
  ------------------------
  No Restrictions
  ```

<span data-ttu-id="fd6ec-437">Das Ergebnis ist, dass die VoIP-Richtlinie auf John Woods Anrufe angewendet werden nicht eingeschränkt, und die Logik des Routings ausgehender Anrufe für den Aufruf von USA, Kanada und International verfügbaren vor.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-437">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="enable-calling-for-microsoft-teams"></a><span data-ttu-id="fd6ec-438">Aktivieren Sie Anrufe für Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="fd6ec-438">Enable Calling for Microsoft Teams</span></span>

<span data-ttu-id="fd6ec-439">Bevor ein Benutzer auf die Registerkarte Anrufe in Microsoft-Teams, sehen kann, müssen Sie private Anrufe für den Mandanten in Microsoft-Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-439">Before a user can see the Calls tab in Microsoft Teams, you need to enable private calling for the tenant in Microsoft Teams.</span></span> <span data-ttu-id="fd6ec-440">Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-440">To do this:</span></span>

1.  <span data-ttu-id="fd6ec-441">Melden Sie sich als mandantenadministrator für das Office 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-441">Sign in as tenant administrator on the Office 365 Admin center.</span></span>
2.  <span data-ttu-id="fd6ec-442">Wechseln Sie zu **Einstellungen und Dienste und -add-ins** , und wählen Sie **Microsoft-Teams**.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-442">Go to **Settings and Services and add-ins** and select **Microsoft Teams**.</span></span> 
3.  <span data-ttu-id="fd6ec-443">Erweitern Sie **Anrufe und Besprechungen** , und überprüfen Sie, dass **Aufrufen von privaten zulassen** **aktiviert**ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-443">Expand **Calls and meetings** and verify that **Allow private calling** is **On**.</span></span>

    ![Screenshot des privaten aufrufen eingeschaltet zulassen.](../../media/ConfigDirectRouting-CallsandMeetingsDialog.png)

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-the-users"></a><span data-ttu-id="fd6ec-445">Festlegen Sie Microsoft-Teams für die Benutzer als bevorzugter Client aufrufende</span><span class="sxs-lookup"><span data-stu-id="fd6ec-445">Set Microsoft Teams as the preferred calling client for the users</span></span>

<span data-ttu-id="fd6ec-446">Direktes Routing leitet Anrufe nur für Microsoft-Teams, müssen Sie sicherstellen, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-446">Direct Routing will route calls only to Microsoft Teams, so you need to make sure that Microsoft Teams is the preferred calling client for the users.</span></span> <span data-ttu-id="fd6ec-447">Dies wird durch die TeamsCallingPolicy und die TeamsInteropPolicy gesteuert.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-447">This is controlled by the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span> 

1. <span data-ttu-id="fd6ec-448">Verwenden Sie das folgende Cmdlet zuerst in einer PowerShell-Remotesitzung in der Skype für Business Online Administrationscenter, welche Richtlinien finden Sie unter der Benutzer zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-448">First, use the following cmdlet in a remote PowerShell session in the Skype for Business Online admin center to see which policies the user has been assigned.</span></span> 

  ```
  Get-CsOnlineUser -identity <User Name> | fl *teams*
  ```
 
2. <span data-ttu-id="fd6ec-449">Im nächsten Schritt überprüfen Sie die andere Richtlinieninstanzen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-449">Next, review the different policy instances.</span></span> 

  ```
  Get-CsTeamsCallingPolicy
  ``` 
<span data-ttu-id="fd6ec-450"> und </span><span class="sxs-lookup"><span data-stu-id="fd6ec-450">and</span></span>

  ```
  Get-CsTeamsInteropPolicy
  ``` 

<span data-ttu-id="fd6ec-451">Bevor Benutzer Microsoft-Teams, den Dienst verwenden können, sind zusätzliche Schritte, die Sie möglicherweise durchführen müssen, um die aufrufende Richtlinie anwenden und Anrufe zulassen.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-451">Before Microsoft Teams users can use the service, there are additional steps you may need to take to apply the calling policy and allow calls.</span></span>

### <a name="teams-calling-policy"></a><span data-ttu-id="fd6ec-452">Aufrufen der Richtlinie Teams</span><span class="sxs-lookup"><span data-stu-id="fd6ec-452">Teams Calling Policy</span></span>

<span data-ttu-id="fd6ec-453">Sie müssen sicherstellen, dass der Benutzer eine TeamsCallingPolicy mit AllowCalling = True.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-453">You need to make sure that the user has a TeamsCallingPolicy with AllowCalling = True.</span></span> <span data-ttu-id="fd6ec-454">Mit dieser Richtlinie kann die globale Richtlinie in Ihrem Mandanten oder eine bestimmte Richtlinie erteilt dem Benutzer sein.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-454">This policy can either be the Global policy in your tenant or a specific policy granted to the user.</span></span> <span data-ttu-id="fd6ec-455">Wenn Sie einem Benutzer eine bestimmte Richtlinie erteilt werden müssen, können Sie das Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-455">If you need to grant a user a specific policy, you can use the cmdlet:</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy> -Identity <User Name>
```

### <a name="teams-interop-policy"></a><span data-ttu-id="fd6ec-456">Teams Interop-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="fd6ec-456">Teams Interop Policy</span></span>

<span data-ttu-id="fd6ec-457">Stellen Sie sicher, dass der Benutzer den aufrufenden bevorzugten Client festzulegen, der Microsoft-Teams, verfügt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-457">Make sure that the user has the preferred calling client to set to Microsoft Teams.</span></span> <span data-ttu-id="fd6ec-458">Dies kann auf zwei Arten erfolgen:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-458">This can be done in two ways:</span></span>

- <span data-ttu-id="fd6ec-459">Der Benutzer festgelegt aufrufenden bevorzugten Client in der Microsoft-Teams, Client.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-459">The user sets the preferred calling client in the Microsoft Teams client.</span></span>
- <span data-ttu-id="fd6ec-460">Der Benutzer hat eine Richtlinie zugewiesen wurde, die aufrufenden bevorzugten Client festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-460">The user has been assigned a policy that sets the preferred calling client.</span></span>

<span data-ttu-id="fd6ec-461">Um eine Richtlinie zuweisen, die Microsoft-Teams, als bevorzugter Client aufrufende festlegt, stellen Sie sicher, dass der Benutzer eine Richtlinie mit CallingDefaultClient eingeholt wurde = Teams.</span><span class="sxs-lookup"><span data-stu-id="fd6ec-461">To assign a policy that sets Microsoft Teams as the preferred calling client, make sure that the user is granted a policy with CallingDefaultClient = Teams.</span></span> <span data-ttu-id="fd6ec-462">Nachfolgend sehen Sie ein Beispiel-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fd6ec-462">An example cmdlet is shown below:</span></span>

```
Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity “<User Name>”
```

## <a name="see-also"></a><span data-ttu-id="fd6ec-463">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd6ec-463">See also</span></span>

[<span data-ttu-id="fd6ec-464">Planen der direkten Routing</span><span class="sxs-lookup"><span data-stu-id="fd6ec-464">Plan Direct Routing</span></span>](plan-direct-routing.md)
