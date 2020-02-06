---
title: Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Zusammenfassung: Konfigurieren Sie die VTC-Geräte so, dass Sie mit Skype for Business Server funktionieren.'
ms.openlocfilehash: b266c8cc97898fe192ec023183a565b921d86949
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798082"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="6c04f-103">Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6c04f-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="6c04f-104">**Zusammenfassung:** Konfigurieren Sie die VTC-Geräte für die Zusammenarbeit mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c04f-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="6c04f-105">Sie müssen die folgenden Konfigurations Anpassungsverfahren für jede VTC durchführen, die mit dem Skype for Business-VIS-Server über einen SIP-Trunk und einen Cisco Unified Communications Manager (CallManager oder CUCM)-Video Gateway verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="6c04f-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="6c04f-106">Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Arbeit mit einem VIS konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6c04f-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="6c04f-107">Andere Einstellungen und/oder Verwendungsmöglichkeiten von alternativen CUCM-Funktionen können auch zum Erzielen des gleichen Ergebnisses herangezogen werden.</span><span class="sxs-lookup"><span data-stu-id="6c04f-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="6c04f-108">Es wird keine Empfehlung für die optimale Konfiguration eines bestimmten Szenarios impliziert.</span><span class="sxs-lookup"><span data-stu-id="6c04f-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="6c04f-109">Konfigurieren einer beim CUCM registrierten Videotelekonferenz</span><span class="sxs-lookup"><span data-stu-id="6c04f-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="6c04f-110">Melden Sie sich beim Cisco VTC-Gerät an, und navigieren\>Sie zu Konfiguration\>– System Konfiguration – Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6c04f-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="6c04f-111">Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6c04f-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="6c04f-112">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-112">**Parameter**</span></span>|<span data-ttu-id="6c04f-113">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6c04f-114">Bereitstellungsmodus</span><span class="sxs-lookup"><span data-stu-id="6c04f-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="6c04f-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="6c04f-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="6c04f-116">ExternalManager-Adresse</span><span class="sxs-lookup"><span data-stu-id="6c04f-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="6c04f-117">Vollqualifizierter Domänenname des CUCM</span><span class="sxs-lookup"><span data-stu-id="6c04f-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="6c04f-118">Externalmanager-Domäne</span><span class="sxs-lookup"><span data-stu-id="6c04f-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="6c04f-119">CUCM-Domäne</span><span class="sxs-lookup"><span data-stu-id="6c04f-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="6c04f-120">Navigieren Sie zu Konfiguration\>– System Konfiguration\>– Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="6c04f-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="6c04f-121">Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6c04f-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="6c04f-122">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-122">**Parameter**</span></span>|<span data-ttu-id="6c04f-123">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6c04f-124">DNS-Domänenname</span><span class="sxs-lookup"><span data-stu-id="6c04f-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="6c04f-125">CUCM-Domänenname</span><span class="sxs-lookup"><span data-stu-id="6c04f-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="6c04f-126">DNS-Serveradresse 1</span><span class="sxs-lookup"><span data-stu-id="6c04f-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="6c04f-127">Die Adresse Ihres gewünschten DNS-Servers</span><span class="sxs-lookup"><span data-stu-id="6c04f-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="6c04f-128">Navigieren Sie zu Konfiguration\>– System Konfiguration\>– Netzwerkdienste.</span><span class="sxs-lookup"><span data-stu-id="6c04f-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="6c04f-129">Stellen Sie sicher, dass der H.323-Modus deaktiviert und der SIP-Modus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6c04f-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="6c04f-p103">Diese Optionen werden automatisch eingestellt, wenn der Endpunkt beim CUCM registriert wird. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6c04f-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="6c04f-132">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-132">**Parameter**</span></span>|<span data-ttu-id="6c04f-133">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6c04f-134">H.323-Modus</span><span class="sxs-lookup"><span data-stu-id="6c04f-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="6c04f-135">Aus</span><span class="sxs-lookup"><span data-stu-id="6c04f-135">Off</span></span> <br/> |
   |<span data-ttu-id="6c04f-136">HTTP-Modus</span><span class="sxs-lookup"><span data-stu-id="6c04f-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="6c04f-137">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-137">On</span></span> <br/> |
   | <span data-ttu-id="6c04f-138">SIP-Modus</span><span class="sxs-lookup"><span data-stu-id="6c04f-138">SIP Mode</span></span> <br/> | <span data-ttu-id="6c04f-139">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-139">On</span></span> <br/> |
   |<span data-ttu-id="6c04f-140">Telnet-Modus</span><span class="sxs-lookup"><span data-stu-id="6c04f-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="6c04f-141">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-141">On</span></span> <br/> |
   |<span data-ttu-id="6c04f-142">Begrüßungstext</span><span class="sxs-lookup"><span data-stu-id="6c04f-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="6c04f-143">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-143">On</span></span> <br/> |
   |<span data-ttu-id="6c04f-144">XMLAPI-Modus</span><span class="sxs-lookup"><span data-stu-id="6c04f-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="6c04f-145">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-145">On</span></span> <br/> |
   
7. <span data-ttu-id="6c04f-146">Navigieren Sie zu Konfiguration\>– System Konfiguration\>– SIP.</span><span class="sxs-lookup"><span data-stu-id="6c04f-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="6c04f-147">Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6c04f-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="6c04f-148">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-148">**Parameter**</span></span>|<span data-ttu-id="6c04f-149">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6c04f-150">Profil 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="6c04f-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="6c04f-151">TCP</span><span class="sxs-lookup"><span data-stu-id="6c04f-151">TCP</span></span> <br/> |
   |<span data-ttu-id="6c04f-152">Profil 1 - Ausgehend</span><span class="sxs-lookup"><span data-stu-id="6c04f-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="6c04f-153">Aus</span><span class="sxs-lookup"><span data-stu-id="6c04f-153">Off</span></span> <br/> |
   |<span data-ttu-id="6c04f-154">Profil 1 – TlsVerify</span><span class="sxs-lookup"><span data-stu-id="6c04f-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="6c04f-155">Ein</span><span class="sxs-lookup"><span data-stu-id="6c04f-155">On</span></span> <br/> |
   |<span data-ttu-id="6c04f-156">Profil 1 - Typ</span><span class="sxs-lookup"><span data-stu-id="6c04f-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="6c04f-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="6c04f-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="6c04f-158">Profil 1 - URI</span><span class="sxs-lookup"><span data-stu-id="6c04f-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="6c04f-159">Bei CUCM-Registrierung automatisch zugewiesen</span><span class="sxs-lookup"><span data-stu-id="6c04f-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="6c04f-160">Proxy 1 - Adresse</span><span class="sxs-lookup"><span data-stu-id="6c04f-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="6c04f-161">Der Hostname des CUCM</span><span class="sxs-lookup"><span data-stu-id="6c04f-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="6c04f-p104">Die Videotelekonferenz ist jetzt für Interoperabilität konfiguriert. Bevor der Dienst gestartet werden kann, müssen CUCM-seitig abschließende Schritte durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6c04f-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="6c04f-164">Konfigurieren Sie Videotelekonferenzgeräte im CUCM</span><span class="sxs-lookup"><span data-stu-id="6c04f-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="6c04f-165">Melden Sie sich bei CUCM an, und navigieren Sie zu Cisco\>Unified cm\>Administration-\>Device-Phone-Find.</span><span class="sxs-lookup"><span data-stu-id="6c04f-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="6c04f-p105">Wählen Sie das Videotelekonferenzgerät, das konfiguriert werden soll. Überprüfen Sie die folgenden Einstellungen im Bildschirm „Telefonkonfiguration“ und führen Sie ggf. Korrekturen durch. Klicken Sie auf **Save** (Speichern), nachdem diese Einstellungen geändert oder überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="6c04f-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="6c04f-169">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-169">**Parameter**</span></span>|<span data-ttu-id="6c04f-170">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6c04f-171">Geräteinformation - Telefontastenvorlage</span><span class="sxs-lookup"><span data-stu-id="6c04f-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="6c04f-172">Standard-Cisco TelePresence-Codec C40</span><span class="sxs-lookup"><span data-stu-id="6c04f-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="6c04f-173">Geräteinformation - Allgemeines Telefonprofil</span><span class="sxs-lookup"><span data-stu-id="6c04f-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="6c04f-174">Standardmäßiges allgemeines Telefonprofil</span><span class="sxs-lookup"><span data-stu-id="6c04f-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="6c04f-175">Geräteinformation - Wahlberechtigungsmodul</span><span class="sxs-lookup"><span data-stu-id="6c04f-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-177">Geräteinformation - AAR-Wahlberechtigungsmodul</span><span class="sxs-lookup"><span data-stu-id="6c04f-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-179">Geräteinformation - Medienressourcen-Gruppenliste</span><span class="sxs-lookup"><span data-stu-id="6c04f-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="6c04f-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-181">Protokollspezifische Information - Gerätesicherheitsprofil</span><span class="sxs-lookup"><span data-stu-id="6c04f-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="6c04f-182">Cisco TelePresence-Codec C40</span><span class="sxs-lookup"><span data-stu-id="6c04f-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="6c04f-183">Protokollspezifische Information - Umleitungs-Wahlberechtigungsmodul</span><span class="sxs-lookup"><span data-stu-id="6c04f-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-185">Protokollspezifische Informationen-abonnieren des Suchbereichs für Anrufe</span><span class="sxs-lookup"><span data-stu-id="6c04f-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-187">Protokollspezifische Information - SIP-Profil</span><span class="sxs-lookup"><span data-stu-id="6c04f-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="6c04f-188">Standardmäßiges SIP-Profil für Telepräsenzendpunkt</span><span class="sxs-lookup"><span data-stu-id="6c04f-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="6c04f-189">Wenn die VTC-Konfiguration gespeichert ist, navigieren Sie erneut zum Bildschirm „Telefonkonfiguration“ für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="6c04f-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="6c04f-190">Klicken Sie oben im Bildschirm in der Gruppe „Zuordnung“ auf die Zuordnung für die Videointeroperabilität.</span><span class="sxs-lookup"><span data-stu-id="6c04f-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="6c04f-191">Damit öffnen Sie den Bildschirm „Verzeichnisnummernkonfiguration“.</span><span class="sxs-lookup"><span data-stu-id="6c04f-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="6c04f-192">Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6c04f-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="6c04f-193">Nehmen Sie die entsprechenden Änderungen vor wie in der Verzeichnisnummerninformation und den Verzeichnisnummerneinstellungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c04f-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="6c04f-194">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6c04f-194">**Parameter**</span></span>|<span data-ttu-id="6c04f-195">**Empfohlene Einstellung**</span><span class="sxs-lookup"><span data-stu-id="6c04f-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="6c04f-196">Verzeichnisnummerninformation - Routenpartition</span><span class="sxs-lookup"><span data-stu-id="6c04f-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="6c04f-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="6c04f-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="6c04f-198">Verzeichnisnummerneinstellungen - Leerzeichen für Anrufsuche</span><span class="sxs-lookup"><span data-stu-id="6c04f-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-200">MLPP-Einstellungen für neuen Gesprächspartner und vertrauliche Zugriffsebene - MLPP-Wahlberechtigungsmodul</span><span class="sxs-lookup"><span data-stu-id="6c04f-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="6c04f-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="6c04f-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="6c04f-202">Zeile 1 auf Device-Display (Rufnummernanzeige)</span><span class="sxs-lookup"><span data-stu-id="6c04f-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="6c04f-203">Nach Bedarf</span><span class="sxs-lookup"><span data-stu-id="6c04f-203">As desired</span></span> <br/> |
   |<span data-ttu-id="6c04f-204">Zeile 1 auf Device-ASCII-Display (Rufnummernanzeige)</span><span class="sxs-lookup"><span data-stu-id="6c04f-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="6c04f-205">Nach Bedarf</span><span class="sxs-lookup"><span data-stu-id="6c04f-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="6c04f-206">Scrollen Sie nach Beendigung im Bildschirm nach oben und drücken Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6c04f-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="6c04f-p107">Die Konfiguration für dieses Videotelekonferenzgerät ist damit beendet. Sie müssen diesen Vorgang ggf. für andere Videotelekonferenzgeräte in Ihrem Unternehmen wiederholen.</span><span class="sxs-lookup"><span data-stu-id="6c04f-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

