---
title: Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für Skype für Business Server 2015 Stress and Performance-Tool.
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881207"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e2e57-103">Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="e2e57-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e2e57-104">Richtlinienkonfiguration für Skype für Business Server 2015 Stress and Performance-Tool.</span><span class="sxs-lookup"><span data-stu-id="e2e57-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="e2e57-105">Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype für Business Server 2015 konfigurieren können, vor dem Ausführen der Stress and Performance-Tool:</span><span class="sxs-lookup"><span data-stu-id="e2e57-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="e2e57-106">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="e2e57-107">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="e2e57-108">Kontakte-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="e2e57-109">Richtlinie für den Verbund</span><span class="sxs-lookup"><span data-stu-id="e2e57-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="e2e57-110">Call Admission Control-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="e2e57-111">VoIP-Routing-Regeln</span><span class="sxs-lookup"><span data-stu-id="e2e57-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="e2e57-112">Die Anwendung Konferenzzentrale Konferenz</span><span class="sxs-lookup"><span data-stu-id="e2e57-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="e2e57-113">Dienst zum Parken Server</span><span class="sxs-lookup"><span data-stu-id="e2e57-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="e2e57-114">Notrufe</span><span class="sxs-lookup"><span data-stu-id="e2e57-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="e2e57-115">Konfigurieren der reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="e2e57-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="e2e57-116">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-116">Archiving policy</span></span>
<span data-ttu-id="e2e57-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-117"></span></span>

<span data-ttu-id="e2e57-118">Wenn Sie einen Archivierungsserver in Ihrer Skype für Business Server-Topologie bereitgestellt haben, können Sie das Skript ArchivingPolicy.ps1 anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="e2e57-119">Wenn Sie weitere Hilfe benötigen, checken Sie die Cmdlets für Archivierung und Webkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="e2e57-120">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-120">Conferencing policy</span></span>
<span data-ttu-id="e2e57-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-121"></span></span>

<span data-ttu-id="e2e57-122">Für Konferenzen haben wir das Skript MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="e2e57-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="e2e57-123">Wenn Sie weitere Hilfe benötigen, checken Sie die Cmdlets für Webkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="e2e57-124">Kontakte-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-124">Contacts policy</span></span>
<span data-ttu-id="e2e57-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-125"></span></span>

<span data-ttu-id="e2e57-126">ContactsPolicy.ps1 Skript wird im Beispiel sein, die, das Sie benötigen, um zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="e2e57-127">Die Cmdlets für Instant Messaging und Anwesenheit ist hilfreich, wenn Sie weitere Verweise benötigen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="e2e57-128">Richtlinie für den Verbund</span><span class="sxs-lookup"><span data-stu-id="e2e57-128">Federation policy</span></span>
<span data-ttu-id="e2e57-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-129"></span></span>

<span data-ttu-id="e2e57-130">Das Beispielskript für den Verbund ist FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="e2e57-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="e2e57-131">Die Cmdlets zu überprüfen, wenn Sie weitere Erkenntnisse, benötigen, werden die Edge-Server, Partnerverbund und externer Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e2e57-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="e2e57-132">Call Admission Control-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e2e57-132">Call Admission Control policy</span></span>
<span data-ttu-id="e2e57-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-133"></span></span>

<span data-ttu-id="e2e57-134">Sie können für diese Richtlinie auf BandwidthPolicy.ps1 verweisen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="e2e57-135">Call Admission Control-Cmdlets werden weitere Informationen sowie haben.</span><span class="sxs-lookup"><span data-stu-id="e2e57-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="e2e57-136">VoIP-Routing-Regeln</span><span class="sxs-lookup"><span data-stu-id="e2e57-136">Voice Routing rules</span></span>
<span data-ttu-id="e2e57-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-137"></span></span>

<span data-ttu-id="e2e57-138">Sie benötigen das RoutingRules.ps1 Beispielskript für VoIP-Routing.</span><span class="sxs-lookup"><span data-stu-id="e2e57-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="e2e57-139">Wenn Sie diese Regeln konfigurieren, notieren Sie den Kontext (d. h., /Location Profil oder /SimpleName), Telefon und interner/externer Vorwahlen, damit Sie sie beim Erstellen von Benutzern angeben können.</span><span class="sxs-lookup"><span data-stu-id="e2e57-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="e2e57-140">Sie benötigen auch während der Konfiguration (speziell für PSTN-UC und UC-zu-PSTN) LyncPerfTool eingetragenen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="e2e57-141">Beispielsweise sollte der SimpleName-Parameter im Aufruf an das Cmdlet **New-CsDialPlan** im Beispiel RoutingRules.ps1 für den LocationProfile-Wert in der folgenden Abbildung der UserProfileGenerator.exe verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e2e57-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business-Lastkonfigurationstool, Registerkarte für VoIP-Szenarien, Erweiterte Einstellungen für Unterhaltungen](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="e2e57-143">Weitere Informationen hierzu können Sie die Enterprise-VoIP-Cmdlets überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="e2e57-144">Die Anwendung Konferenzzentrale Konferenz</span><span class="sxs-lookup"><span data-stu-id="e2e57-144">Conference Attendant application</span></span>
<span data-ttu-id="e2e57-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-145"></span></span>

<span data-ttu-id="e2e57-146">Überprüfen Sie zuerst das ConferenceAutoAttendantConfiguration.ps1 Skript.</span><span class="sxs-lookup"><span data-stu-id="e2e57-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="e2e57-147">Sie sollten eine Notiz der Rufnummer ConferencingAutoAttendant (standardmäßig 1121111111), sodass Sie ihn in das Konfigurationstool für LyncPerfTool für Konfiguration Generation wie unten eingeben können:</span><span class="sxs-lookup"><span data-stu-id="e2e57-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Die Registerkarte für VoIP-Szenarien zeigt die Stufe der Konferenzauslastung und die Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="e2e57-149">Weitere Informationen finden Sie in den Konferenzen und Einwahlkonferenzen Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e2e57-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="e2e57-150">Dienst zum Parken Server</span><span class="sxs-lookup"><span data-stu-id="e2e57-150">Server Call Park service</span></span>
<span data-ttu-id="e2e57-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-151"></span></span>

<span data-ttu-id="e2e57-152">Dies ist tatsächlich standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e2e57-152">This is actually disabled by default.</span></span> <span data-ttu-id="e2e57-153">Sie können das Beispielskript CallParkConfiguration.ps1 ansehen, wenn Sie benötigen, um dies zu testen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="e2e57-154">Darüber hinaus checken Sie die Cmdlets Call Park Anwendung wie gewünscht.</span><span class="sxs-lookup"><span data-stu-id="e2e57-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="e2e57-155">Notrufe</span><span class="sxs-lookup"><span data-stu-id="e2e57-155">Emergency calls</span></span>
<span data-ttu-id="e2e57-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-156"></span></span>

<span data-ttu-id="e2e57-157">Sie müssen die folgenden Schritte zum Konfigurieren von belastungs- und Leistungstests für Notrufe durchführen:</span><span class="sxs-lookup"><span data-stu-id="e2e57-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="e2e57-158">Richten Sie eine VoIP-Route für Notrufe.</span><span class="sxs-lookup"><span data-stu-id="e2e57-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="e2e57-159">Sie können verwenden Sie das Skript RoutingRules.ps1 und prüfen Sie unter den Kommentar " **Route E911 mit PSTN** " für ein Beispiel dafür, wie diese VoIP-Route einrichten.</span><span class="sxs-lookup"><span data-stu-id="e2e57-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e2e57-160">Der Befehl im Beispiel in RoutingRules.ps1 hat ein Muster, die die Anzahl 119 statt 911 enthält.</span><span class="sxs-lookup"><span data-stu-id="e2e57-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="e2e57-161">Sie sollten vermeiden der Verwendung von 911 (oder Ihre aktuelle lokale Notrufnummer), um versehentliche Anrufe an Ihre lokalen Notfällen Operatoren während die Auslastungstests zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e2e57-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="e2e57-162">Beachten Sie, dass diese Konfiguration nur aus Gründen der Simulation ist!</span><span class="sxs-lookup"><span data-stu-id="e2e57-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="e2e57-163">Konfigurieren Sie Adressen durch die Werte auf der Registerkarte **Info-Dienstkonfiguration Speicherort** in der UserProvisioningTool ausfüllen, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e2e57-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Das Benutzerbereitstellungstool zeigt die Anzahl der Adressen, Subnetze, Switche und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="e2e57-165">Wenn Sie alles in der UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche **LIS-Config-Dateien zu generieren** .</span><span class="sxs-lookup"><span data-stu-id="e2e57-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="e2e57-166">Nun wird CSV-Dateien für Ports, Subnetze, Switches und drahtlose Zugriffspunkte (drahtlose Zugriffspunkte) als auch eine XML-Datei für den Stress and Performance-Tool generiert.</span><span class="sxs-lookup"><span data-stu-id="e2e57-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="e2e57-167">Die CSV-Dateien können für Eingaben beim Konfigurieren des Standortinformationen-Diensts (LIS) mit dem Skript LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="e2e57-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="e2e57-168">Zu diesem Zweck müssen Sie die Datei Locations0.xml in demselben Ordner wie die Stress and Performance-Tool ausführbare (LyncPerfTool.exe) verschieben.</span><span class="sxs-lookup"><span data-stu-id="e2e57-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="e2e57-169">Dadurch können Sie den Speicherort Profil (Wählplan) Szenarios auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="e2e57-170">Konfigurieren der reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="e2e57-170">Configuring Response Group application</span></span>
<span data-ttu-id="e2e57-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="e2e57-171"></span></span>

<span data-ttu-id="e2e57-172">Das Beispielskript ist ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="e2e57-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="e2e57-173">Es gibt auch Cmdlets für die Reaktionsgruppenanwendung Weitere Einzelheiten zur Konfiguration überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e2e57-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="e2e57-174">Das folgende Diagramm zeigt einige der Konfigurationsdetails an:</span><span class="sxs-lookup"><span data-stu-id="e2e57-174">The following diagram will show some of the configuration details:</span></span>
  
![Das Konfigurationstool für Reaktionsgruppen zeigt vorhandene Workflows für Testzwecke.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

