---
title: Skype Room System – Verbesserte Verwaltung und Tools
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.
ms.openlocfilehash: 74c484b321312fc77c7a1e892f41bdeac8af49ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768858"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="3abde-103">Skype Room System – Verbesserte Verwaltung und Tools</span><span class="sxs-lookup"><span data-stu-id="3abde-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="3abde-104">Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="3abde-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="3abde-105">Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="3abde-105">Administrative Portal</span></span>

<span data-ttu-id="3abde-106">Bei lokalen Bereitstellungen von Skype for Business Server können Sie das administrative Portal für das Skype Room-System nutzen, um die Bereitstellung von Skype Room-Systemen in Ihrer Organisation aktiv zu verwalten und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="3abde-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="3abde-107">Weitere Informationen finden Sie im folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="3abde-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="3abde-108">Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3abde-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="3abde-109">Exchange-Checkliste</span><span class="sxs-lookup"><span data-stu-id="3abde-109">Exchange Checklist</span></span>

- <span data-ttu-id="3abde-110">Stellen Sie sicher, dass der AutoErmittlungsdienst eingerichtet ist und dass ein interner DNS-A/CNAME-Eintrag für „autodiscover.domain.com“ verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3abde-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="3abde-111">Senden Sie ein Pingsignal an den AutoErmittlungsdienst (z. B. „ping autodiscover.contoso.com“).</span><span class="sxs-lookup"><span data-stu-id="3abde-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="3abde-112">Testen Sie Ihren AutoErmittlungsdienst mithilfe des Tools Microsoft Connectivity Analyzer.</span><span class="sxs-lookup"><span data-stu-id="3abde-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="3abde-113">Wählen Sie den ersten Test "Ich kann mich nicht mit Office Outlook anmelden" aus.</span><span class="sxs-lookup"><span data-stu-id="3abde-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="3abde-114">Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, erweitern Sie dieses Konto für das Skype-Raum System (Beispielskript unten auf der Seite).</span><span class="sxs-lookup"><span data-stu-id="3abde-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="3abde-115">Skype for Business-Checkliste</span><span class="sxs-lookup"><span data-stu-id="3abde-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="3abde-116">Führen Sie die folgenden Tools aus:</span><span class="sxs-lookup"><span data-stu-id="3abde-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="3abde-117">Skype for Business Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="3abde-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="3abde-118">Skype for Business-Integritätsanalyse Tool (Excel)</span><span class="sxs-lookup"><span data-stu-id="3abde-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="3abde-119">Skype for Business Connectivity Analyzer 32-Bit oder 64-Bit</span><span class="sxs-lookup"><span data-stu-id="3abde-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="3abde-120">Überprüfen Sie [hilfreiche neue Problem Behandlungs-und Analysetools für Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="3abde-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="3abde-121">Bestätigen Sie, dass Sie über einen Skype for Business-Pool und einen Office Web Apps-Server verfügen und eine PowerPoint-Plattform über den Skype for Business-Client freigeben können.</span><span class="sxs-lookup"><span data-stu-id="3abde-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="3abde-122">Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, aktivieren Sie es für Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3abde-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="3abde-123">Falls erforderlich, fordern Sie eine DID-Telefonnummer (direkte Durchwahl) für das Konferenzraumsystem an und aktualisieren Sie das Feld für die allgemeine Telefonnummer im Active Directory-Tool.</span><span class="sxs-lookup"><span data-stu-id="3abde-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="3abde-124">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3abde-124">Network</span></span>

- <span data-ttu-id="3abde-125">Stellen Sie sicher, dass Sie über eine kabelgebundene Netzwerkverbindung für das Skype Room-System verfügen.</span><span class="sxs-lookup"><span data-stu-id="3abde-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="3abde-126">Lesen Sie das Netzwerk Planungshandbuch für Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3abde-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="3abde-127">Fordern Sie eine Skype for Business-Netzwerkbewertung von einem Skype for Business-Partner an.</span><span class="sxs-lookup"><span data-stu-id="3abde-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="3abde-128">Lesen Sie die Leistungsdaten, die im Skype for Business-Integritätsanalyse Tool (Excel) erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="3abde-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="3abde-129">Führen Sie das Netzwerkanalysetool aus.</span><span class="sxs-lookup"><span data-stu-id="3abde-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="3abde-130">Führen Sie das Vor-Anruf-Diagnosetool aus.</span><span class="sxs-lookup"><span data-stu-id="3abde-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="3abde-131">Skype Room-System Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3abde-131">Skype Room System Security</span></span>

<span data-ttu-id="3abde-132">Skype Room System ist ein eingebettetes System, das vollständig in eine Windows-Bereitstellung mit dem Skype for Business-Sicherheitsmodell, Rechteverwaltung und Verwaltungstools wie SCOM integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3abde-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="3abde-133">Zu den Features gehören:</span><span class="sxs-lookup"><span data-stu-id="3abde-133">Features include:</span></span>
  
- <span data-ttu-id="3abde-134">Ein Schreibfilter, um zu verhindern, dass im Benutzermodus auf Datenträger geschrieben wird</span><span class="sxs-lookup"><span data-stu-id="3abde-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="3abde-p104">Eine App-Sperre, um zu vermeiden, dass nicht autorisierte Apps ausgeführt werden. Im Benutzermodus sind alle USB-Anschlüsse deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3abde-p104">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="3abde-137">Auf der System Hardware von Skype Room befinden sich keine Standard-Apps oder-Viewer.</span><span class="sxs-lookup"><span data-stu-id="3abde-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="3abde-138">Alle Inhalte werden über das HTTP- oder das RDP-Protokoll wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="3abde-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="3abde-p106">Der Anwendungs-PC führt das Betriebssystem „Windows Embedded Standard 7“ aus. Sämtliche Hardware, einschließlich der Geräte, wird von OEM-Partnern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3abde-p106">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="3abde-141">Optionale „Domain Join to Active Directory Domain“-Dienste (AD DS) ermöglichen die lokale Sicherheitskontenverwaltung und -steuerung.</span><span class="sxs-lookup"><span data-stu-id="3abde-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="3abde-142">Sie können das lokale Administratorkonto auch über das Skype for Business Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="3abde-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="3abde-143">Das Skype Room-System wird über standardmäßige Microsoft Update-Prozesse aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3abde-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="3abde-144">Skype Room System stellt eine Verbindung mit Skype for Business her.</span><span class="sxs-lookup"><span data-stu-id="3abde-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="3abde-145">Skype for Business verwendet End-to-End-Verschlüsselung und-Autorisierung für alle Kommunikationsmodi</span><span class="sxs-lookup"><span data-stu-id="3abde-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="3abde-146">Skype Room System unterstützt Skype for Business-Sicherheits-und Compliance-Standards.</span><span class="sxs-lookup"><span data-stu-id="3abde-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="3abde-147">Weitere Informationen finden Sie unter [Planen der Sicherheit in Skype for Business Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="3abde-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="3abde-148">Lizenz</span><span class="sxs-lookup"><span data-stu-id="3abde-148">License</span></span>

<span data-ttu-id="3abde-149">Stellen Sie sicher, dass Sie für die Aktivierung von Software einen KMS verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abde-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="3abde-150">In diesem Fall müssen Sie möglicherweise den Skype for Business-Client-KMS-Schlüssel überprüfen oder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3abde-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="3abde-151">Wenn Sie KMS nicht verwenden, fordern Sie den Volumen Lizenzierungsschlüssel für den Skype for Business-Client MAK an.</span><span class="sxs-lookup"><span data-stu-id="3abde-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="3abde-152">Lizenzschlüssel</span><span class="sxs-lookup"><span data-stu-id="3abde-152">License keys</span></span>

<span data-ttu-id="3abde-153">Skype Room System führt den Skype for Business-Desktop-Client im Hintergrund aus.</span><span class="sxs-lookup"><span data-stu-id="3abde-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="3abde-154">Wenn Skype Room System ein Domänenmitglied ist, wird es ihren KMS entdecken.</span><span class="sxs-lookup"><span data-stu-id="3abde-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="3abde-155">(und wenn Sie über den KMS-Schlüssel für die Volumenlizenzierung verfügt, wird Sie automatisch aktiviert).</span><span class="sxs-lookup"><span data-stu-id="3abde-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="3abde-156">Die Volumenlizenzierung bietet auch einen MAK, den Sie beim Anzeigen von XXXXX-XXXXX-XXXXX-XXXXX eingeben.</span><span class="sxs-lookup"><span data-stu-id="3abde-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="3abde-157">(Sie benötigen Internet Zugriff, um die Verwendung von MAK, aber nicht KMS) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3abde-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="3abde-158">Weitere Informationen finden Sie unter Volumenaktivierung von Office 2013.</span><span class="sxs-lookup"><span data-stu-id="3abde-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="3abde-159">Zum Eingeben des MAK-Schlüssels wechseln Sie zu OEM \> -Einstellungen SRS-Lizenzierungs Tool.</span><span class="sxs-lookup"><span data-stu-id="3abde-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="3abde-160">Klicken Sie auf „Status überprüfen“.</span><span class="sxs-lookup"><span data-stu-id="3abde-160">Click Check Status.</span></span> <span data-ttu-id="3abde-161">Wenn der Status "Produkt ist nicht aktiviert" lautet, geben Sie den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="3abde-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="3abde-162">Wenn während der Aktivierung eine Fehlermeldung angezeigt wird, die besagt, dass der Software Lizenzierungsdienst gemeldet hat, dass der Product Key ungültig ist, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3abde-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="3abde-163">der Schlüssel korrekt eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3abde-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="3abde-164">Sie haben den Skype for Business-MAK-Schlüssel und nicht einen anderen Schlüssel eingegeben.</span><span class="sxs-lookup"><span data-stu-id="3abde-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="3abde-165">das System Zugang zum Internet hat.</span><span class="sxs-lookup"><span data-stu-id="3abde-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="3abde-166">Sie können per Telefon aktivieren, müssen aber zunächst versucht haben, mit dem SRS Licensing Tool zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3abde-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="3abde-167">Um per Telefon zu aktivieren, starten Sie eine Testbesprechung (nicht einen Testanruf, denn der wäre zu kurz).</span><span class="sxs-lookup"><span data-stu-id="3abde-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="3abde-168">Wählen Sie im Office-Aktivierungs-Assistententelefon Aktivierung aus, rufen Sie Microsoft an, geben Sie die lange Nummer ein, und geben Sie eine Antwort ein.</span><span class="sxs-lookup"><span data-stu-id="3abde-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="3abde-169">Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="3abde-169">Certificate Authority</span></span>

<span data-ttu-id="3abde-170">Überprüfen Sie, ob die für die Ausgabe des Zertifikats für Office Web Apps Server 2013 verwendete Zertifizierungsstelle über einen HTTP-Pfad verfügt, der in der Eigenschaft „Certificate Revocation List“ enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3abde-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="3abde-171">Importieren Sie die Zertifikatsdatei (. CRT) in das Skype Room-System, wenn Sie Skype for Business Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abde-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="3abde-172">Sie kann ganz einfach aus dem CertEnroll-Kontingent des CA-Servers oder aus dem Trusted Root-Ordner jedes an die Domäne angeschlossenen PCs bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="3abde-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="3abde-173">Zertifikate</span><span class="sxs-lookup"><span data-stu-id="3abde-173">Certificates</span></span>

<span data-ttu-id="3abde-p113">Stellen Sie sicher, dass Ihre Zertifizierungsstelle über einen HTTP-Pfad für die Zertifikatssperrliste (Certificate Revocation List; CRL) verfügt. Sollte das nicht der Fall sein, aktualisieren Sie Ihre CA, damit ein HTTP-Pfad vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3abde-p113">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="3abde-176">Installieren Sie Zertifikate in der Administrator Einrichtung des Skype Room-Systems unter System \> Einstellungen Zertifikat-Manager.</span><span class="sxs-lookup"><span data-stu-id="3abde-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="3abde-177">Sie benötigen die Stammzertifizierungsstelle (Enterprise Root CA) für Ihr internes Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="3abde-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="3abde-178">Eine Möglichkeit zum Abrufen der erforderlichen Zertifikate ist die Ermittlung der Zertifizierungsstelle, die Ihre Zertifikate ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="3abde-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="3abde-179">Klicken Sie bei Skype for Business Server auf einem PC in Skype for Business auf Einstellungen \> Tools \> Einwahlkonferenzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3abde-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="3abde-180">Dadurch wird eine Webseite geöffnet, die von der Zertifizierungsstelle, die die internen Zertifikate ausgestellt hat, gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="3abde-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="3abde-181">Klicken Sie auf das Sperren-Symbol in der Adressleiste des Browsers, damit ein Sicherheitsbericht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3abde-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="3abde-182">Klicken Sie auf „Zertifikate anzeigen“ und überprüfen Sie die Eigenschaft „CRL Distribution Point“.</span><span class="sxs-lookup"><span data-stu-id="3abde-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="3abde-183">Der zweite CN-Parameter sollte der Servername der Zertifizierungsstelle sein.</span><span class="sxs-lookup"><span data-stu-id="3abde-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="3abde-184">Öffnen Sie nun den Windows-Explorer \\ \< für diesen Adress \>-ca-Server Namen \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="3abde-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="3abde-185">Kopieren Sie die beiden .crl-Dateien und die .crt-Datei auf einen Speicherstick und stecken Sie diesen auf der linken Seite des SmartBoards ein.</span><span class="sxs-lookup"><span data-stu-id="3abde-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="3abde-186">Importieren Sie die CRT-Datei in das Skype Room-System unter Trusted Room Certification Authority-Ordner.</span><span class="sxs-lookup"><span data-stu-id="3abde-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="3abde-187">Importieren Sie die CRL-Dateien im Skype Room-System unter dem Ordner Zwischenzertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="3abde-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="3abde-188">(Sie müssen den Filter für Dateierweiterungen im Zertifikat-Manager zu „.crl“ ändern, damit die Dateien angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="3abde-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="3abde-189">Hinweis: der Office Web Apps 2013-Server hat möglicherweise dieselbe Zertifizierungsstelle wie Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3abde-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="3abde-190">Ist dies nicht der Fall, können Sie PowerPoint in einer Besprechung nicht gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="3abde-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="3abde-191">Erkundigen Sie sich bei der IT-Abteilung und besorgen Sie sich die .crt- und .crl-Dateien aus dem CA-Netzwerkkontingent CertEnroll, wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3abde-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="3abde-192">Die Domänenmitgliedschaft kann einige Dinge vereinfachen, da Sie das Skype Room-System als Windows-System behandeln können und es sich auf Active Directory für einige der Zertifikat Aspekte verlassen kann.</span><span class="sxs-lookup"><span data-stu-id="3abde-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="3abde-193">Es empfiehlt sich jedoch, diese manuell zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="3abde-193">However, it's best to manually manage this.</span></span>
  

