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
ms.openlocfilehash: 8b132174a305e55d79b935ceec5105fcfc1fc2e6
ms.sourcegitcommit: 6c3bf5f453188bc951e92aa26b5562bf6680d4d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19907944"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="2b2e0-103">Konfigurieren der Weiterleitung von direkten</span><span class="sxs-lookup"><span data-stu-id="2b2e0-103">Configure Direct Routing</span></span>

  > [!NOTE]
  > <span data-ttu-id="2b2e0-104">Dies ist eine Vorabversion der Microsoft Phone System direkten Routing.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-104">This is a preview release of Microsoft Phone System Direct Routing.</span></span>  <span data-ttu-id="2b2e0-105">Produktfunktionen und Dokumentation werden können geändert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-105">Product functionality and documentation are subject to change.</span></span>

<span data-ttu-id="2b2e0-106">Wenn Sie dies nicht bereits geschehen ist, lesen [Planen direkten Routing](plan-direct-routing.md) für erforderliche Komponenten und zum Überprüfen der anderen Schritte müssen Sie ergreifen, bevor Sie das Telefonsystem Microsoft-Netzwerk konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-106">If you have not already done so, read [Plan Direct Routing](plan-direct-routing.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="2b2e0-107">Dieses Dokument ist für IT-Experten vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-107">This document is intended for IT professionals.</span></span>  

<span data-ttu-id="2b2e0-108">In diesem Artikel wird beschrieben, wie Microsoft Phone System direkten Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-108">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="2b2e0-109">Es werden wie eine unterstützte Session Border Controller (SBC) zum direkten Routing Kopplung und zum Konfigurieren von Microsoft-Teams, Benutzer zum direkten Routing Verbindung zu im Public Switched Telephone Network, (PSTN) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-109">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2b2e0-110">Um die in diesem Artikel erläuterten Schritte ausgeführt haben, benötigen Administratoren mit PowerShell-Cmdlets vertraut.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2b2e0-111">Weitere Informationen zum Verwenden von PowerShell finden Sie unter [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 

<span data-ttu-id="2b2e0-112">Es wird empfohlen, dass Sie bestätigen, dass Ihre SBC bereits konfiguriert wurde, wie mithilfe des Herstellers Ihres SBC empfohlen:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-112">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="2b2e0-113">Dokumentation zur Bereitstellung von AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2b2e0-113">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="2b2e0-114">Dokumentation zur Bereitstellung von Menüband</span><span class="sxs-lookup"><span data-stu-id="2b2e0-114">Ribbon deployment documentation</span></span>

<span data-ttu-id="2b2e0-115">Sie können Ihr Telefonsystem Microsoft konfigurieren und Aktivieren von Benutzern mithilfe von Direct Routing, und richten Sie Microsoft-Teams, als bevorzugte aufrufenden Clients anhand der folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-115">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="2b2e0-116">Den SBC mit einem Microsoft-Telefonsystem Kopplung und überprüfen die Verbindung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="2b2e0-117">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="2b2e0-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="2b2e0-118">Sicherstellen Sie, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="2b2e0-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-the-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="2b2e0-119">Den SBC um Routingdienst von Telefonsystem leiten Kopplung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-119">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="2b2e0-120">Es folgen drei allgemeinen Schritte ausführen, können Sie eine Verbindung herstellen oder Paaren Sie den SBC mit der direkten Routing-Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="2b2e0-121">Verbinden Sie mit **Skype für Business Online** -Verwaltungskonsole mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b2e0-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="2b2e0-122">Paar die SBC</span><span class="sxs-lookup"><span data-stu-id="2b2e0-122">Pair the SBC</span></span> 
- <span data-ttu-id="2b2e0-123">Überprüfen der Paarung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-123">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="2b2e0-124">Herstellen einer Verbindung mit Skype für Business Online mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b2e0-124">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="2b2e0-125">Eine PowerShell-Sitzung mit dem Mandanten verbunden können Sie den SBC mit der direkten Routing-Schnittstelle Kopplung.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="2b2e0-126">Um eine PowerShell-Sitzung zu öffnen, wenden Sie sich, befolgen Sie die Schritte in [Einrichten des Computers für Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 
 
<span data-ttu-id="2b2e0-127">Nachdem Sie eine PowerShell-Remotesitzung eingerichtet haben, überprüfen Sie, dass Sie die Befehle zum Verwalten des SBC sehen können.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="2b2e0-128">Um die Befehle zu überprüfen, geben Sie ein oder kopieren und Einfügen in der folgenden in der PowerShell-Sitzung und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="2b2e0-129">Der Befehl gibt die hier gezeigten vier Funktionen zurück, mit der Sie die SBCs verwalten können.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-129">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="2b2e0-130">Paar die SBC beziehen, um den Mandanten</span><span class="sxs-lookup"><span data-stu-id="2b2e0-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="2b2e0-131">So Paaren Sie die SBC beziehen, um den Mandanten in die PowerShell-Sitzung Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="2b2e0-132">Es wird dringend empfohlen festlegen einen Grenzwert für den SBC mit Informationen, die in der Dokumentation SBC gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-132">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="2b2e0-133">Der Grenzwert wird eine Benachrichtigung auslösen, wenn SBC Ebene der Kapazität wird.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-133">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="2b2e0-134">Sie können nur den SBC mit FQDN, bei denen der Domänenteil des Namens eine der in Ihrem Mandanten entspricht, außer registrierte Domänen Kopplung \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-134">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="2b2e0-135">Mithilfe von \*. omicrosoft.com Domänennamen wird für die SBC-FQDN-Namen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-135">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="2b2e0-136">Angenommen, Sie haben zwei Domänennamen:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="2b2e0-137">wobei **ABC**".xyz"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-137">**abc**.xyz</span></span><br/><span data-ttu-id="2b2e0-138">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2b2e0-138">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="2b2e0-139">Für den Namen SBC können Sie den Namen sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-139">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="2b2e0-140">Wenn Sie versuchen, den SBC mit einem Namen sbc.xyz.abc Kopplung, wird das System können Sie nicht, wie die Domäne nicht diesen Mandanten gehört.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-140">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="2b2e0-141">Gibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-141">Returns:</span></span>
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
<span data-ttu-id="2b2e0-142">Es sind zusätzliche Optionen, die während der Paarung festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-142">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="2b2e0-143">Im vorherigen Beispiel jedoch nur die mindestens erforderlichen Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-143">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="2b2e0-144">Die folgende Tabelle enthält die zusätzlichen Parameter, die Sie beim Einrichten von Parametern für *Neu CsOnlinePstnGateway*verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-144">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="2b2e0-145">Erforderlich?</span><span class="sxs-lookup"><span data-stu-id="2b2e0-145">Required?</span></span>|<span data-ttu-id="2b2e0-146">Name</span><span class="sxs-lookup"><span data-stu-id="2b2e0-146">Name</span></span>|<span data-ttu-id="2b2e0-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-147">Description</span></span>|<span data-ttu-id="2b2e0-148">Standard</span><span class="sxs-lookup"><span data-stu-id="2b2e0-148">Default</span></span>|<span data-ttu-id="2b2e0-149">Mögliche Werte</span><span class="sxs-lookup"><span data-stu-id="2b2e0-149">Possible values</span></span>|<span data-ttu-id="2b2e0-150">Typ und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-150">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b2e0-151">Ja</span><span class="sxs-lookup"><span data-stu-id="2b2e0-151">Yes</span></span>|<span data-ttu-id="2b2e0-152">FQDN</span><span class="sxs-lookup"><span data-stu-id="2b2e0-152">FQDN</span></span>|<span data-ttu-id="2b2e0-153">Den Vollqualifizierten Domänennamen der SBC</span><span class="sxs-lookup"><span data-stu-id="2b2e0-153">The FQDN name of the SBC</span></span> |<span data-ttu-id="2b2e0-154">Keine</span><span class="sxs-lookup"><span data-stu-id="2b2e0-154">None</span></span>|<span data-ttu-id="2b2e0-155">NoneFQDN Name, Grenzwert 63 Zeichen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-155">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="2b2e0-156">Zeichenfolge, die Liste der zulässigen / nicht zulässigen Zeichen auf [Namenskonventionen in Active Directory für Computer, Domänen, Sites und OUs](https://support.microsoft.com/en-us/help/909264)</span><span class="sxs-lookup"><span data-stu-id="2b2e0-156">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/en-us/help/909264)</span></span>|
|<span data-ttu-id="2b2e0-157">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-157">No</span></span>|<span data-ttu-id="2b2e0-158">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="2b2e0-158">MediaBypass</span></span> |<span data-ttu-id="2b2e0-159">Der Parameter für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-159">The parameter reserved for future use.</span></span> <span data-ttu-id="2b2e0-160">Unterstützt die Medienumgehung der Parameter angegeben, der die SBC und der Administrator möchte, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-160">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="2b2e0-161">Keine</span><span class="sxs-lookup"><span data-stu-id="2b2e0-161">None</span></span>|<span data-ttu-id="2b2e0-162">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-162">True</span></span><br/><span data-ttu-id="2b2e0-163">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-163">False</span></span>|<span data-ttu-id="2b2e0-164">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2b2e0-164">Boolean</span></span>|
|<span data-ttu-id="2b2e0-165">Ja</span><span class="sxs-lookup"><span data-stu-id="2b2e0-165">Yes</span></span>|<span data-ttu-id="2b2e0-166">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="2b2e0-166">SipSignallingPort</span></span> |<span data-ttu-id="2b2e0-167">Überwachungsport für die Kommunikation mit direktem Routing Services mithilfe des Protokolls Transport Layer Security (TLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-167">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="2b2e0-168">Keine</span><span class="sxs-lookup"><span data-stu-id="2b2e0-168">None</span></span>|<span data-ttu-id="2b2e0-169">Alle Ports</span><span class="sxs-lookup"><span data-stu-id="2b2e0-169">Any port</span></span>|<span data-ttu-id="2b2e0-170">zwischen 0 und 65535</span><span class="sxs-lookup"><span data-stu-id="2b2e0-170">0 to 65535</span></span> |
|<span data-ttu-id="2b2e0-171">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-171">No</span></span>|<span data-ttu-id="2b2e0-172">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="2b2e0-172">FailoverTimeSeconds</span></span> |<span data-ttu-id="2b2e0-173">Bei Festlegung auf 10 (Standardwert), ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden an den nächsten verfügbaren Trunk weitergeleitet werden; Wenn keine zusätzlichen Trunks vorhanden sind, wird der Anruf automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-173">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="2b2e0-174">In einer Organisation mit langsamen Netzwerken und Gateway Antworten möglich, die potenziell Anrufe unnötig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-174">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="2b2e0-175">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-175">The default value is 10.</span></span>|<span data-ttu-id="2b2e0-176">10</span><span class="sxs-lookup"><span data-stu-id="2b2e0-176">10</span></span>|<span data-ttu-id="2b2e0-177">Number</span><span class="sxs-lookup"><span data-stu-id="2b2e0-177">Number</span></span>|<span data-ttu-id="2b2e0-178">Int</span><span class="sxs-lookup"><span data-stu-id="2b2e0-178">Int</span></span>|
|<span data-ttu-id="2b2e0-179">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-179">No</span></span>|<span data-ttu-id="2b2e0-180">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="2b2e0-180">ForwardCallHistory</span></span> |<span data-ttu-id="2b2e0-181">Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-181">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="2b2e0-182">Falls aktiviert, sendet der Office 365-PSTN-Proxy zwei Header: "History-Info" und weitergeleitet durch.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-182">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="2b2e0-183">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-183">The default value is **False** ($False).</span></span> |<span data-ttu-id="2b2e0-184">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-184">False</span></span>|<span data-ttu-id="2b2e0-185">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-185">True</span></span><br/><span data-ttu-id="2b2e0-186">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-186">False</span></span>|<span data-ttu-id="2b2e0-187">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2b2e0-187">Boolean</span></span>|
|<span data-ttu-id="2b2e0-188">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-188">No</span></span>|<span data-ttu-id="2b2e0-189">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="2b2e0-189">ForwardPAI</span></span>|<span data-ttu-id="2b2e0-190">Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-190">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="2b2e0-191">Mit dem PAI-Header lässt sich die Identität des Anrufers überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-191">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="2b2e0-192">Der Standardwert ist **"false"** ($False).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-192">The default value is **False** ($False).</span></span>|<span data-ttu-id="2b2e0-193">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-193">False</span></span>|<span data-ttu-id="2b2e0-194">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-194">True</span></span><br/><span data-ttu-id="2b2e0-195">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-195">False</span></span>|<span data-ttu-id="2b2e0-196">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2b2e0-196">Boolean</span></span>|
|<span data-ttu-id="2b2e0-197">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-197">No</span></span>|<span data-ttu-id="2b2e0-198">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="2b2e0-198">SendSIPOptions</span></span> |<span data-ttu-id="2b2e0-199">Legt fest, ob ein SBC wird oder die SIP-Optionen wird nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-199">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="2b2e0-200">Wenn deaktiviert, wird der SBC aus der Überwachung und Warnung System ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-200">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="2b2e0-201">Es wird dringend empfohlen, dass Sie SIP-Optionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-201">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="2b2e0-202">Standardwert ist **True**.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-202">Default value is **True**.</span></span> |<span data-ttu-id="2b2e0-203">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-203">True</span></span>|<span data-ttu-id="2b2e0-204">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-204">True</span></span><br/><span data-ttu-id="2b2e0-205">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-205">False</span></span>|<span data-ttu-id="2b2e0-206">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2b2e0-206">Boolean</span></span>|
|<span data-ttu-id="2b2e0-207">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-207">No</span></span>|<span data-ttu-id="2b2e0-208">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="2b2e0-208">MaxConcurrentSessions</span></span> |<span data-ttu-id="2b2e0-209">Wird vom System Warnungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-209">Used by alerting system.</span></span> <span data-ttu-id="2b2e0-210">Wenn Sie einen beliebigen Wert festgelegt ist, generieren Alarm System eine Benachrichtigung an den mandantenadministrator wird die Anzahl der gleichzeitigen Sitzung 90 % oder höher ist als dieser Wert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-210">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="2b2e0-211">Wenn der Parameter nicht festgelegt ist, werden keine Benachrichtigungen generiert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-211">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="2b2e0-212">Jedoch meldet das System der Überwachung Anzahl gleichzeitiger Sitzungen alle 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-212">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="2b2e0-213">NULL</span><span class="sxs-lookup"><span data-stu-id="2b2e0-213">Null</span></span>|<span data-ttu-id="2b2e0-214">NULL</span><span class="sxs-lookup"><span data-stu-id="2b2e0-214">Null</span></span><br/><span data-ttu-id="2b2e0-215">1 bis 100.000</span><span class="sxs-lookup"><span data-stu-id="2b2e0-215">1 to 100,000</span></span> ||
|<span data-ttu-id="2b2e0-216">Nein</span><span class="sxs-lookup"><span data-stu-id="2b2e0-216">No</span></span>|<span data-ttu-id="2b2e0-217">Aktiviert \*</span><span class="sxs-lookup"><span data-stu-id="2b2e0-217">Enabled\*</span></span>|<span data-ttu-id="2b2e0-218">Zum Aktivieren dieser SBC für ausgehende Anrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-218">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="2b2e0-219">Kann verwendet werden, um die SBC vorübergehend zu entfernen, während er aktualisiert wird oder während der Wartung.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-219">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="2b2e0-220">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-220">False</span></span>|<span data-ttu-id="2b2e0-221">True</span><span class="sxs-lookup"><span data-stu-id="2b2e0-221">True</span></span><br/><span data-ttu-id="2b2e0-222">False</span><span class="sxs-lookup"><span data-stu-id="2b2e0-222">False</span></span>|<span data-ttu-id="2b2e0-223">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="2b2e0-223">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="2b2e0-224">Überprüfen Sie die SBC-Verbindung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-224">Verify the SBC pairing</span></span> 

<span data-ttu-id="2b2e0-225">Überprüfen Sie die Verbindung aus:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-225">Verify the connection:</span></span> 
- <span data-ttu-id="2b2e0-226">Überprüfen Sie, ob in der Liste der kombinierte SBCs der SBC ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-226">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="2b2e0-227">Überprüfen Sie die SIP-Optionen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-227">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="2b2e0-228">Überprüfen Sie, ob in der Liste der kombinierte SBCs SBC ist</span><span class="sxs-lookup"><span data-stu-id="2b2e0-228">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="2b2e0-229">Überprüfen Sie nachdem Sie die SBC Paar, dass der SBC mithilfe des folgenden Befehls in einer remote-PowerShell-Sitzung in der Liste der kombinierte SBCs vorhanden ist:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="2b2e0-229">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="2b2e0-230">Kombinierte Gateway sollte in der Liste angezeigt wird, wie im folgenden Beispiel dargestellt, und stellen Sie sicher, dass der Parameter *Enabled* gibt den Wert **True**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-230">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="2b2e0-231">Geben Sie ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-231">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="2b2e0-232">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-232">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="2b2e0-233">Überprüfen Sie die Optionen SIP-Fluss</span><span class="sxs-lookup"><span data-stu-id="2b2e0-233">Validate SIP Options flow</span></span> 

<span data-ttu-id="2b2e0-234">Um die Verbindung mit ausgehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Management-Schnittstelle und sehen Sie, dass der SBC 200 OK-Antworten den ausgehenden Optionen abrufen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-234">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="2b2e0-235">Beim direkten Routing Optionen für eingehende Faxe erkennt, wird gestartet senden ausgehende Optionen auf den SBC-FQDN im Feld Kopfzeile Kontakt in der eingehenden Nachricht Optionen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-235">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="2b2e0-236">Um die Verbindung mit eingehenden SIP-Optionen zu validieren, verwenden Sie die SBC-Management-Schnittstelle und finden Sie, dass der SBC Antwort auf die Optionen für Nachrichten, die von direkten Routing wird und der Antwortcode 200 OK ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-236">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="2b2e0-237">Aktivieren von Benutzern für direkte Routingdienst</span><span class="sxs-lookup"><span data-stu-id="2b2e0-237">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="2b2e0-238">Wenn Sie so aktivieren Sie Benutzer für die direkte Routingdienst bereit sind, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-238">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="2b2e0-239">Erstellen eines Benutzers in Office 365 und eine Telefon-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-239">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="2b2e0-240">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-240">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="2b2e0-241">Konfigurieren Sie die Telefonnummer ein, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-241">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="2b2e0-242">Konfigurieren von VoIP-routing.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-242">Configure voice routing.</span></span> <span data-ttu-id="2b2e0-243">Die Route wird automatisch überprüft.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-243">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="2b2e0-244">Erstellen eines Benutzers in Office 365 und Lizenz zuweisen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-244">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="2b2e0-245">Es gibt zwei Optionen zum Erstellen eines neuen Benutzers in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-245">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="2b2e0-246">Jedoch wird empfohlen, dass Ihre Organisation wählen und verwenden eine Option, um routing Probleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-246">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="2b2e0-247">Erstellen Sie des Benutzers in Active Directory am Standort und synchronisieren Sie den Benutzer in die Cloud zu.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-247">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="2b2e0-248">Finden Sie unter [integrieren Ihre lokale Verzeichnisse mit Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-248">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="2b2e0-249">Erstellen Sie den Benutzer direkt in Office 365-Administrator-Portal.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-249">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="2b2e0-250">Finden Sie unter [Benutzer einzeln oder in einer Sammeloperation zu Office 365 - Admin Hilfe hinzufügen](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-250">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="2b2e0-251">Wenn Sie das System, das mit Skype für Business 2015 oder Lync 2010/2013 lokal vorhanden ist erstellen, ist die einzige unterstützte Option den Benutzer im lokalen Active Directory erstellen und Synchronisieren des Benutzers in die Cloud (Option 1).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-251">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="2b2e0-252">Lizenzen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-252">Required licenses:</span></span> 

- <span data-ttu-id="2b2e0-253">Office 365 Enterprise E3 (einschließlich SfB Plan2, Exchange Plan2 und Teams) + Phone System</span><span class="sxs-lookup"><span data-stu-id="2b2e0-253">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="2b2e0-254">Office 365 Enterprise E5 (einschließlich SfB Plan2, Exchange Plan2, Teams und Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="2b2e0-254">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="2b2e0-255">Optional Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-255">Optional licenses:</span></span> 

- <span data-ttu-id="2b2e0-256">Plan aufrufen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-256">Calling Plan</span></span> 
- <span data-ttu-id="2b2e0-257">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-257">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="2b2e0-258">Stellen Sie sicher, dass der Benutzer in Skype für Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="2b2e0-258">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="2b2e0-259">Direktes Routing bewirkt, dass den Benutzer in Skype für Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-259">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="2b2e0-260">Sie können dies überprüfen, anhand des RegistrarPool-Parameters.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-260">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="2b2e0-261">Es muss einen Wert in der Domäne infra.lync.com verfügen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-261">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="2b2e0-262">Verbinden Sie mit remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-262">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="2b2e0-263">Geben Sie den Befehl:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-263">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="2b2e0-264">Konfigurieren Sie die Telefonnummer ein, und Aktivieren von Enterprise-VoIP und voicemail</span><span class="sxs-lookup"><span data-stu-id="2b2e0-264">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="2b2e0-265">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt so konfigurieren Sie ihre Telefonnummer und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-265">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="2b2e0-266">Dies kann in einem Schritt erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-266">This can be done in one step.</span></span> 

<span data-ttu-id="2b2e0-267">So fügen Sie die Telefonnummer, und für Voicemail aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-267">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="2b2e0-268">Verbinden Sie mit einer remote-PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-268">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="2b2e0-269">Geben Sie den Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-269">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="2b2e0-270">Um eine Rufnummer für den Benutzer "Software niedrig" hinzuzufügen, würden Sie beispielsweise Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-270">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="2b2e0-271">Die Rufnummer muss als eine vollständige e. 164-Rufnummer mit Ländercode konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-271">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="2b2e0-272">Wenn Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie lokale Skype für Business-Verwaltungsshell oder in der Systemsteuerung so konfigurieren Sie die Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-272">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="2b2e0-273">Konfigurieren von VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="2b2e0-273">Configure Voice Routing</span></span> 

<span data-ttu-id="2b2e0-274">Microsoft Telefonsystem hat einen routing Mechanismus, der einen Anruf an eine bestimmte SBC basierend auf gesendet werden können:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-274">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="2b2e0-275">Nummernmuster aufgerufen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-275">Called number pattern</span></span> 
- <span data-ttu-id="2b2e0-276">Nummernmuster + bestimmte Benutzer, der den Anruf tätigt aufgerufen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-276">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="2b2e0-277">SBCs können als aktiv und backup festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-277">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="2b2e0-278">Das bedeutet, wenn der SBC, der für diese Nummernmuster, oder Nummernmuster + bestimmten Benutzer als aktiv konfiguriert ist nicht verfügbar ist, und klicken Sie dann die Anrufe an eine Sicherung SBC weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-278">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="2b2e0-279">Anrufrouting aus den folgenden Elementen besteht:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-279">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="2b2e0-280">VoIP Routing-Richtlinie – Container für PSTN-Verwendungen; kann an einen Benutzer oder mehreren Benutzern zugewiesen werden</span><span class="sxs-lookup"><span data-stu-id="2b2e0-280">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="2b2e0-281">PSTN-Verwendungen – Container für VoIP-Routen und PSTN-Verwendungen; können in unterschiedlichen VoIP-Routing-Richtlinien gemeinsam genutzt werden</span><span class="sxs-lookup"><span data-stu-id="2b2e0-281">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="2b2e0-282">VoIP-Routen-Muster und einen Satz von Online PSTN-Gateways für Anrufe verwendet, in dem anrufende Nummer mit dem Muster übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="2b2e0-282">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="2b2e0-283">Online PSTN-Gateway - Zeiger SBC, speichert auch die Konfiguration, die angewendet wird, wenn der Anruf über den SBC, wie P-Asserted-Identity (PAI) nach vorne oder bevorzugte Codecs platziert wird. VoIP-Routen können hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="2b2e0-283">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="2b2e0-284">Erstellen einer VoIP-Routingrichtlinie mit einem PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="2b2e0-284">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="2b2e0-285">Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routingrichtlinien zurückgegeben in Anruffluss.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-285">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="2b2e0-286">**Call Flow 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf weitergeleitet, um SBC sbc1<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-286">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="2b2e0-287">Wenn weder sbc1<span></span>. contoso.biz noch sbc2<span></span>. contoso.biz verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-287">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="2b2e0-288">**Call Flow 2 (auf der rechten Seite):** Wenn ein Benutzer einen Anruf an +1 425 XXX XX XX oder +1 206 XXX XX XX herstellt, wird der Anruf zuerst an SBC sbc1 weitergeleitet<span></span>. contoso.biz oder sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-288">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="2b2e0-289">Wenn weder SBC verfügbar ist, wird die Route mit niedrigere Priorität versucht (sbc3<span></span>. contoso.biz und sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="2b2e0-289">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="2b2e0-290">Wenn keines der SBCs verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-290">If none of the SBCs are available, the call is dropped.</span></span> 

![Beispiele für VoIP routing-Richtlinie](../../media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="2b2e0-292">Während der VoIP-Route Prioritäten zugewiesen wird, werden die SBCs in die Routen in beiden Beispielen in zufälliger Reihenfolge getestet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-292">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2b2e0-293">Wenn der Benutzer auch eine Microsoft aufrufen planen Lizenz besitzt, werden Anrufe an eine andere Zahl mit Ausnahme der Zielrufnummer entsprechen die Muster + +1 425 XXX XX XX oder +1 206 XXX XX XX in der Beispielkonfiguration gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-293">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="2b2e0-294">Wenn der Benutzer eine Lizenz aufrufen planen verfügt, wird der Anruf automatisch entsprechend den Richtlinien von Microsoft aufrufen planen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-294">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="2b2e0-295">Microsoft aufrufen planen automatisch als die letzte Route gilt für alle Benutzer mit der Lizenz Microsoft aufrufen planen und erfordert keine zusätzlichen Aufruf Routingkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-295">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="2b2e0-296">Im Beispiel in der folgenden Abbildung wird eine VoIP-Route zum Senden von Anrufen an alle anderen USA und Kanada Nummer (Anrufe, die an das gewählte übersetzende + 1 XXX XXX XX XX umgeleitet) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-296">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Zeigt VoIP-routing-Richtlinie mit einer dritten route](../../media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="2b2e0-298">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-298">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2b2e0-299">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-299">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2b2e0-300">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-300">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2b2e0-301">Die Priorität die Wert für die Route "Andere + 1" ist in diesem Fall unerheblich, wie es ist nur eine Route, die dem Muster + 1 entspricht XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-301">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="2b2e0-302">Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 herstellt und sbc5.contoso.biz und sbc6.contoso.biz nicht verfügbar sind, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-302">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="2b2e0-303">In der folgenden Tabelle werden die Konfiguration mit drei VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-303">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="2b2e0-304">In diesem Beispiel werden alle drei Routen Teil der gleichen PSTN-Verwendung "Uns und Kanada" an.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-304">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="2b2e0-305">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-305">**PSTN usage**</span></span>|<span data-ttu-id="2b2e0-306">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-306">**Voice route**</span></span>|<span data-ttu-id="2b2e0-307">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-307">**Number pattern**</span></span>|<span data-ttu-id="2b2e0-308">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-308">**Priority**</span></span>|<span data-ttu-id="2b2e0-309">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-309">**SBC**</span></span>|<span data-ttu-id="2b2e0-310">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-310">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b2e0-311">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-311">US only</span></span>|<span data-ttu-id="2b2e0-312">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-312">“Redmond 1”</span></span>|<span data-ttu-id="2b2e0-313">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="2b2e0-313">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2b2e0-314">1</span><span class="sxs-lookup"><span data-stu-id="2b2e0-314">1</span></span>|<span data-ttu-id="2b2e0-315">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-315">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-316">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-316">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-317">Aktive Route für gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2b2e0-317">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2b2e0-318">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-318">US only</span></span>|<span data-ttu-id="2b2e0-319">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-319">“Redmond 2”</span></span>|<span data-ttu-id="2b2e0-320">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="2b2e0-320">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2b2e0-321">2</span><span class="sxs-lookup"><span data-stu-id="2b2e0-321">2</span></span>|<span data-ttu-id="2b2e0-322">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-322">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-323">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-323">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-324">Backup Route für die gewählte Nummern +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2b2e0-324">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2b2e0-325">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-325">US only</span></span>|<span data-ttu-id="2b2e0-326">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-326">"Other +1”</span></span>|<span data-ttu-id="2b2e0-327">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2b2e0-327">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2b2e0-328">3</span><span class="sxs-lookup"><span data-stu-id="2b2e0-328">3</span></span>|<span data-ttu-id="2b2e0-329">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-329">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-330">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-330">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-331">Weiterleiten von zur gewählte Nummern + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2b2e0-331">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="2b2e0-332">Alle Routen die PSTN-Verwendung "Uns und Kanada" zugeordnet sind, und die PSTN-Verwendung der VoIP-Routing-Richtlinie "Nur in den USA." zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="2b2e0-332">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="2b2e0-333">In diesem Beispiel wird der Benutzer Spencer Low VoIP-routing-Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-333">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="2b2e0-334">Beispiele für anrufrouten</span><span class="sxs-lookup"><span data-stu-id="2b2e0-334">Examples of call routes</span></span>

<span data-ttu-id="2b2e0-335">Im folgenden Beispiel wir wird gezeigt, wie Routen, PSTN-Verwendungen und Routing Richtlinien konfigurieren, und weisen wir die Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-335">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="2b2e0-336">**Schritt 1:** Erstellen Sie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-336">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="2b2e0-337">Geben Sie in einer Skype für Business Remote-PowerShell-Sitzung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-337">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="2b2e0-338">Überprüfen Sie, dass die Verwendung durch Eingabe erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-338">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="2b2e0-339">Die eine Liste mit Namen zurückgibt, der abgeschnitten werden kann:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-339">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="2b2e0-340">Im folgenden Beispiel sehen Sie das Ergebnis der Ausführung der PowerShell-Befehl *`(Get-CSOnlinePSTNUsage).usage`* vollständige Namen (nicht abgeschnitten) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-340">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="2b2e0-341">**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype für Business Online drei Routen: 1, 2 und andere + 1, Redmond "Redmond", wie in der vorherigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-341">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="2b2e0-342">Wenn Sie um die Route "" Redmond "1" zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-342">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="2b2e0-343">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-343">Which returns:</span></span>
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
<span data-ttu-id="2b2e0-344">Um die Route für Redmond 2 zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-344">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2b2e0-345">Um die anderen + 1-Route zu erstellen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-345">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="2b2e0-346">Stellen Sie sicher, dass es sich bei Ihren reguläre Ausdruck in das Attribut NumberPattern Ausdruck zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-346">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="2b2e0-347">Sie können mithilfe dieser Website testen:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="2b2e0-347">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="2b2e0-348">In einigen Fällen besteht Bedarf für alle Anrufe an den gleichen SBC weitergeleitet. Verwenden Sie - NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-348">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="2b2e0-349">Alle Anrufe an demselben SBC weiterleiten</span><span class="sxs-lookup"><span data-stu-id="2b2e0-349">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="2b2e0-350">Überprüfen Sie, ob Sie die Route durch Ausführen von ordnungsgemäß konfiguriert haben die `Get-CSOnlineVoiceRoute` Powershell-Befehl mit der Optionen wie dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-350">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="2b2e0-351">Die zurückgegeben werden soll:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-351">Which should return:</span></span>
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

<span data-ttu-id="2b2e0-352">Im Beispiel die Route, dass "Andere + 1" automatisch Priorität zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-352">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="2b2e0-353">**Schritt 3:** Erstellen einer VoIP-Routing-Richtlinie "Nur USA" und Hinzufügen der Richtlinie die PSTN-Verwendung "USA und Kanada".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-353">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="2b2e0-354">Geben Sie in einer PowerShell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-354">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2b2e0-355">In diesem Beispiel wird das Ergebnis gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-355">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="2b2e0-356">**Schritt 4:** Dem Benutzer erteilen Sie Spence Low eine VoIP-routing-Richtlinie mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-356">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="2b2e0-357">Geben Sie in einer Powershell-Sitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-357">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="2b2e0-358">Überprüfen Sie die Zuordnung der Richtlinie, indem Sie folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-358">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="2b2e0-359">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-359">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="2b2e0-360">Erstellen einer VoIP-Routing-Richtlinie mit mehreren PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-360">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="2b2e0-361">Die VoIP-Routing-Richtlinie erstellt ermöglicht zuvor nur Anrufe an externe Telefonnummern in den USA und Kanada –, es sei denn, die Lizenz Microsoft aufrufen planen auch dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-361">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="2b2e0-362">Im folgenden Beispiel wird, können Sie die VoIP-Routing-Richtlinie "Ohne Einschränkungen." erstellen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-362">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="2b2e0-363">Die Richtlinie verwendet die PSTN-Verwendung "Uns und Kanada" erstellt, die im vorherigen Beispiel als auch die neuen PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-363">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="2b2e0-364">Dies leitet alle anderen Aufrufe der SBCs sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-364">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="2b2e0-365">In den Beispielen, die angezeigt werden Zuweisen von uns nur die Richtlinie für Benutzer "Software niedrig" und keine Einschränkungen für den Benutzer "John Woods".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-365">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="2b2e0-366">Software niedrig – zulässig Anrufe nur für die USA und Kanada Zahlen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-366">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="2b2e0-367">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-367">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2b2e0-368">Außerhalb der USA Zahlen werden nicht weitergeleitet werden, es sei denn, die Lizenz planen aufrufen, das dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-368">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="2b2e0-369">John Woods – Anrufe an eine beliebige Anzahl zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-369">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="2b2e0-370">Beim Aufruf von zu "Redmond" Nummern, muss dem spezifischen Berechtigungssatz SBC verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-370">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2b2e0-371">Außerhalb der USA Rufnummern weitergeleitet werden über sbc2<span></span>. contoso.biz und sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-371">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer Spencer Low zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="2b2e0-373">Verfügt ein Benutzer sowohl Lizenzen (Microsoft Telefonsystem und Microsoft aufrufen planen), wird für alle Anrufe automatisch Route verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-373">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2b2e0-374">Wenn keine der rufnummernmuster in die der Administrator erstellt online VoIP-Routen, Route über Microsoft aufrufen Plan übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-374">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2b2e0-375">Wenn der Benutzer nur Microsoft Telefonsystem verfügt, wird der Anruf getrennt, da keine passenden Regeln zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-375">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Zeigt die VoIP-Routingrichtlinie Benutzer John Woods zugewiesen ist](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="2b2e0-377">In der folgenden Tabelle werden die routing Richtlinie "No Einschränkungen" Usage Bezeichnungen und VoIP-Routen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-377">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="2b2e0-378">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-378">**PSTN usage**</span></span>|<span data-ttu-id="2b2e0-379">**VoIP-route**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-379">**Voice route**</span></span>|<span data-ttu-id="2b2e0-380">**Nummernmuster**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-380">**Number pattern**</span></span>|<span data-ttu-id="2b2e0-381">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-381">**Priority**</span></span>|<span data-ttu-id="2b2e0-382">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-382">**SBC**</span></span>|<span data-ttu-id="2b2e0-383">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2b2e0-383">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b2e0-384">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-384">US Only</span></span>|<span data-ttu-id="2b2e0-385">"" Redmond "1"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-385">“Redmond 1”</span></span>|<span data-ttu-id="2b2e0-386">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="2b2e0-386">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2b2e0-387">1</span><span class="sxs-lookup"><span data-stu-id="2b2e0-387">1</span></span>|<span data-ttu-id="2b2e0-388">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-388">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-389">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-389">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-390">Aktive Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2b2e0-390">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2b2e0-391">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-391">US Only</span></span>|<span data-ttu-id="2b2e0-392">"" Redmond "2"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-392">“Redmond 2”</span></span>|<span data-ttu-id="2b2e0-393">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="2b2e0-393">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2b2e0-394">2</span><span class="sxs-lookup"><span data-stu-id="2b2e0-394">2</span></span>|<span data-ttu-id="2b2e0-395">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-395">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-396">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-396">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-397">Backup Route für angerufenen Zahlen +1 425 XXX XX XX oder +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2b2e0-397">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2b2e0-398">UNS nur</span><span class="sxs-lookup"><span data-stu-id="2b2e0-398">US Only</span></span>|<span data-ttu-id="2b2e0-399">"Andere + 1"</span><span class="sxs-lookup"><span data-stu-id="2b2e0-399">“Other +1”</span></span>|<span data-ttu-id="2b2e0-400">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2b2e0-400">^+1(\d{10})$</span></span>|<span data-ttu-id="2b2e0-401">3</span><span class="sxs-lookup"><span data-stu-id="2b2e0-401">3</span></span>|<span data-ttu-id="2b2e0-402">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-402">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-403">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-403">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-404">Route für angerufenen Zahlen + 1 XXX XXX XX XX (mit Ausnahme von +1 425 XXX XX XX oder +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2b2e0-404">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="2b2e0-405">International</span><span class="sxs-lookup"><span data-stu-id="2b2e0-405">International</span></span>|<span data-ttu-id="2b2e0-406">International</span><span class="sxs-lookup"><span data-stu-id="2b2e0-406">International</span></span>|<span data-ttu-id="2b2e0-407">\d+</span><span class="sxs-lookup"><span data-stu-id="2b2e0-407">\d+</span></span>|<span data-ttu-id="2b2e0-408">4</span><span class="sxs-lookup"><span data-stu-id="2b2e0-408">4</span></span>|<span data-ttu-id="2b2e0-409">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-409">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="2b2e0-410">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2b2e0-410">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="2b2e0-411">Route für alle Nummernmuster</span><span class="sxs-lookup"><span data-stu-id="2b2e0-411">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="2b2e0-412">Die Reihenfolge der PSTN-Verwendungen in VoIP-Routing-Richtlinien ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-412">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="2b2e0-413">Die Verwendungen in Reihenfolge angewendet werden, und wenn in der ersten Verwendung eine Übereinstimmung gefunden wird, klicken Sie dann andere Verwendungen werden nie ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-413">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="2b2e0-414">Die PSTN-Verwendung "International" muss nach der PSTN-Verwendung "Uns nur." platziert werden</span><span class="sxs-lookup"><span data-stu-id="2b2e0-414">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="2b2e0-415">Führen Sie zum Ändern der Reihenfolge der PSTN-Verwendungen, die `Set-CSOnlineRouteRoutingPolicy` Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-415">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="2b2e0-416">Ändern die Reihenfolge von "Uns und Kanada" beispielsweise vor- und "International" Sekunde bis zu der umgekehrten Reihenfolge ausführen:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-416">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="2b2e0-417">Die Priorität für "Andere + 1" und "International" VoIP-Routen werden automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-417">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="2b2e0-418">Diese nicht von Bedeutung sind, solange sie niedrigere Prioritäten als "" Redmond "1" und "Redmond 2" besitzen</span><span class="sxs-lookup"><span data-stu-id="2b2e0-418">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="2b2e0-419">Beispiel für VoIP-Routing-Richtlinie für den Benutzer John Woods</span><span class="sxs-lookup"><span data-stu-id="2b2e0-419">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="2b2e0-420">Die Schritte zum Erstellen von PSTN-Verwendung "International", VoIP-Route "International", VoIP-Routing-Richtlinie "No Einschränkungen,", und klicken Sie dann den Benutzer "John Woods" zuweisen lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-420">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1.  <span data-ttu-id="2b2e0-421">Erstellen Sie zunächst die PSTN-Verwendung "International".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-421">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="2b2e0-422">Geben Sie in einer PowerShell-Remotesitzung in Skype für Business Online Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-422">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  <span data-ttu-id="2b2e0-423">Im nächsten Schritt erstellen Sie die neue VoIP-Route "International".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-423">Next, create the new voice route “International.”</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  <span data-ttu-id="2b2e0-424">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-424">Which returns:</span></span>

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
3.  <span data-ttu-id="2b2e0-425">Im nächsten Schritt erstellen Sie eine VoIP-Routing-Richtlinie "Ohne Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="2b2e0-425">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="2b2e0-426">Die PSTN-Verwendung "" Redmond "1" und "Redmond" werden in dieser VoIP-Routingrichtlinie besondere Behandlung für Aufrufe von "+1 425 XXX XX XX" und "+1 206 XXX XX XX" als lokale oder am Standort Aufrufe nummerieren beibehalten wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-426">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="2b2e0-427">Die zurückgibt</span><span class="sxs-lookup"><span data-stu-id="2b2e0-427">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4.  <span data-ttu-id="2b2e0-428">Weisen Sie die VoIP-routing-Richtlinie für den Benutzer "John Woods" mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-428">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  <span data-ttu-id="2b2e0-429">Überprüfen Sie anschließend die Zuordnung mit dem Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-429">Then verify the assignment using the command:</span></span>   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  <span data-ttu-id="2b2e0-430">Die zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-430">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="2b2e0-431">Das Ergebnis ist, dass die VoIP-Richtlinie auf John Woods Anrufe angewendet werden nicht eingeschränkt, und die Logik des Routings ausgehender Anrufe für den Aufruf von USA, Kanada und International verfügbaren vor.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-431">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="enable-calling-for-microsoft-teams"></a><span data-ttu-id="2b2e0-432">Aktivieren Sie Anrufe für Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="2b2e0-432">Enable Calling for Microsoft Teams</span></span>

<span data-ttu-id="2b2e0-433">Bevor ein Benutzer auf die Registerkarte Anrufe in Microsoft-Teams, sehen kann, müssen Sie private Anrufe für den Mandanten in Microsoft-Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-433">Before a user can see the Calls tab in Microsoft Teams, you need to enable private calling for the tenant in Microsoft Teams.</span></span> <span data-ttu-id="2b2e0-434">Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-434">To do this:</span></span>

1.  <span data-ttu-id="2b2e0-435">Melden Sie sich als mandantenadministrator für das Office 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-435">Sign in as tenant administrator on the Office 365 Admin center.</span></span>
2.  <span data-ttu-id="2b2e0-436">Wechseln Sie zu **Einstellungen und Dienste und -add-ins** , und wählen Sie **Microsoft-Teams**.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-436">Go to **Settings and Services and add-ins** and select **Microsoft Teams**.</span></span> 
3.  <span data-ttu-id="2b2e0-437">Erweitern Sie **Anrufe und Besprechungen** , und überprüfen Sie, dass **Aufrufen von privaten zulassen** **aktiviert**ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-437">Expand **Calls and meetings** and verify that **Allow private calling** is **On**.</span></span>

    ![Screenshot des privaten aufrufen eingeschaltet zulassen.](../../media/ConfigDirectRouting-CallsandMeetingsDialog.png)

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-the-users"></a><span data-ttu-id="2b2e0-439">Festlegen Sie Microsoft-Teams für die Benutzer als bevorzugter Client aufrufende</span><span class="sxs-lookup"><span data-stu-id="2b2e0-439">Set Microsoft Teams as the preferred calling client for the users</span></span>

<span data-ttu-id="2b2e0-440">Direktes Routing leitet Anrufe nur für Microsoft-Teams, müssen Sie sicherstellen, dass Microsoft-Teams, die bevorzugte aufrufende Client für die Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-440">Direct Routing will route calls only to Microsoft Teams, so you need to make sure that Microsoft Teams is the preferred calling client for the users.</span></span> <span data-ttu-id="2b2e0-441">Dies wird durch die TeamsCallingPolicy und die TeamsInteropPolicy gesteuert.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-441">This is controlled by the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span> 

1. <span data-ttu-id="2b2e0-442">Verwenden Sie das folgende Cmdlet zuerst in einer PowerShell-Remotesitzung in der Skype für Business Online Administrationscenter, welche Richtlinien finden Sie unter der Benutzer zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-442">First, use the following cmdlet in a remote PowerShell session in the Skype for Business Online admin center to see which policies the user has been assigned.</span></span> 

  ```
  Get-CsOnlineUser -identity <User Name> | fl *teams*
  ```
 
2. <span data-ttu-id="2b2e0-443">Im nächsten Schritt überprüfen Sie die andere Richtlinieninstanzen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-443">Next, review the different policy instances.</span></span> 

  ```
  Get-CsTeamsCallingPolicy
  ``` 
<span data-ttu-id="2b2e0-444"> und </span><span class="sxs-lookup"><span data-stu-id="2b2e0-444">and</span></span>

  ```
  Get-CsTeamsInteropPolicy
  ``` 

<span data-ttu-id="2b2e0-445">Bevor Benutzer Microsoft-Teams, den Dienst verwenden können, sind zusätzliche Schritte, die Sie möglicherweise durchführen müssen, um die aufrufende Richtlinie anwenden und Anrufe zulassen.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-445">Before Microsoft Teams users can use the service, there are additional steps you may need to take to apply the calling policy and allow calls.</span></span>

### <a name="teams-calling-policy"></a><span data-ttu-id="2b2e0-446">Aufrufen der Richtlinie Teams</span><span class="sxs-lookup"><span data-stu-id="2b2e0-446">Teams Calling Policy</span></span>

<span data-ttu-id="2b2e0-447">Sie müssen sicherstellen, dass der Benutzer eine TeamsCallingPolicy mit AllowCalling = True.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-447">You need to make sure that the user has a TeamsCallingPolicy with AllowCalling = True.</span></span> <span data-ttu-id="2b2e0-448">Mit dieser Richtlinie kann die globale Richtlinie in Ihrem Mandanten oder eine bestimmte Richtlinie erteilt dem Benutzer sein.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-448">This policy can either be the Global policy in your tenant or a specific policy granted to the user.</span></span> <span data-ttu-id="2b2e0-449">Wenn Sie einem Benutzer eine bestimmte Richtlinie erteilt werden müssen, können Sie das Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-449">If you need to grant a user a specific policy, you can use the cmdlet:</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy> -Identity <User Name>
```

### <a name="teams-interop-policy"></a><span data-ttu-id="2b2e0-450">Teams Interop-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="2b2e0-450">Teams Interop Policy</span></span>

<span data-ttu-id="2b2e0-451">Stellen Sie sicher, dass der Benutzer den aufrufenden bevorzugten Client festzulegen, der Microsoft-Teams, verfügt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-451">Make sure that the user has the preferred calling client to set to Microsoft Teams.</span></span> <span data-ttu-id="2b2e0-452">Dies kann auf zwei Arten erfolgen:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-452">This can be done in two ways:</span></span>

- <span data-ttu-id="2b2e0-453">Der Benutzer festgelegt aufrufenden bevorzugten Client in der Microsoft-Teams, Client.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-453">The user sets the preferred calling client in the Microsoft Teams client.</span></span>
- <span data-ttu-id="2b2e0-454">Der Benutzer hat eine Richtlinie zugewiesen wurde, die aufrufenden bevorzugten Client festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-454">The user has been assigned a policy that sets the preferred calling client.</span></span>

<span data-ttu-id="2b2e0-455">Um eine Richtlinie zuweisen, die Microsoft-Teams, als bevorzugter Client aufrufende festlegt, stellen Sie sicher, dass der Benutzer eine Richtlinie mit CallingDefaultClient eingeholt wurde = Teams.</span><span class="sxs-lookup"><span data-stu-id="2b2e0-455">To assign a policy that sets Microsoft Teams as the preferred calling client, make sure that the user is granted a policy with CallingDefaultClient = Teams.</span></span> <span data-ttu-id="2b2e0-456">Nachfolgend sehen Sie ein Beispiel-Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2b2e0-456">An example cmdlet is shown below:</span></span>

```
Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity “<User Name>”
```

## <a name="see-also"></a><span data-ttu-id="2b2e0-457">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b2e0-457">See also</span></span>

[<span data-ttu-id="2b2e0-458">Planen der direkten Routing</span><span class="sxs-lookup"><span data-stu-id="2b2e0-458">Plan Direct Routing</span></span>](plan-direct-routing.md)
