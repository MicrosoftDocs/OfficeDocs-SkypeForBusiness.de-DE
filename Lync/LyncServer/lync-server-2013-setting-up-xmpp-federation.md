---
title: 'Lync Server 2013: Einrichten des XMPP-Verbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6cbe8db6b432f8e837e110875881e86adab9c51
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="18630-102">Einrichten des XMPP-Verbunds in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18630-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18630-103">_**Letztes Änderungsstand des Themas:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="18630-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="18630-104">Um den XMPP-Proxy im Edgeserver bereitzustellen, müssen Sie die Edgeserver für XMPP-Verbund konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="18630-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="18630-105">Hierzu führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="18630-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="18630-106">Einrichten des XMPP-Verbunds</span><span class="sxs-lookup"><span data-stu-id="18630-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="18630-107">Melden Sie sich an dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.</span><span class="sxs-lookup"><span data-stu-id="18630-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="18630-108">Öffnen Sie auf dem Front-End-Server den Assistenten für die lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="18630-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="18630-109">Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen".</span><span class="sxs-lookup"><span data-stu-id="18630-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="18630-110">Klicken Sie auf "Erneut ausführen".</span><span class="sxs-lookup"><span data-stu-id="18630-110">Click Run Again.</span></span>

3.  <span data-ttu-id="18630-p103">Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="18630-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="18630-p104">Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".</span><span class="sxs-lookup"><span data-stu-id="18630-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="18630-p105">Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="18630-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="18630-122">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3: Zertifikate anfordern, installieren oder zuweisen auf Erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="18630-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="18630-123">Wenn Sie den Edgerserver zum ersten Mal bereitstellen, sehen Sie die Schaltfläche Ausführen anstatt Erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="18630-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="18630-124">Klicken Sie auf der Seite Verfügbare Zertifikataufgaben auf Neue Zertifikatanforderung erstellen.</span><span class="sxs-lookup"><span data-stu-id="18630-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="18630-125">Klicken Sie auf der Seite Zertifikatanforderung auf Externes Edgezertifikat.</span><span class="sxs-lookup"><span data-stu-id="18630-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="18630-126">Aktivieren Sie auf der Seite Verzögerte oder sofortige Anforderung das Kontrollkästchen Anforderung jetzt vorbereiten, jedoch später senden.</span><span class="sxs-lookup"><span data-stu-id="18630-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="18630-127">Geben Sie auf der Seite Zertifikatanforderungsdatei den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: Zertifikat "\_Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="18630-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="18630-128">Aktivieren Sie auf der Seite Alternative Zertifikatvorlage angeben das Kontrollkästchen Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18630-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="18630-129">Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="18630-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="18630-130">Geben Sie im Feld Anzeigename einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="18630-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="18630-131">Geben Sie im Feld Bitlänge die Bitlänge ein (typischerweise wird der Standardwert 2048 verwendet).</span><span class="sxs-lookup"><span data-stu-id="18630-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="18630-132">Stellen Sie sicher, dass das Kontrollkästchen Privaten Schlüssel des Zertifikats als "Exportierbar" markieren aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="18630-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="18630-133">Geben Sie auf der Seite Organisationsinformationen den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="18630-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="18630-134">Geben Sie auf der Seite Geografische Informationen die Standortinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="18630-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="18630-135">Auf der Seite Antragstellername/Alternative Antragstellernamen werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="18630-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="18630-136">Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.</span><span class="sxs-lookup"><span data-stu-id="18630-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="18630-137">Aktivieren Sie auf der Seite SIP-Domäneneinstellung für alternative Antragstellernamen (SANs) das Kontrollkästchen Domäne, um ein SIP hinzuzufügen. \<sipdomain "\> -Eintrag zur Liste der alternativen Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="18630-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="18630-138">Geben Sie auf der Seite zusätzliche Alternative Antragstellernamen konfigurieren zusätzliche Alternative Antragstellernamen an, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="18630-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="18630-p107">Bei der Installation des XMPP-Proxys wird in den Einträgen für den alternativen Antragstellernamen standardmäßig der Domänenname (z. B. contoso.com) gefüllt. Wenn Sie weitere Einträge benötigen, fügen Sie diese in diesem Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="18630-p107">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="18630-141">Überprüfen Sie auf der Seite Anforderungszusammenfassung die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18630-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="18630-142">Nachdem die Befehle ausgeführt wurden, können Sie auf Protokoll anzeigen oder auf Weiter klicken, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="18630-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="18630-143">Auf der Seite Zertifikatsanforderungsdatei können Sie die Signieranforderung für das Zertifikat (CSR-Datei) anzeigen, indem Sie auf Anzeigen klicken. Oder beenden Sie den Zertifikat-Assistenten, indem Sie auf Fertig stellen klicken.</span><span class="sxs-lookup"><span data-stu-id="18630-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="18630-144">Kopieren Sie die Anforderungsdatei, und übermitteln Sie diese an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="18630-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="18630-p108">Nachdem das öffentliche Zertifikat empfangen, importiert und zugewiesen wurde, müssen Sie die Edgeserverdienste beenden und neu starten. Geben Sie in der Lync Server-Verwaltungskonsole dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18630-p108">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="18630-147">Um DNS für den XMPP-Verbund zu konfigurieren, fügen Sie den folgenden SRV-Eintrag\_zu externem DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Zugriffs-Edge-FQDN des Edgeserver mit dem Portwert 5269 aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="18630-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="18630-148">Darüber hinaus konfigurieren Sie einen "A"-Hosteintrag (beispielsweise xmpp.contoso.com), der auf die IP-Adresse des Access-Edgeserver verweist.</span><span class="sxs-lookup"><span data-stu-id="18630-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="18630-149">Wenn Sie über Edge-Pools an mehreren Standorten verfügen, wird empfohlen, dass Sie mehrere SRV-Einträge für den XMPP-Partnerverbund hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="18630-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="18630-150">Fügen Sie für jede Edgepool in Ihrer Organisation einen SRV-Eintrag hinzu, und geben Sie jedem dieser SRV-Einträge eine andere Priorität.</span><span class="sxs-lookup"><span data-stu-id="18630-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="18630-151">Wenn alle Edge-Pools ausgeführt werden, werden alle XMPP-Anforderungen von der Edgepool mit der ersten Priorität verarbeitet, aber wenn dieser Edgepool ausfällt, müssen Sie keinen neuen SRV-Eintrag hinzufügen, um die XMPP-Verbund Funktionalität wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="18630-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="18630-152">Konfigurieren Sie eine neue Richtlinie für den externen Zugriff, um alle Benutzer zu aktivieren, indem Sie die lync Server-Verwaltungsshell auf dem Front-End öffnen und Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="18630-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="18630-153">Aktivieren Sie XMPP-Zugriff für externe Benutzer, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="18630-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="18630-154">Öffnen Sie auf dem Edgeserver, in dem der XMPP-Proxy bereitgestellt wird, eine Eingabeaufforderung oder eine Windows PowerShell™ Befehlszeilenschnittstelle, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18630-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="18630-155">Der Befehl **netstat – ano** ist ein Befehl "Netzwerkstatistik", die Parameter **– Ano-** Anforderung, dass netstat alle Verbindungen und Abhör-Ports, die Adresse und die Ports anzeigen, in numerischer Form angezeigt werden, und dass der besitzenden Prozess-ID jeder Verbindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="18630-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="18630-156">Das Zeichen **|** definiert eine Pipe für die nächste Befehls-, **findstr**-oder Find-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="18630-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="18630-157">Die Zahl 5269 und 23456, die an findstr als Parameter übergeben wird, weist findstr an, die Ausgabe von netstat für die Zeichenfolgen 5269 und 23456 zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="18630-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="18630-158">Wenn XMPP ordnungsgemäß konfiguriert ist, sollte das Ergebnis der Befehle zum hören und zum Herstellen von Verbindungen führen, sowohl auf der externen (Port 5269) als auch auf den internen Schnittstellen (Port 23456) des Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="18630-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="18630-159">Wenn die Befehle keine festgelegten oder abhörenden Ports an 5269 und 23456 zurückgeben, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="18630-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="18630-160">Problembehandlung beim XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="18630-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="18630-161">Gehen Sie folgendermaßen vor, um festzustellen, ob der XMPP-Proxy aktiv ist:</span><span class="sxs-lookup"><span data-stu-id="18630-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="18630-162">Melden Sie sich bei dem Edgeserver, auf dem der XMPP-Proxy Dienst läuft, als Mitglied der lokalen Administratorgruppe an.</span><span class="sxs-lookup"><span data-stu-id="18630-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="18630-163">Klicken Sie im **Startmenü**auf **Alle Programme**, dann auf **Verwaltung**und dann auf **Dienste** .</span><span class="sxs-lookup"><span data-stu-id="18630-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="18630-164">Suchen Sie in Dienste nach lync Server XMPP-Übersetzungs Gateway-Proxy.</span><span class="sxs-lookup"><span data-stu-id="18630-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="18630-165">Der Dienst sollte den Status **gestartet** aufweisen.</span><span class="sxs-lookup"><span data-stu-id="18630-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="18630-166">Wenn er nicht gestartet wurde, klicken Sie in der Symbolleiste auf das Symbol **Start** .</span><span class="sxs-lookup"><span data-stu-id="18630-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="18630-167">Das Symbol wird als grüner, nach rechts zeigender Pfeil angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18630-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="18630-168">Stellen Sie sicher, dass der Dienst in **gestartet**geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="18630-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="18630-169">Wenn er erfolgreich gestartet wurde, schließen Sie **Dienste** , und fahren Sie fort.</span><span class="sxs-lookup"><span data-stu-id="18630-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="18630-170">Wenn der Dienst nicht erfolgreich gestartet wurde, öffnen Sie in der Verwaltungs Tools die Ereignisanzeige, und lesen Sie die Fehler und Warnungen im Abschnitt **lync Server** unter **Anwendungs-und Dienstprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="18630-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="18630-171">Nachdem der **lync Server XMPP-Übersetzungs Gateway** -Dienst aktiv ist, überprüfen Sie die zuvor verwendeten netstat-Befehle erneut.</span><span class="sxs-lookup"><span data-stu-id="18630-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="18630-172">Wenn Sie keine festgelegten oder Überwachungssitzungen sehen, überprüfen und sicherstellen, dass die **XMPP-Verbund Route** ordnungsgemäß im Topologie-Generator konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="18630-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="18630-173">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="18630-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="18630-174">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="18630-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="18630-175">Wählen Sie im Topologie-Generator den Standort für die XMPP-Verbund Route aus, und überprüfen Sie, um zu bestätigen, dass die **Standort Verbund-Routen Zuweisung** für **XMPP-Verbund** ihre Edgeserver oder Edgepool als ausgewählte XMPP-Verbund Routen Zuweisung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="18630-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="18630-176">Wenn die Routen Zuweisung falsch oder nicht festgelegt ist, klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="18630-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="18630-177">Aktivieren Sie das Kontrollkästchen XMPP Federation, und wählen Sie dann die richtige Edgeserver oder Edgepool aus.</span><span class="sxs-lookup"><span data-stu-id="18630-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="18630-178">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="18630-178">Publish the topology.</span></span> <span data-ttu-id="18630-179">Ausführliche Informationen finden Sie unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="18630-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="18630-180">Obwohl dies nicht erforderlich ist und in der Regel nicht erforderlich ist, müssen Sie die Edgeserver möglicherweise neu starten.</span><span class="sxs-lookup"><span data-stu-id="18630-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="18630-181">Überprüfen Sie mithilfe des zuvor verwendeten netstat-Prozesses, ob der Edgeserver nun Sitzungen auf Port 5269 und Port 23456 überwacht oder eingerichtet hat.</span><span class="sxs-lookup"><span data-stu-id="18630-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="18630-182">Wenn die erwarteten Sitzungen immer noch nicht angezeigt werden, überprüfen Sie die Ereignisanzeige auf mögliche Ursachen für das Kommunikationsproblem.</span><span class="sxs-lookup"><span data-stu-id="18630-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18630-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18630-183">See Also</span></span>


[<span data-ttu-id="18630-184">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="18630-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="18630-185">Verwalten von XMPP-Verbundpartnern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18630-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

