---
title: 'Lync Server 2013: Einrichten eines XMPP-Partnerverbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cda79f7b80d6f1bbdf2163ecf987f4a05949bfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="504fe-102">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="504fe-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="504fe-103">_**Letztes Änderungsdatum des Themas:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="504fe-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="504fe-104">Wenn Sie den XMPP-Proxy auf dem Edgeserver bereitstellen möchten, müssen Sie den Edgeserver für die XMPP-Föderation konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="504fe-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="504fe-105">Führen Sie dazu die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="504fe-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="504fe-106">Einrichten von XMPP Federation</span><span class="sxs-lookup"><span data-stu-id="504fe-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="504fe-107">Melden Sie sich bei dem Computer an, auf dem der lync Server-Bereitstellungs-Assistent als Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" installiert ist.</span><span class="sxs-lookup"><span data-stu-id="504fe-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="504fe-108">Öffnen Sie auf dem Front-End-Server den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="504fe-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="504fe-109">Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="504fe-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="504fe-110">Klicken Sie erneut auf ausführen.</span><span class="sxs-lookup"><span data-stu-id="504fe-110">Click Run Again.</span></span>

3.  <span data-ttu-id="504fe-111">Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="504fe-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="504fe-112">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="504fe-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="504fe-113">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="504fe-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="504fe-114">Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="504fe-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="504fe-115">Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="504fe-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="504fe-116">Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="504fe-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="504fe-117">Klicken Sie erneut auf ausführen.</span><span class="sxs-lookup"><span data-stu-id="504fe-117">Click Run Again.</span></span>

5.  <span data-ttu-id="504fe-118">Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="504fe-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="504fe-119">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="504fe-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="504fe-120">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="504fe-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="504fe-121">Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="504fe-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="504fe-122">Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten auf erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="504fe-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="504fe-123">Wenn Sie den Edgeserver zum ersten Mal bereitstellen, wird Run anstelle von Run erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="504fe-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="504fe-124">Klicken Sie auf der Seite Verfügbare Zertifikataufgaben auf Neue Zertifikatsanforderung erstellen.</span><span class="sxs-lookup"><span data-stu-id="504fe-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="504fe-125">Klicken Sie auf der Seite Zertifikatanforderung auf externes Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="504fe-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="504fe-126">Aktivieren Sie auf der Seite verzögerte oder sofortige Anforderung das Kontrollkästchen Anforderung jetzt vorbereiten, aber später senden.</span><span class="sxs-lookup"><span data-stu-id="504fe-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="504fe-127">Geben Sie auf der Seite Zertifikatanforderungsdatei den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").</span><span class="sxs-lookup"><span data-stu-id="504fe-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="504fe-128">Aktivieren Sie auf der Seite Alternative Zertifikatvorlage angeben für das Kontrollkästchen Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden, um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="504fe-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="504fe-129">Führen Sie auf der Seite  Namens- und Sicherheitseinstellungen  die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="504fe-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="504fe-130">Geben Sie unter Anzeigename einen Anzeigenamen für das Zertifikat ein.</span><span class="sxs-lookup"><span data-stu-id="504fe-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="504fe-131">Geben Sie in Bit length die Bit-Länge an (in der Regel der Standardwert von 2048).</span><span class="sxs-lookup"><span data-stu-id="504fe-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="504fe-132">Überprüfen, ob das Kontrollkästchen "Zertifikat privater Schlüssel als exportierbar kennzeichnen" aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="504fe-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="504fe-133">Geben Sie auf der Seite Organisationsinformationen den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).</span><span class="sxs-lookup"><span data-stu-id="504fe-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="504fe-134">Geben Sie auf der Seite geographische Informationen die Standortinformationen an.</span><span class="sxs-lookup"><span data-stu-id="504fe-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="504fe-135">Auf der Seite Betreffname/Subject Alternative Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="504fe-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="504fe-136">Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.</span><span class="sxs-lookup"><span data-stu-id="504fe-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="504fe-137">Aktivieren Sie in der SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs) das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.</span><span class="sxs-lookup"><span data-stu-id="504fe-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="504fe-138">Geben Sie auf der Seite Configure additional Subject Alternative Names die zusätzlichen alternativen Subjektnamen an, die erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="504fe-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="504fe-139">Wenn der XMPP-Proxy installiert ist, wird standardmäßig der Domänenname (wie contoso.com) in den San-Einträgen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="504fe-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="504fe-140">Wenn Sie weitere Einträge benötigen, fügen Sie Sie in diesem Schritt hinzu.</span><span class="sxs-lookup"><span data-stu-id="504fe-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="504fe-141">Überprüfen Sie auf der Seite Anforderungszusammenfassung die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="504fe-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="504fe-142">Nachdem die Befehle ausgeführt wurden, können Sie das Protokoll anzeigen oder auf Weiter klicken, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="504fe-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="504fe-143">Auf der Seite Zertifikatanforderungsdatei können Sie die generierte CSR-Datei (Certificate Signing Request) anzeigen, indem Sie auf Fertig stellen klicken oder den Zertifikat-Assistenten verlassen.</span><span class="sxs-lookup"><span data-stu-id="504fe-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="504fe-144">Kopieren Sie die Anforderungsdatei, und senden Sie Sie an Ihre öffentliche Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="504fe-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="504fe-145">Nachdem Sie das öffentliche Zertifikat empfangen, importiert und zugewiesen haben, müssen Sie die Edgeserver-Dienste beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="504fe-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="504fe-146">Hierzu geben Sie in der lync Server-Verwaltungskonsole Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="504fe-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```
        Stop-CsWindowsService
       ```
    
       ```
        Start-CsWindowsService
       ```

23. <span data-ttu-id="504fe-147">Zum Konfigurieren von DNS für die XMPP-Föderation fügen Sie den folgenden SRV-Eintrag zu\_externem DNS hinzu: XMPP-Server. \_TCP. \<Domänenname\> der SRV-Eintrag wird in den Access-Edge-FQDN des Edge-Servers mit einem Portwert von 5269 aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="504fe-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="504fe-148">Darüber hinaus konfigurieren Sie einen "A"-Hosteintrag (beispielsweise xmpp.contoso.com), der auf die IP-Adresse des Access Edge-Servers verweist.</span><span class="sxs-lookup"><span data-stu-id="504fe-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="504fe-149">Wenn Sie über Edge-Pools an mehreren Standorten verfügen, empfehlen wir, dass Sie mehrere SRV-Einträge für die XMPP-Föderation hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="504fe-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="504fe-150">Fügen Sie einen SRV-Eintrag für jeden Edge-Pool in Ihrer Organisation hinzu, und geben Sie jedem dieser SRV-Einträge eine andere Priorität.</span><span class="sxs-lookup"><span data-stu-id="504fe-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="504fe-151">Wenn alle Edge-Pools ausgeführt werden, werden alle XMPP-Anforderungen vom Edge-Pool mit der ersten Priorität verarbeitet, doch wenn dieser Edge-Pool ausfällt, müssen Sie keinen neuen SRV-Eintrag hinzufügen, um die Funktion der XMPP-Föderation wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="504fe-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="504fe-152">Konfigurieren Sie eine neue Richtlinie für den externen Zugriff, um alle Benutzer zu aktivieren, indem Sie die lync Server-Verwaltungsshell auf dem Front-End öffnen und Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="504fe-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="504fe-153">Aktivieren Sie den XMPP-Zugriff für externe Benutzer, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="504fe-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="504fe-154">Öffnen Sie auf dem Edgeserver, auf dem der XMPP-Proxy bereitgestellt wird, eine Eingabeaufforderung oder eine Windows PowerShell-™ Befehlszeilenschnittstelle, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="504fe-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```
        Netstat -ano | findstr 5269
       ```
    
       ```
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="504fe-155">Der Befehl **netstat – ano** ist ein Netzwerkstatistik Befehl, die Parameter **– Ano-** Anforderung, dass netstat alle Verbindungen und Abhör Anschlüsse anzeigt, Adresse und Ports werden in einer numerischen Form angezeigt, und die besitzende Prozess-ID ist zugeordnet bei jeder Verbindung.</span><span class="sxs-lookup"><span data-stu-id="504fe-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="504fe-156">Das Zeichen **|** definiert eine Pipe für den nächsten Befehl, die **findstr**oder die Suchzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="504fe-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="504fe-157">Die Zahl 5269 und 23456, die als Parameter an findstr übergeben wird, weist findstr an, die Ausgabe von netstat für die Zeichenfolgen 5269 und 23456 zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="504fe-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="504fe-158">Wenn XMPP ordnungsgemäß konfiguriert ist, sollte das Ergebnis der Befehle zum Überwachen und Herstellen von Verbindungen führen, die sowohl auf dem externen (Port 5269) als auch auf den internen (Port 23456)-Schnittstellen des Edge-Servers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="504fe-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="504fe-159">Wenn die Befehle keine festgelegten oder abhörenden Ports auf 5269 und 23456 zurückgeben, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="504fe-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="504fe-160">Problembehandlung bei der XMPP-Föderation</span><span class="sxs-lookup"><span data-stu-id="504fe-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="504fe-161">Gehen Sie wie folgt vor, um festzustellen, ob der XMPP-Proxy ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="504fe-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="504fe-162">Melden Sie sich beim Edgeserver, auf dem der XMPP-Proxy Dienst ausgeführt wird, als Mitglied der lokalen Administratorgruppe an.</span><span class="sxs-lookup"><span data-stu-id="504fe-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="504fe-163">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, klicken Sie auf **Dienste** .</span><span class="sxs-lookup"><span data-stu-id="504fe-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="504fe-164">Suchen Sie in Dienste nach lync Server XMPP übersetzen des Gateway-Proxys.</span><span class="sxs-lookup"><span data-stu-id="504fe-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="504fe-165">Der Dienst sollte den Status " **gestartet** " aufweisen.</span><span class="sxs-lookup"><span data-stu-id="504fe-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="504fe-166">Wenn Sie nicht gestartet wurde, klicken Sie auf der Symbolleiste auf das Symbol **Start** .</span><span class="sxs-lookup"><span data-stu-id="504fe-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="504fe-167">Das Symbol wird als grüner, nach rechts zeigender Pfeil angezeigt.</span><span class="sxs-lookup"><span data-stu-id="504fe-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="504fe-168">Überprüfen Sie, ob der Dienst in **Started**geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="504fe-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="504fe-169">Wenn Sie erfolgreich gestartet wurde, schließen Sie **Dienste** , und fahren Sie fort.</span><span class="sxs-lookup"><span data-stu-id="504fe-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="504fe-170">Wenn der Dienst nicht erfolgreich gestartet wurde, öffnen Sie in den Verwaltungs Tools die Ereignisanzeige, und verweisen Sie auf die Fehler und Warnungen im **lync Server** -Abschnitt unter **Anwendungen und Dienstprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="504fe-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="504fe-171">Nachdem der **lync Server XMPP** -Konvertierungs-Gatewayserver ausgeführt wurde, überprüfen Sie die zuvor verwendeten netstat-Befehle erneut.</span><span class="sxs-lookup"><span data-stu-id="504fe-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="504fe-172">Wenn Sie keine festgelegten oder anhörenden Sitzungen sehen, überprüfen und sicherstellen, dass die **XMPP-Föderations Route** im Topologie-Generator richtig konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="504fe-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="504fe-173">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="504fe-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="504fe-174">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="504fe-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="504fe-175">Wählen Sie im Topologie-Generator die Website für die XMPP-Föderations Route und überprüfen aus, um zu bestätigen, dass die **Standort Verbund-Routenzuordnung** für den **XMPP-Verbund** Ihren Edge-Server oder Edge-Pool als ausgewählte XMPP-Verbund Routenzuordnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="504fe-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="504fe-176">Wenn die Arbeitsplanzuordnung falsch ist oder nicht eingerichtet ist, klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="504fe-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="504fe-177">Aktivieren Sie das Kontrollkästchen XMPP Federation, und wählen Sie dann den richtigen Edgeserver oder Edge-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="504fe-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="504fe-178">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="504fe-178">Publish the topology.</span></span> <span data-ttu-id="504fe-179">Ausführliche Informationen finden Sie unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="504fe-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="504fe-180">Obwohl dies nicht erforderlich ist und in der Regel nicht erforderlich ist, müssen Sie möglicherweise die Edgeserver neu starten.</span><span class="sxs-lookup"><span data-stu-id="504fe-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="504fe-181">Überprüfen Sie mithilfe des zuvor verwendeten netstat-Prozesses, ob der Edgeserver jetzt zuhört oder Sitzungen auf Port 5269 und Port 23456 eingerichtet hat.</span><span class="sxs-lookup"><span data-stu-id="504fe-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="504fe-182">Wenn die erwarteten Sitzungen immer noch nicht angezeigt werden, überprüfen Sie die Ereignisanzeige auf mögliche Ursachen für das Kommunikationsproblem.</span><span class="sxs-lookup"><span data-stu-id="504fe-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="504fe-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="504fe-183">See Also</span></span>


[<span data-ttu-id="504fe-184">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</span><span class="sxs-lookup"><span data-stu-id="504fe-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="504fe-185">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="504fe-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

