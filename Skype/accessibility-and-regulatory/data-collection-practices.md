---
title: Data-Auflistung-Methoden
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: 
description: Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements.
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="f7125-104">Datensammlungsverfahren im Zusammenhang mit Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7125-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="f7125-105">Skype für Business Server 2015, Skype für Business Online, zusammen mit Skype für Geschäfts- und Microsoft-Teams, apps Sammeln von Daten zur Unterstützung von Microsoft zu verstehen, wie diese Produkte genutzt werden und welche Arten von Fehlern, z. B. Anmeldefehlern, aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="f7125-105">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="f7125-106">Anhand dieser Informationen können wir Nutzungsmuster verstehen, neue Funktionen planen, eine Problembehandlung durchführen und Problembereiche korrigieren.</span><span class="sxs-lookup"><span data-stu-id="f7125-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="f7125-p103">Einige Nutzungsdaten werden automatisch gesammelt, andere Daten können hingegen nur gesammelt werden, wenn der Administrator und/oder Nutzer dies zulässt. Die Datensammlung unterteilt sich in diese drei Kategorien:</span><span class="sxs-lookup"><span data-stu-id="f7125-p103">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="f7125-109">Statistische Daten zum Nutzer</span><span class="sxs-lookup"><span data-stu-id="f7125-109">Census data</span></span>
    
- <span data-ttu-id="f7125-110">Nutzungsdaten</span><span class="sxs-lookup"><span data-stu-id="f7125-110">Usage data</span></span>
    
- <span data-ttu-id="f7125-111">Fehlerberichtsdaten</span><span class="sxs-lookup"><span data-stu-id="f7125-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="f7125-112">Statistische Daten zum Nutzer</span><span class="sxs-lookup"><span data-stu-id="f7125-112">Census data</span></span>

<span data-ttu-id="f7125-113">Erhebung von Daten werden ausschließlich zum Bereitstellen, unterstützen und verbessern Skype für Unternehmen erworben.</span><span class="sxs-lookup"><span data-stu-id="f7125-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="f7125-114">Microsoft-Teams und Skype für Unternehmen Online.</span><span class="sxs-lookup"><span data-stu-id="f7125-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="f7125-115">Sie enthalten Umgebungsinformationen wie beispielsweise Gerät und Betriebssystemversion sowie regionale Einstellungen und Spracheinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f7125-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="f7125-116">Sie umfassen auch Zähler für erfolgreiche und fehlgeschlagene Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="f7125-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="f7125-117">Hier sehen Sie einige konkrete Beispiele für statistische Daten zu Benutzern, die gesammelt werden:</span><span class="sxs-lookup"><span data-stu-id="f7125-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="f7125-118">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f7125-118">**Data type**</span></span>|<span data-ttu-id="f7125-119">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f7125-119">**Example**</span></span>|<span data-ttu-id="f7125-120">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="f7125-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7125-121">AppName</span><span class="sxs-lookup"><span data-stu-id="f7125-121">AppName</span></span>  <br/> |<span data-ttu-id="f7125-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="f7125-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="f7125-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="f7125-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="f7125-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="f7125-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="f7125-125">Name des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="f7125-125">OSName</span></span>  <br/> |<span data-ttu-id="f7125-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="f7125-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="f7125-127">Version des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="f7125-127">OSVersion</span></span>  <br/> |<span data-ttu-id="f7125-128">8.3</span><span class="sxs-lookup"><span data-stu-id="f7125-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="f7125-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="f7125-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="f7125-130">DE-DE</span><span class="sxs-lookup"><span data-stu-id="f7125-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="f7125-131">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="f7125-131">UserID</span></span>  <br/> |<span data-ttu-id="f7125-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="f7125-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="f7125-p105">Für die ID wird zweimal ein Hash-Algorithmus verwendet: einmal im Client und einmal im Telemetriedienst. Der Hash-Algorithmus stellt sicher, dass die ID nicht mit einem bestimmten Nutzer verknüpft werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7125-p105">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="f7125-135">Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="f7125-135">DeviceID</span></span>  <br/> |<span data-ttu-id="f7125-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="f7125-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="f7125-137">Die Geräte-ID ist eine GUID, die nach dem Zufallsprinzip einmalig auf dem Gerät generiert und an den Telemetriedienst gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f7125-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="f7125-p106">Die statistischen Daten enthalten KEINE Informationen, anhand derer Ihre Organisation oder Ihre Benutzer identifiziert werden können. Weitere Informationen finden Sie unter [Datenschutzbestimmungen für Skype for Business](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7125-p106">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="f7125-140">Das Sammeln der statistischen Daten zum Nutzer ist standardmäßig aktiviert und kann von Administratoren oder Endbenutzern nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f7125-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="f7125-141">Nutzungsdaten</span><span class="sxs-lookup"><span data-stu-id="f7125-141">Usage data</span></span>

<span data-ttu-id="f7125-142">Zu den Nutzungsdaten zählen beispielsweise Informationen wie die Anzahl der getätigten Anrufe, die Anzahl der gesendeten oder empfangenen Chatnachrichten, die Anzahl der genutzten Telefonkonferenzen, die Nutzungshäufigkeit in Bezug auf verschiedene Features und Stabilitätsprobleme.</span><span class="sxs-lookup"><span data-stu-id="f7125-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="f7125-143">Nutzungsdaten enthalten unter Umständen Informationen, anhand derer Ihr Unternehmen identifiziert werden kann, beispielsweise contoso.com. Hier sehen Sie einige konkrete Beispiele für Nutzungsdaten, die gesammelt werden:</span><span class="sxs-lookup"><span data-stu-id="f7125-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="f7125-144">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f7125-144">**Data type**</span></span>|<span data-ttu-id="f7125-145">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f7125-145">**Example**</span></span>|<span data-ttu-id="f7125-146">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="f7125-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7125-147">Chatnachrichten gesendet</span><span class="sxs-lookup"><span data-stu-id="f7125-147">IM Sent</span></span>  <br/> |<span data-ttu-id="f7125-148">12</span><span class="sxs-lookup"><span data-stu-id="f7125-148">12</span></span>  <br/> ||
|<span data-ttu-id="f7125-149">Chatnachrichten erhalten</span><span class="sxs-lookup"><span data-stu-id="f7125-149">IM Received</span></span>  <br/> |<span data-ttu-id="f7125-150">5</span><span class="sxs-lookup"><span data-stu-id="f7125-150">5</span></span>  <br/> ||
|<span data-ttu-id="f7125-151">Besprechung beigetreten (Versuche)</span><span class="sxs-lookup"><span data-stu-id="f7125-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="f7125-152">5</span><span class="sxs-lookup"><span data-stu-id="f7125-152">5</span></span>  <br/> ||
|<span data-ttu-id="f7125-153">Besprechung beigetreten (erfolgreiche Versuche)</span><span class="sxs-lookup"><span data-stu-id="f7125-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="f7125-154">4</span><span class="sxs-lookup"><span data-stu-id="f7125-154">4</span></span>  <br/> ||
|<span data-ttu-id="f7125-155">Anruf-/Besprechungs-Minuten</span><span class="sxs-lookup"><span data-stu-id="f7125-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="f7125-156">30 Min.</span><span class="sxs-lookup"><span data-stu-id="f7125-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="f7125-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="f7125-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="f7125-158">Microsoft.com (engl.)</span><span class="sxs-lookup"><span data-stu-id="f7125-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="f7125-159">Dies ist der Name des Unternehmens, das in Office 365 registriert ist. Er wird in Klartext übertragen, also nicht verschleiert.</span><span class="sxs-lookup"><span data-stu-id="f7125-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="f7125-160">Die Nutzungsdaten enthalten KEINE Informationen, anhand derer Nutzer identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="f7125-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="f7125-p107">Die Sammlung der Nutzungsdaten ist standardmäßig aktiviert, lokale Administratoren können sie jedoch mit der Gruppenrichtlinieneinstellung „Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren" (DisableAutomaticSendTracing) für Skype for Business Server 2015 deaktivieren. Das Deaktivieren dieser Einstellung wirkt sich auf alle Benutzer in der Organisation aus. Unter [Konfigurieren von Richtlinien für das Client-Bootstrapping in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f7125-p107">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015. Turning this setting off affects all users in the organization. See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="f7125-164">Benutzer können die Sammlung der Nutzungsdaten nicht aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7125-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="f7125-165">Die Telemetrie für die Webseiten der Skype-Besprechungs-App und von Join Launcher kann durch diese Richtlinie gesteuert werden:</span><span class="sxs-lookup"><span data-stu-id="f7125-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="f7125-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="f7125-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="f7125-p108">Diese Richtlinie ist standardmäßig auf „False" festgelegt, das heißt, die Telemetriesammlung ist standardmäßig deaktiviert. Diese Einstellung gilt pro Pool und für alle Benutzer, die über die Skype-Besprechungs-App eine Verbindung mit einer Besprechung herstellen, die auf dem jeweiligen Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f7125-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="f7125-169">Fehlerberichtsdaten</span><span class="sxs-lookup"><span data-stu-id="f7125-169">Error reporting data</span></span>

<span data-ttu-id="f7125-p109">Zu den Fehlerberichtsdaten zählen Informationen über Leistung und Zuverlässigkeit, Gerätekonfiguration, Netzwerk-Verbindungsqualität, Fehlercodes, Fehlerprotokolle und Ausnahmen. Hier sehen Sie einige konkrete Beispiele für Fehlerberichtsdaten, die gesammelt werden:</span><span class="sxs-lookup"><span data-stu-id="f7125-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="f7125-172">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f7125-172">**Data type**</span></span>|<span data-ttu-id="f7125-173">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f7125-173">**Example**</span></span>|<span data-ttu-id="f7125-174">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="f7125-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7125-175">Nachrichtenrichtung</span><span class="sxs-lookup"><span data-stu-id="f7125-175">Message direction</span></span>  <br/> |<span data-ttu-id="f7125-176">Eingehend</span><span class="sxs-lookup"><span data-stu-id="f7125-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="f7125-177">Unterhaltungsstatus</span><span class="sxs-lookup"><span data-stu-id="f7125-177">Conversation state</span></span>  <br/> |<span data-ttu-id="f7125-178">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="f7125-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="f7125-179">Unterhaltungs-Thread-ID</span><span class="sxs-lookup"><span data-stu-id="f7125-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="f7125-180">AdDO8hsJqilU93hQHC3OZaPR2saEA ==</span><span class="sxs-lookup"><span data-stu-id="f7125-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="f7125-181">Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="f7125-181">UserID</span></span>  <br/> |<span data-ttu-id="f7125-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="f7125-182">amosmarble</span></span> <br/> |<span data-ttu-id="f7125-183">Die ID wird im Klartext übertragen, auf den der Telemetriedienst vor dem Speichern einen Hash-Algorithmus anwendet</span><span class="sxs-lookup"><span data-stu-id="f7125-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="f7125-p110">Die Fehlerberichterstattungsdaten können außerdem personenbezogene Informationen enthalten, beispielsweise die IP-Adresse des Benutzers und den SIP-URI (Session Initiation Protocol Uniform Resource Identifier). Unter [Datenschutzbestimmungen für Skype for Business](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) wird ausführlich erklärt, welche Daten gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="f7125-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="f7125-186">Für die Fehlerberichterstattung müssen zwei Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="f7125-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="f7125-p111">Die DisableAutomaticSendTracing-Gruppenrichtlinieneinstellung muss auf dem Server oder im Mandanten-Admin Center auf False festgelegt sein (das ist der Standardzustand). Unter [Konfigurieren von Richtlinien für das Client-Bootstrapping in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f7125-p111">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state). See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="f7125-189">Benutzer erteilen die Erlaubnis über die Registerkarte „Allgemein" (durch Klicken auf das Zahnradsymbol wird das Dialogfeld „Optionen" geöffnet, in dem die Registerkarte „Allgemein" angezeigt wird) im Skype for Business-Client.</span><span class="sxs-lookup"><span data-stu-id="f7125-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![Zahnradsymbol](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="f7125-p112">Für die Skype-Besprechungs-App steuert „MeetingUxEnableTelemetry" außerdem die Fehlerberichterstattung, obwohl für Abstürze unter Windows die Watson-Einstellungen das Hochladen von Absturzinformationen steuern. Es gibt für die Skype-Besprechungs-App keine Benutzereinstellung wie im Dialogfeld des Desktopclients.</span><span class="sxs-lookup"><span data-stu-id="f7125-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="f7125-194">Weitere Informationen finden Sie unter [Festlegen von allgemeinen Optionen in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).</span><span class="sxs-lookup"><span data-stu-id="f7125-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="f7125-195">Informationen zur Einrichtung Ihres Netzwerks finden Sie unter [Einrichten Ihres Netzwerks für Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).</span><span class="sxs-lookup"><span data-stu-id="f7125-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="f7125-196">Wenn Sie Office 365 über 21Vianet in China nutzen, finden Sie weiterführende Informationen unter [Set up your network for Lync Online](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="f7125-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f7125-197">See Also</span><span class="sxs-lookup"><span data-stu-id="f7125-197">Related topics</span></span>
[<span data-ttu-id="f7125-198">Programm zur Verbesserung der Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="f7125-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="f7125-199">Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="f7125-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
