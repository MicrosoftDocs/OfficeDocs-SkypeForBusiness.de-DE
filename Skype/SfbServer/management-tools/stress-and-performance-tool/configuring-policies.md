---
title: Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für das Stress-und Leistungs Tool von Skype for Business Server 2015
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299751"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="71828-103">Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="71828-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="71828-104">Richtlinienkonfiguration für das Stress-und Leistungs Tool von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="71828-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="71828-105">Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype for Business Server 2015 konfigurieren können, bevor Sie das Belastungs-und Leistungs Tool ausführen:</span><span class="sxs-lookup"><span data-stu-id="71828-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="71828-106">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="71828-107">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="71828-108">Kontakt Richtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="71828-109">Föderations Richtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="71828-110">Richtlinien für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="71828-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="71828-111">VoIP-Weiterleitungsregeln</span><span class="sxs-lookup"><span data-stu-id="71828-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="71828-112">Anwendung für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="71828-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="71828-113">Server-Anruf Park Service</span><span class="sxs-lookup"><span data-stu-id="71828-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="71828-114">Notrufe</span><span class="sxs-lookup"><span data-stu-id="71828-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="71828-115">Konfigurieren der Antwortgruppen Anwendung</span><span class="sxs-lookup"><span data-stu-id="71828-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="71828-116">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-116">Archiving policy</span></span>
<span data-ttu-id="71828-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-117"></span></span>

<span data-ttu-id="71828-118">Wenn Sie einen Archivierungsserver in Ihrer Skype for Business Server-Topologie bereitgestellt haben, können Sie das ArchivingPolicy. ps1-Skript sehen.</span><span class="sxs-lookup"><span data-stu-id="71828-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="71828-119">Wenn Sie weitere Hilfe benötigen, lesen Sie die Cmdlets Archivierungs-und Webkonferenz.</span><span class="sxs-lookup"><span data-stu-id="71828-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="71828-120">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-120">Conferencing policy</span></span>
<span data-ttu-id="71828-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-121"></span></span>

<span data-ttu-id="71828-122">Für Konferenzen haben wir das MeetingPolicy. ps1-Skript.</span><span class="sxs-lookup"><span data-stu-id="71828-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="71828-123">Wenn Sie weitere Hilfe benötigen, lesen Sie die Webkonferenz-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="71828-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="71828-124">Kontakt Richtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-124">Contacts policy</span></span>
<span data-ttu-id="71828-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-125"></span></span>

<span data-ttu-id="71828-126">Das ContactsPolicy. ps1-Skript ist das Beispiel, das Sie überprüfen müssen.</span><span class="sxs-lookup"><span data-stu-id="71828-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="71828-127">Die Cmdlets für Sofortnachrichten und Anwesenheitsinformationen sind hilfreich, wenn Sie Weitere Verweise benötigen.</span><span class="sxs-lookup"><span data-stu-id="71828-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="71828-128">Föderations Richtlinie</span><span class="sxs-lookup"><span data-stu-id="71828-128">Federation policy</span></span>
<span data-ttu-id="71828-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-129"></span></span>

<span data-ttu-id="71828-130">Das Beispielskript für Federation lautet FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="71828-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="71828-131">Die zu überprüfenden Cmdlets, wenn Sie weitere Einblicke benötigen, sind Edgeserver, Federation und externer Zugriff.</span><span class="sxs-lookup"><span data-stu-id="71828-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="71828-132">Richtlinien für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="71828-132">Call Admission Control policy</span></span>
<span data-ttu-id="71828-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-133"></span></span>

<span data-ttu-id="71828-134">Sie können auf BandwidthPolicy. ps1 für diese Richtlinie verweisen.</span><span class="sxs-lookup"><span data-stu-id="71828-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="71828-135">Weitere Informationen finden Sie auch in den Cmdlets für die Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="71828-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="71828-136">VoIP-Weiterleitungsregeln</span><span class="sxs-lookup"><span data-stu-id="71828-136">Voice Routing rules</span></span>
<span data-ttu-id="71828-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-137"></span></span>

<span data-ttu-id="71828-138">Sie benötigen das RoutingRules. ps1-Beispielskript für das VoIP-Routing.</span><span class="sxs-lookup"><span data-stu-id="71828-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="71828-139">Wenn Sie diese Regeln konfigurieren, notieren Sie sich den Telefonkontext (also/Location-Profil oder/SimpleName) sowie interne/externe Ortsvorwahl, damit Sie diese beim Erstellen von Benutzern angeben können.</span><span class="sxs-lookup"><span data-stu-id="71828-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="71828-140">Sie benötigen Sie auch während der LyncPerfTool-Konfiguration (insbesondere für PSTN-UC und UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="71828-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="71828-141">Beispielsweise sollte der Parameter SimpleName im Aufruf des Cmdlets **New-CsDialPlan** im RoutingRules. ps1-Beispiel für den LocationProfile-Wert in der folgenden Abbildung von UserProfileGenerator. exe verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="71828-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business-Lastkonfigurationstool, Registerkarte für VoIP-Szenarien, Erweiterte Einstellungen für Unterhaltungen](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="71828-143">Ausführliche Informationen finden Sie unter Enterprise-VoIP-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="71828-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="71828-144">Anwendung für Konferenzteilnehmer</span><span class="sxs-lookup"><span data-stu-id="71828-144">Conference Attendant application</span></span>
<span data-ttu-id="71828-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-145"></span></span>

<span data-ttu-id="71828-146">Überprüfen Sie zuerst das ConferenceAutoAttendantConfiguration. ps1-Skript.</span><span class="sxs-lookup"><span data-stu-id="71828-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="71828-147">Sie sollten die ConferencingAutoAttendant-Telefonnummer (standardmäßig 1121111111) notieren, damit Sie diese in das LyncPerfTool-Konfigurationstool für die Konfigurations Generierung eingeben können, wie unten beschrieben:</span><span class="sxs-lookup"><span data-stu-id="71828-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Die Registerkarte für VoIP-Szenarien zeigt die Stufe der Konferenzauslastung und die Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="71828-149">Weitere Details finden Sie unter Konferenz-und Einwahlkonferenz-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="71828-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="71828-150">Server-Anruf Park Service</span><span class="sxs-lookup"><span data-stu-id="71828-150">Server Call Park service</span></span>
<span data-ttu-id="71828-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-151"></span></span>

<span data-ttu-id="71828-152">Dies ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="71828-152">This is actually disabled by default.</span></span> <span data-ttu-id="71828-153">Sie können das CallParkConfiguration. ps1-Beispielskript überprüfen, wenn Sie dies testen möchten.</span><span class="sxs-lookup"><span data-stu-id="71828-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="71828-154">Darüber hinaus können Sie die Cmdlets für die Parken-Anwendung nach Bedarf abrufen.</span><span class="sxs-lookup"><span data-stu-id="71828-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="71828-155">Notrufe</span><span class="sxs-lookup"><span data-stu-id="71828-155">Emergency calls</span></span>
<span data-ttu-id="71828-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-156"></span></span>

<span data-ttu-id="71828-157">Sie müssen die folgenden Schritte ausführen, um die Belastungs-und Leistungstests für Notrufe zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="71828-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="71828-158">Einrichten einer VoIP-Route für Notrufe.</span><span class="sxs-lookup"><span data-stu-id="71828-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="71828-159">Sie können das RoutingRules. ps1-Skript verwenden und unter dem Kommentar " **Route E911 to PSTN** " ein Beispiel für die Einrichtung dieser VoIP-Route finden.</span><span class="sxs-lookup"><span data-stu-id="71828-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="71828-160">Der Beispielbefehl in RoutingRules. ps1 weist ein Zahlenmuster auf, das die Zahl 119 anstatt 911 enthält.</span><span class="sxs-lookup"><span data-stu-id="71828-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="71828-161">Sie sollten die Verwendung von 911 (oder ihrer tatsächlichen lokalen Notfallnummer) vermeiden, um versehentliche Anrufe an Ihre lokalen Notfall Operatoren während der Auslastungstests zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="71828-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="71828-162">Beachten Sie, dass diese Konfiguration nur zu Simulationszwecken dient!</span><span class="sxs-lookup"><span data-stu-id="71828-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="71828-163">Konfigurieren Sie Adressen, indem Sie die Werte auf der Registerkarte **Location Info Service config** im UserProvisioningTool ausfüllen, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="71828-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Das Benutzerbereitstellungstool zeigt die Anzahl der Adressen, Subnetze, Switche und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="71828-165">Wenn Sie alles im UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche " **LIS-Konfigurationsdateien generieren** ".</span><span class="sxs-lookup"><span data-stu-id="71828-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="71828-166">Nun werden CSV-Dateien für Ports, Subnets, Switches und drahtlose Zugriffspunkte (WAPs) sowie eine XML-Datei für das Stress-und Leistungstool generiert.</span><span class="sxs-lookup"><span data-stu-id="71828-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="71828-167">Sie können die CSV-Dateien für Eingaben verwenden, wenn Sie den Location Information Service (LIS) mit dem LisConfiguration. ps1-Skript konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71828-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="71828-168">Zu diesem Zweck müssen Sie die Datei "Locations0. xml" in denselben Ordner wie die ausführbare Druck-und Leistungs Tool-Datei (LyncPerfTool. exe) verschieben.</span><span class="sxs-lookup"><span data-stu-id="71828-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="71828-169">Auf diese Weise können Sie Standortprofil Szenarien (Wähl Plan) ausführen.</span><span class="sxs-lookup"><span data-stu-id="71828-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="71828-170">Konfigurieren der Antwortgruppen Anwendung</span><span class="sxs-lookup"><span data-stu-id="71828-170">Configuring Response Group application</span></span>
<span data-ttu-id="71828-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="71828-171"></span></span>

<span data-ttu-id="71828-172">Das Beispielskript lautet ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="71828-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="71828-173">Es gibt auch Cmdlets für die Antwortgruppen Anwendung, die für weitere Konfigurationsdetails zu überprüfen sind.</span><span class="sxs-lookup"><span data-stu-id="71828-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="71828-174">Im folgenden Diagramm werden einige Konfigurationsdetails angezeigt:</span><span class="sxs-lookup"><span data-stu-id="71828-174">The following diagram will show some of the configuration details:</span></span>
  
![Das Konfigurationstool für Reaktionsgruppen zeigt vorhandene Workflows für Testzwecke.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

