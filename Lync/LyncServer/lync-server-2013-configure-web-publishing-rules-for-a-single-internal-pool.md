---
title: 'Lync Server 2013: Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="54279-102">Konfigurieren von Webveröffentlichungsregeln für einen einzelnen internen Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54279-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54279-103">_**Letztes Änderungsdatum des Themas:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="54279-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="54279-104">Microsoft Forefront Threat Management Gateway 2010 und Internet Information Server Application Request Routing (IIS arr) verwendet Webveröffentlichungsregeln zum Veröffentlichen interner Ressourcen, beispielsweise einer Besprechungs-URL, für Benutzer im Internet.</span><span class="sxs-lookup"><span data-stu-id="54279-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="54279-105">Zusätzlich zu den Webdienste-URLs für die virtuellen Verzeichnisse müssen Sie auch Veröffentlichungsregeln für einfache URLs, die LyncDiscover-URL und den Office Web Apps-Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="54279-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="54279-106">Für jede einfache URL müssen Sie eine einzelne Regel auf dem Reverseproxy erstellen, die auf diese einfache URL verweist.</span><span class="sxs-lookup"><span data-stu-id="54279-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="54279-107">Wenn Sie Mobilität bereitstellen und die automatische Ermittlung verwenden, müssen Sie eine Veröffentlichungsregel für die URL des externen AutoErmittlungsdiensts erstellen.</span><span class="sxs-lookup"><span data-stu-id="54279-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="54279-108">Für die automatische Ermittlung sind auch Veröffentlichungsregeln für die externe lync Server-Webdienste-URL für den Director-Pool und den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="54279-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="54279-109">Details zum Erstellen der Webveröffentlichungsregeln für die automatische Erkennung finden Sie unter [Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="54279-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="54279-110">Führen Sie die folgenden Verfahren aus, um Webveröffentlichungsregeln zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54279-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54279-111">Bei diesen Verfahren wird davon ausgegangen, dass Sie die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert haben oder Internet Information Server mit der Erweiterung Application Request Routing (IIS arr) installiert und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="54279-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="54279-112">Sie verwenden entweder TMG oder IIS arr.</span><span class="sxs-lookup"><span data-stu-id="54279-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="54279-113">So erstellen Sie eine Web Server-Veröffentlichungsregel auf dem Computer mit TMG 2010</span><span class="sxs-lookup"><span data-stu-id="54279-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="54279-114">Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="54279-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="54279-115">Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, wählen Sie **neu**aus, und klicken Sie dann auf **Website Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="54279-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="54279-116">Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die Veröffentlichungsregel ein (beispielsweise LyncServerWebDownloadsRule).</span><span class="sxs-lookup"><span data-stu-id="54279-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="54279-117">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="54279-118">Wählen Sie \*\*\*\* auf der Seite Veröffentlichungs **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="54279-119">Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **SSL verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="54279-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="54279-120">Geben Sie auf der Seite **interne Veröffentlichungs Details** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Webfarm ein, die den Inhalt der Besprechungsinhalte und des Adressbuchs im Feld **interner Websitename** hostet.</span><span class="sxs-lookup"><span data-stu-id="54279-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54279-121">Wenn es sich bei dem internen Server um einen Standard Edition-Server handelt, handelt es sich um den FQDN des Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="54279-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="54279-122">Wenn es sich bei dem internen Server um einen Front-End-Pool handelt, handelt es sich bei diesem FQDN um einen Hardware-Lastenausgleichsmodul (Virtual IP, VIP), mit dem die internen Webfarmserver ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="54279-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="54279-123">Der TMG-Server muss den FQDN in die IP-Adresse des internen Webservers auflösen können.</span><span class="sxs-lookup"><span data-stu-id="54279-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="54279-124">Wenn der TMG-Server den FQDN nicht in die richtige IP-Adresse auflösen kann, können Sie <STRONG>einen Computernamen oder eine IP-Adresse verwenden, um eine Verbindung mit dem veröffentlichten Server herzustellen</STRONG>, und dann im Feld <STRONG>Computername oder</STRONG> <STRONG>IP-Adresse</STRONG> die IP-Adresse des internen w eingeben. EB-Server.</span><span class="sxs-lookup"><span data-stu-id="54279-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="54279-125">In diesem Fall müssen Sie sicherstellen, dass Port 53 auf dem TMG-Server geöffnet ist und einen DNS-Server erreicht, der sich im Umkreisnetzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="54279-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="54279-126">Sie können auch Einträge in der lokalen Hosts-Datei verwenden, um die Namensauflösung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="54279-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="54279-127">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein.</span><span class="sxs-lookup"><span data-stu-id="54279-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54279-128">Im Website-Veröffentlichungs-Assistenten können Sie nur einen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="54279-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="54279-129">Zusätzliche Pfade können durch Ändern der Eigenschaften der Regel hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="54279-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="54279-130">Überprüfen Sie auf der Seite Details für den **öffentlichen Namen** , ob **dieser Domänenname** unter **Anforderungen annehmen für**ausgewählt ist, geben Sie im Feld **Öffentlicher Name** den FQDN der externen Webdienste ein.</span><span class="sxs-lookup"><span data-stu-id="54279-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="54279-131">Klicken Sie auf der Seite Weblistener **auswählen** auf **neu** , um den Assistenten für neue Weblistener-Definition zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="54279-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="54279-132">Geben Sie auf der Seite **Willkommen beim neuen** Weblistener-Assistenten im Feld Weblistener- **Name** einen Namen für den Weblistener ein (beispielsweise LyncServerWebServers).</span><span class="sxs-lookup"><span data-stu-id="54279-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="54279-133">Wählen Sie auf der Seite **Client Verbindungssicherheit** die Option **SSL-gesicherte Verbindungen mit Clients anfordern**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="54279-134">Wählen Sie auf der Seite Weblistener **-IP-Adresse** die Option **extern**aus, und klicken Sie dann auf **IP-Adressen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="54279-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="54279-135">Wählen Sie auf der Seite **externe Listener-IP-Auswahl** die Option **angegebene IP-Adresse auf dem Forefront TMG-Computer im ausgewählten Netzwerk**aus, wählen Sie die entsprechende IP-Adresse aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54279-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="54279-136">Wählen Sie auf der Seite **Listener SSL-Zertifikate** die Option **Zertifikat für jede IP-Adresse zuweisen**aus, wählen Sie die IP-Adresse aus, die dem externen Web-FQDN zugeordnet ist, und klicken Sie dann auf **Zertifikat auswählen**.</span><span class="sxs-lookup"><span data-stu-id="54279-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="54279-137">Wählen Sie auf der Seite **Zertifikat auswählen** das Zertifikat aus, das mit den in Schritt 9 angegebenen öffentlichen Namen übereinstimmt, und klicken Sie auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="54279-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="54279-138">Wählen Sie auf der Seite **Authentifizierungseinstellung** **keine Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="54279-139">Klicken Sie auf der Seite **SSO-Einstellungen** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="54279-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="54279-140">Überprüfen Sie auf der Seite **abschließen des** Weblistener-Assistenten, ob die Weblistener **-** Einstellungen korrekt sind, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="54279-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="54279-141">Wählen Sie \*\*\*\* auf der Seite Authentifizierungsdelegierung **keine Delegierung aus, aber der Client kann sich direkt authentifizieren**.</span><span class="sxs-lookup"><span data-stu-id="54279-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="54279-142">Klicken Sie auf der Seite **Benutzersatz** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="54279-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="54279-143">Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="54279-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="54279-144">Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="54279-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="54279-145">So erstellen Sie eine Web Server-Veröffentlichungsregel auf dem Computer, auf dem IIS arr ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="54279-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="54279-146">Binden Sie das Zertifikat, das Sie für den Reverse-Proxy verwenden, an das HTTPS-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="54279-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="54279-147">Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.</span><span class="sxs-lookup"><span data-stu-id="54279-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54279-148">Weitere Hilfe, Screenshots und Anleitungen zum Bereitstellen und Konfigurieren von IIS arr finden Sie im NextHop-Artikel <A href="http://go.microsoft.com/fwlink/?linkid=293391">Verwenden von IIS arr als Reverse-Proxy für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54279-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="54279-149">Wenn dies noch nicht geschehen ist, importieren Sie das Zertifikat, das Sie für den Reverse-Proxy verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="54279-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="54279-150">Klicken Sie im **Internet Informationsdienste (IIS)-Manager**auf den Namen des Reverse Proxyservers auf der linken Seite der Konsole.</span><span class="sxs-lookup"><span data-stu-id="54279-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="54279-151">Klicken Sie in der Mitte der Konsole unter **IIS** auf **Server Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="54279-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="54279-152">Klicken Sie mit der rechten Maustaste auf **Server Zertifikate** , und wählen Sie **Funktion öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="54279-153">Klicken Sie auf der rechten Seite der Konsole auf **importieren.**...</span><span class="sxs-lookup"><span data-stu-id="54279-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="54279-154">Geben Sie den Pfad und den Dateinamen des Zertifikats mit der Erweiterung ein, oder klicken Sie auf **...**</span><span class="sxs-lookup"><span data-stu-id="54279-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="54279-155">, um nach dem Zertifikat zu suchen.</span><span class="sxs-lookup"><span data-stu-id="54279-155">to browse for the certificate.</span></span> <span data-ttu-id="54279-156">Wählen Sie das Zertifikat aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="54279-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="54279-157">Geben Sie das Kennwort ein, mit dem der private Schlüssel geschützt wird (wenn Sie beim Exportieren des Zertifikats und des privaten Schlüssels ein Kennwort zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="54279-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="54279-158">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54279-158">Click **OK**.</span></span> <span data-ttu-id="54279-159">Wenn der Zertifikatimport erfolgreich war, wird das Zertifikat als Eintrag in der Mitte der Konsole als Eintrag in **Server Zertifikate**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54279-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="54279-160">Weisen Sie das Zertifikat zur Verwendung durch HTTPS zu.</span><span class="sxs-lookup"><span data-stu-id="54279-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="54279-161">Wählen Sie auf der linken Seite der Konsole die **Standardwebsite** des IIS-Servers aus.</span><span class="sxs-lookup"><span data-stu-id="54279-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="54279-162">Klicken Sie auf der rechten Seite auf **Bindungen...**.</span><span class="sxs-lookup"><span data-stu-id="54279-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="54279-163">Klicken Sie im Dialogfeld **Websitebindungen** auf **hinzufügen.**...</span><span class="sxs-lookup"><span data-stu-id="54279-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="54279-164">Wählen Sie im Dialogfeld **Websitebindung hinzufügen** unter **Typ:** die Option **https**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="54279-165">Wenn Sie HTTPS auswählen, können Sie das Zertifikat auswählen, das für HTTPS verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="54279-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="54279-166">Wählen Sie unter **SSL-Zertifikat:** das Zertifikat aus, das Sie für den Reverse-Proxy importiert haben.</span><span class="sxs-lookup"><span data-stu-id="54279-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="54279-167">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54279-167">Click **OK**.</span></span> <span data-ttu-id="54279-168">Klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="54279-168">Then, click **Close**.</span></span> <span data-ttu-id="54279-169">Das Zertifikat ist nun an den Reverse-Proxy für Secure Socket Layer (SSL) und Transport Layer Security (TLS) gebunden.</span><span class="sxs-lookup"><span data-stu-id="54279-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54279-170">Wenn beim Schließen der Bindungen Dialogfelder, die Zwischenzertifikate fehlen, eine Warnung angezeigt wird, müssen Sie das Zertifikat der öffentlichen Zertifizierungsstelle für die Stammzertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate suchen und importieren.</span><span class="sxs-lookup"><span data-stu-id="54279-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="54279-171">Lesen Sie die Anweisungen in der öffentlichen Zertifizierungsstelle, von der Sie Ihr Zertifikat angefordert haben, und folgen Sie den Anweisungen zum Anfordern und Importieren einer Zertifikatkette.</span><span class="sxs-lookup"><span data-stu-id="54279-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="54279-172">Wenn Sie das Zertifikat von Ihrem Edge-Server exportiert haben, können Sie das Stammzertifizierungsstellenzertifikat und alle dem Edgeserver zugeordneten Zwischenzertifizierungsstellen Zertifikate exportieren.</span><span class="sxs-lookup"><span data-stu-id="54279-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="54279-173">Importieren Sie das Zertifikat der Stammzertifizierungsstelle auf dem Computer (nicht zu verwechseln mit dem Benutzerspeicher) vertrauenswürdige Stammzertifizierungsstellen und Zwischenzertifikate in den Zwischenspeicher des Computers Zwischenzertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="54279-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="54279-174">Klicken Sie auf der linken Seite der Konsole unter dem Namen des IIS-Servers mit der rechten Maustaste auf **Server** Farmen, und klicken Sie dann auf **Serverfarm erstellen...**.</span><span class="sxs-lookup"><span data-stu-id="54279-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54279-175">Wenn der Knoten <STRONG>Server Farms</STRONG> nicht angezeigt wird, müssen Sie den Anwendungs Anforderungs Routing installieren.</span><span class="sxs-lookup"><span data-stu-id="54279-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="54279-176">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54279-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="54279-177">Geben Sie im Dialogfeld **Serverfarm erstellen** in **Serverfarm Name**den Namen (Dies kann ein Anzeigename für die Identifizierung sein) für die erste URL ein.</span><span class="sxs-lookup"><span data-stu-id="54279-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="54279-178">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="54279-178">Click **Next**.</span></span>

6.  <span data-ttu-id="54279-179">Geben Sie im Dialogfeld **Server hinzufügen** unter **Serveradresse**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der externen Webdienste auf dem Front-End-Server ein.</span><span class="sxs-lookup"><span data-stu-id="54279-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="54279-180">Die Namen, die hier zum Beispiel verwendet werden, sind dieselben, die im Planungsabschnitt für den Reverse Proxy, [Certificate Summary-Reverse Proxy in lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md), verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54279-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="54279-181">In Bezug auf die Reverse-Proxy-Planung geben wir `webext.contoso.com`den FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="54279-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="54279-182">Vergewissern Sie sich, dass das Kontrollkästchen neben **Online** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="54279-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="54279-183">Klicken Sie auf **Hinzufügen** , um den Server zum Pool von Webservern für diese Konfiguration hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="54279-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="54279-184">Lync Server verwendet Hardwarelastenausgleichs, um die Pool Director-und Front-End-Server für http-und HTTPS-Datenverkehr zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="54279-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="54279-185">Beim Hinzufügen eines Servers zur IIS arr-Server Farm wird nur ein FQDN bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="54279-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="54279-186">Der FQDN ist der Front-End-Server oder-Director in nicht gepoolten Serverkonfigurationen oder der FQDN des konfigurierten Hardware Lastenausgleichs für Server Pools.</span><span class="sxs-lookup"><span data-stu-id="54279-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="54279-187">Die einzige unterstützte Methode zum Lastenausgleich von http-und HTTPS-Datenverkehr ist die Verwendung von Hardwarelastenausgleichs.</span><span class="sxs-lookup"><span data-stu-id="54279-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="54279-188">Klicken Sie im Dialogfeld **Server hinzufügen** auf **Erweiterte Einstellungen.**...</span><span class="sxs-lookup"><span data-stu-id="54279-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="54279-189">Dadurch wird ein Dialogfeld zum Definieren des Anwendungs Anforderungs Routings für Anforderungen an den konfigurierten FQDN geöffnet.</span><span class="sxs-lookup"><span data-stu-id="54279-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="54279-190">Das Ziel besteht darin, den Port neu zu definieren, der verwendet wird, wenn die Anforderung von IIS arr verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="54279-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="54279-191">Standardmäßig muss der http-Ziel-Port als 8080 definiert werden.</span><span class="sxs-lookup"><span data-stu-id="54279-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="54279-192">Klicken Sie neben dem aktuellen **Wert von HTTPPort 80** , und setzen Sie den Wert auf **8080**.</span><span class="sxs-lookup"><span data-stu-id="54279-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="54279-193">Klicken Sie neben dem aktuellen **httpsPort 443** , und setzen Sie den Wert auf **4443**.</span><span class="sxs-lookup"><span data-stu-id="54279-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="54279-194">Belasse den **Gewichtungs** Parameter bei 100.</span><span class="sxs-lookup"><span data-stu-id="54279-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="54279-195">Falls erforderlich, können Sie die Gewichtung für eine bestimmte Regel neu definieren, sobald Sie eine Baseline-Statistik haben.</span><span class="sxs-lookup"><span data-stu-id="54279-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="54279-196">Klicken Sie auf **Fertig stellen** , um diesen Teil der Regelkonfiguration abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="54279-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="54279-197">Möglicherweise wird ein Dialogfeld zum Umschreiben von Regeln angezeigt, in dem Sie darüber informiert werden, dass IIS-Manager eine URL-umschreibungs Regel erstellen kann, um alle eingehenden Anforderungen automatisch an die Serverfarm weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="54279-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="54279-198">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="54279-198">Click **Yes**.</span></span> <span data-ttu-id="54279-199">Sie werden die Regeln manuell anpassen, aber durch Auswählen von Ja wird die ursprüngliche Konfiguration festgelegt.</span><span class="sxs-lookup"><span data-stu-id="54279-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="54279-200">Klicken Sie auf den Namen der Serverfarm, die Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="54279-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="54279-201">Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Zwischenspeicherung**.</span><span class="sxs-lookup"><span data-stu-id="54279-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="54279-202">Deaktivieren Sie den **Datenträgercache aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="54279-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="54279-203">Klicken Sie auf der rechten Seite auf über **nehmen** .</span><span class="sxs-lookup"><span data-stu-id="54279-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="54279-204">Klicken Sie auf den Namen der Serverfarm.</span><span class="sxs-lookup"><span data-stu-id="54279-204">Click the name of the server farm.</span></span> <span data-ttu-id="54279-205">Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="54279-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="54279-206">Ändern Sie auf der Seite Proxy Einstellungen den Wert für **Timeout (Sekunden)** auf einen Wert, der für Ihre Bereitstellung angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="54279-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="54279-207">Klicken Sie auf über **nehmen** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="54279-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54279-208">Der Proxy-Timeoutwert ist eine Zahl, die von der Bereitstellung bis zur Bereitstellung variieren kann.</span><span class="sxs-lookup"><span data-stu-id="54279-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="54279-209">Überwachen Sie Ihre Bereitstellung, und ändern Sie den Wert für die optimale Benutzerfreundlichkeit für Clients.</span><span class="sxs-lookup"><span data-stu-id="54279-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="54279-210">Möglicherweise können Sie den Wert so einstellen, dass er so gering wie 200 ist.</span><span class="sxs-lookup"><span data-stu-id="54279-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="54279-211">Wenn Sie lync Mobile-Clients in Ihrer Umgebung unterstützen, sollten Sie den Wert auf 960 setzen, um das Timeout von Push-Benachrichtigungen von Office 365 zu ermöglichen, die einen Timeoutwert von 900 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="54279-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="54279-212">Es ist sehr wahrscheinlich, dass Sie den Timeoutwert erhöhen müssen, um zu verhindern, dass der Client die Verbindung trennt, wenn der Wert zu gering ist, oder die Zahl verkleinern, wenn Verbindungen über den Proxy nicht getrennt werden, und löschen, nachdem der Client die Verbindung getrennt hat.</span><span class="sxs-lookup"><span data-stu-id="54279-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="54279-213">Überwachen und Base-Lining was für Ihre Umgebung normal ist, ist die einzige genaue Methode, um festzustellen, wo die richtige Einstellung für diesen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="54279-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="54279-214">Klicken Sie auf den Namen der Serverfarm.</span><span class="sxs-lookup"><span data-stu-id="54279-214">Click the name of the server farm.</span></span> <span data-ttu-id="54279-215">Doppelklicken Sie in der Ansicht IIS-Manager-Features unter **Server Farm** auf **Routing Regeln**.</span><span class="sxs-lookup"><span data-stu-id="54279-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="54279-216">Deaktivieren Sie im Dialogfeld Routingregeln unter Routing das Kontrollkästchen neben SSL-Verschiebung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="54279-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="54279-217">Wenn die Möglichkeit zum Deaktivieren des Kontrollkästchens nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **URL-umschreiben verwenden, um eingehende Anforderungen zu überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="54279-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="54279-218">Klicken Sie auf über **nehmen** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="54279-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="54279-219">Die SSL-Verschiebung durch den Reverse-Proxy wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54279-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="54279-220">Wiederholen Sie die Schritte 5-11 für jede URL, die den Reverse-Proxy durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="54279-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="54279-221">Eine gemeinsame Liste ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="54279-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="54279-222">Front-End-Server-Webdienste extern: Webext.contoso.com (bereits durch Initiale durchlaufen konfiguriert)</span><span class="sxs-lookup"><span data-stu-id="54279-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="54279-223">Director-Webdienste extern für Director: webdirext.contoso.com (optional, wenn ein Director bereitgestellt wird)</span><span class="sxs-lookup"><span data-stu-id="54279-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="54279-224">Einfache URL-Besprechung: Meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54279-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="54279-225">Einfache URL Dialin: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54279-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="54279-226">Lync-Auto Ermittlungs-URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54279-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="54279-227">Office Web Apps-Server-URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="54279-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="54279-228">Die URL für den Office Web Apps-Server verwendet eine andere httpsPort-Adresse.</span><span class="sxs-lookup"><span data-stu-id="54279-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="54279-229">In Schritt 7 definieren Sie die <STRONG>httpsPort</STRONG> als <STRONG>443</STRONG> und <STRONG>Wert von HTTPPort</STRONG> als Port <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="54279-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="54279-230">Alle anderen Konfigurationseinstellungen sind identisch.</span><span class="sxs-lookup"><span data-stu-id="54279-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="54279-231">Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers.</span><span class="sxs-lookup"><span data-stu-id="54279-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="54279-232">Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL** -Umschreibung.</span><span class="sxs-lookup"><span data-stu-id="54279-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="54279-233">Doppelklicken Sie auf URL-umschreiben, um die Konfiguration der Regeln für die URL-Umschreibung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="54279-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="54279-234">Es sollten Regeln für jede Server Farm angezeigt werden, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="54279-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="54279-235">Wenn dies nicht der Fall ist, vergewissern Sie sich, dass Sie auf den **IIS-Server** Namen direkt unter dem Knoten **Start Seite** in der Internet Information Server-Manager-Konsole geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="54279-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="54279-236">Im Dialogfeld **URL** -umschreiben unter Verwendung von Webext.contoso.com als Beispiel ist der vollständige Name der angezeigten Regel **arr\_Webext.contoso.com\_Loadbalance\_SSL**.</span><span class="sxs-lookup"><span data-stu-id="54279-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="54279-237">Doppelklicken Sie auf die Regel, um das Dialogfeld " **Eingehende Regel bearbeiten** " zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="54279-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="54279-238">Klicken Sie auf **hinzufügen...**</span><span class="sxs-lookup"><span data-stu-id="54279-238">Click **Add…**</span></span> <span data-ttu-id="54279-239">im Dialogfeld " **Bedingungen** ".</span><span class="sxs-lookup"><span data-stu-id="54279-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="54279-240">Geben **Sie** unter Bedingungs **Eingabe:** **{\_HTTP-Host}** ein.</span><span class="sxs-lookup"><span data-stu-id="54279-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="54279-241">(Während der Eingabe wird ein Dialogfeld eingeblendet, in dem Sie die Bedingung auswählen können).</span><span class="sxs-lookup"><span data-stu-id="54279-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="54279-242">Wählen Sie unter **überprüfen, ob Eingabezeichenfolge:** **die Option entspricht dem Muster**aus.</span><span class="sxs-lookup"><span data-stu-id="54279-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="54279-243">Geben **\*** Sie im **Muster Eingabetyp** an.</span><span class="sxs-lookup"><span data-stu-id="54279-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="54279-244">**Fall ignorieren** sollte ausgewählt sein.</span><span class="sxs-lookup"><span data-stu-id="54279-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="54279-245">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54279-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="54279-246">Scrollen Sie im Dialogfeld " **Eingehende Regel bearbeiten** " nach unten, um das Dialogfeld **Aktion** zu finden.</span><span class="sxs-lookup"><span data-stu-id="54279-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="54279-247">**Aktionstyp:** sollte auf **Route to Server Farm**festzulegen, **Schema:** auf **https://**, **Serverfarm:** auf die URL festzulegen, auf die diese Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="54279-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="54279-248">Für dieses Beispiel sollte dies auf **Webext.contoso.com**festzulegen sein.</span><span class="sxs-lookup"><span data-stu-id="54279-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="54279-249">**Path:** ist auf **/{R: 0}** eingestellt</span><span class="sxs-lookup"><span data-stu-id="54279-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="54279-250">Klicken Sie auf über **nehmen** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="54279-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="54279-251">Klicken Sie auf **zurück zu Regeln** , um zu den Regeln zum Umschreiben von URLs zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="54279-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="54279-252">Wiederholen Sie das in Schritt 14 definierte Verfahren für jede der definierten SSL-umschreibungs Regeln, eine pro Server Farm-URL.</span><span class="sxs-lookup"><span data-stu-id="54279-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="54279-253">Standardmäßig werden http-Regeln ebenfalls erstellt und durch die ähnliche Namensgebung für die SSL-Regeln bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="54279-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="54279-254">Für unser aktuelles Beispiel würde die HTTP-Regel den Namen <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="54279-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="54279-255">Für diese Regeln sind keine Änderungen erforderlich, und Sie können bedenkenlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="54279-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="54279-256">So ändern Sie die Eigenschaften der Web-Veröffentlichungsregel in TMG 2010</span><span class="sxs-lookup"><span data-stu-id="54279-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="54279-257">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, wählen Sie **Microsoft Forefront TMG**aus, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="54279-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="54279-258">Erweitern Sie im linken Bereich **Servername**, und klicken Sie dann auf **Firewall-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="54279-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="54279-259">Klicken Sie im Detailbereich mit der rechten Maustaste auf die Webserver-Veröffentlichungsregel, die Sie im vorherigen Verfahren erstellt haben (beispielsweise LyncServerExternalRule), und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="54279-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="54279-260">Führen Sie auf der Seite " **Eigenschaften** " auf der Registerkarte von die folgenden Aktionen **aus** :</span><span class="sxs-lookup"><span data-stu-id="54279-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="54279-261">Klicken Sie in der Liste **diese Regel gilt für Datenverkehr aus dieser Quelle** auf **eine beliebige Stelle**, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="54279-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="54279-262">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="54279-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="54279-263">Erweitern Sie unter **Netzwerkentitäten hinzufügen**den Knoten **Netzwerke**, klicken Sie auf **extern**, klicken Sie auf **Hinzufügen**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="54279-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="54279-264">Stellen Sie auf der Registerkarte **an** sicher, dass das Kontrollkästchen **ursprünglicher Host-Header weiterleiten anstelle des eigentlichen** Kontrollkästchens aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="54279-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="54279-265">Aktivieren Sie auf der Registerkarte **Bridging** das Kontrollkästchen **Anforderung an SSL-Port umleiten** , und geben Sie dann Port **4443**an.</span><span class="sxs-lookup"><span data-stu-id="54279-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="54279-266">Fügen Sie auf der Registerkarte **Öffentlicher Name** die einfachen URLs hinzu (beispielsweise Meet.contoso.com und dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="54279-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="54279-267">Klicken Sie auf über **nehmen** , um die Änderungen zu speichern, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54279-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="54279-268">Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="54279-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="54279-269">So ändern Sie die Eigenschaften der Webveröffentlichungsregel in IIS Arr</span><span class="sxs-lookup"><span data-stu-id="54279-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="54279-270">Klicken Sie auf **Start**, wählen Sie **Programme**aus, wählen Sie **Verwaltung**aus, und klicken Sie dann auf **Internet Informationsdienste (IIS)-Manager**.</span><span class="sxs-lookup"><span data-stu-id="54279-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="54279-271">Klicken Sie auf der linken Seite der Konsole auf den Namen des IIS-Servers.</span><span class="sxs-lookup"><span data-stu-id="54279-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="54279-272">Suchen Sie in der Mitte der Konsole unter **IIS**nach **URL** -Umschreibung.</span><span class="sxs-lookup"><span data-stu-id="54279-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="54279-273">Doppelklicken Sie auf URL-umschreiben, um die Konfiguration der Regeln für die URL-Umschreibung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="54279-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="54279-274">Doppelklicken Sie auf die Regel, die Sie ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="54279-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="54279-275">Nehmen Sie die gewünschten Änderungen in **Übereinstimmung mit URL**, **Bedingungen**, **Server Variablen** oder **Aktion**vor.</span><span class="sxs-lookup"><span data-stu-id="54279-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="54279-276">Klicken Sie auf über **nehmen** , um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="54279-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="54279-277">Klicken Sie auf **zurück zu Regeln** , um andere Regeln zu ändern, oder schließen Sie die **IIS-Manager-** Konsole, wenn Sie die Änderungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="54279-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

