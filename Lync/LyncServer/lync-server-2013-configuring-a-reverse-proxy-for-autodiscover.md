---
title: 'Lync Server 2013: Konfigurieren eines Reverse-Proxys für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 568e96b999a74ec621f8c7386f24e83d3848721c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="6e100-102">Konfigurieren eines Reverse-Proxys für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e100-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e100-103">_**Letztes Änderungsstand des Themas:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="6e100-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="6e100-104">Für die AutoErmittlung und die Unterstützung von Clients, die die AutoErmittlung verwenden, ist es erforderlich, eine vorhandene Webveröffentlichungsregel zu ändern oder eine neue Webveröffentlichungsregel für den Reverseproxy zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e100-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="6e100-105">Die Änderung oder Erstellung einer neuen Veröffentlichungsregel hängt nicht von der Entscheidung ab, die Listen alternativer Antragstellernamen in den Reverse-Proxy Zertifikaten zu aktualisieren oder nicht zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6e100-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="6e100-106">Wenn Sie HTTPS für die anfängliche lync Server 2013 AutoErmittlungs-Dienstanforderungen verwenden und die Listen alternativer Antragstellernamen in den Reverse-Proxy Zertifikaten aktualisieren, müssen Sie das aktualisierte öffentliche Zertifikat dem Secure Sockets Layer (SSL) Listener auf zuweisen. Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="6e100-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="6e100-107">Das erforderliche Update für das externe (öffentliche) Zertifikat enthält den Eintrag Subject Alternative Name (San) für lyncdiscover. \<Domänenname\>.</span><span class="sxs-lookup"><span data-stu-id="6e100-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="6e100-108">Anschließend müssen Sie den vorhandenen Listener für die externen Webdienste ändern oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen, beispielsweise **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="6e100-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="6e100-109">Wenn Sie noch nicht über eine Webveröffentlichungsregel für die externe lync Server 2013 Webdienste-URL für Ihre Front-End-Pool und Directorpool (wenn Sie Directors bereitgestellt haben), müssen Sie auch eine Regel dafür veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6e100-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e100-110">Die Veröffentlichungsregel und der Listener für Reverseproxys können sowohl für die externen Webdienste als auch für den AutoErmittlungsdienst gelten, solange das dem Listener zugewiesene Zertifikat jeweils den erforderlichen Antragstellernamen und den alternativen Antragstellernamen für beides enthält.</span><span class="sxs-lookup"><span data-stu-id="6e100-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="6e100-111">Ausführliche Informationen zur Standardkonfiguration der Weblistener-und Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="6e100-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="6e100-112">Wenn Sie HTTP für die anfänglichen AutoErmittlungsdienst-Anforderungen verwenden möchten, damit die alternativen Antragstellernamen für den Reverseproxy nicht aktualisiert werden müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e100-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="6e100-113">Die Vorgehensweisen in diesem Abschnitt beschreiben, wie die neuen Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellt oder bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="6e100-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e100-p104">Bei diesen Vorgehensweisen wird vorausgesetzt, dass die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert ist. Wenn Sie einen anderen Reverseproxy verwenden, sind die Vorgänge ähnlich, müssen jedoch der Dokumentation für das Drittanbieterprodukt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6e100-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="6e100-116">So erstellen Sie eine Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL</span><span class="sxs-lookup"><span data-stu-id="6e100-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="6e100-117">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="6e100-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6e100-118">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="6e100-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="6e100-119">Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "LyncErmittlungURL").</span><span class="sxs-lookup"><span data-stu-id="6e100-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="6e100-120">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="6e100-121">Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="6e100-122">Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="6e100-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="6e100-123">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Directorpool ein (beispielsweise lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6e100-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="6e100-124">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN des Front-End-Pool ein (beispielsweise lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6e100-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="6e100-125">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im **Pfad (optional)** als Pfad zu dem zu veröffentlichenden Ordner ein, und wählen Sie dann **den ursprünglichen Hostheader weiterleiten**aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="6e100-126">Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6e100-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="6e100-127">Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="6e100-128">Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL).</span><span class="sxs-lookup"><span data-stu-id="6e100-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="6e100-129">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN für die externe Webdienste auf dem Front-End-Pool ein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6e100-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="6e100-130">Geben \*\*\*\* Sie im Pfad \*\* / \*\*den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="6e100-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="6e100-131">Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** den vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="6e100-132">Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients**.</span><span class="sxs-lookup"><span data-stu-id="6e100-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="6e100-133">Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="6e100-134">Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6e100-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="6e100-135">Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e100-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="6e100-136">Führen Sie auf der Registerkarte **An** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6e100-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="6e100-137">Wählen Sie **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="6e100-138">Wählen Sie **Ursprung der Anforderungen scheint der Forefront TMG-Computer zu sein** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="6e100-139">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6e100-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="6e100-140">Wählen Sie **Webserver** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="6e100-141">Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.</span><span class="sxs-lookup"><span data-stu-id="6e100-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="6e100-142">Wählen Sie **Anforderungen an SSL-Port umleiten** aus, und geben Sie als Portnummer **4443** ein.</span><span class="sxs-lookup"><span data-stu-id="6e100-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="6e100-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e100-143">Click **OK**.</span></span>

18. <span data-ttu-id="6e100-144">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6e100-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="6e100-145">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6e100-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="6e100-146">So bearbeiten Sie eine bestehende Webveröffentlichungsregel zum Hinzufügen des externen AutoErmittlungsdienst-SAN und der -URL</span><span class="sxs-lookup"><span data-stu-id="6e100-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="6e100-147">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="6e100-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e100-148">Sie müssen die Bearbeitung für jede Veröffentlichungsregel und jeden Listener wiederholen.</span><span class="sxs-lookup"><span data-stu-id="6e100-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="6e100-149">Normalerweise ist dies eine Regel und ein Listener für die Front-End-Pools und eine für die optionalen Directors-oder Director-Pools, sofern Sie sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e100-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="6e100-p108">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, und klicken Sie auf die entsprechende Regel. Klicken Sie auf der Registerkarte **Aufgaben** auf **Ausgewählte Regel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6e100-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="6e100-152">Wählen Sie auf der Registerkarte **Öffentlicher Name** unter **Regel gilt für** den Eintrag **Anforderungen für die folgenden Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="6e100-153">Klicken Sie auf **Hinzufügen**, geben Sie den Namen des neuen AutoErmittlungs-Standorts ein (beispielsweise "lyncdiscover.contoso.com"), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e100-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="6e100-p109">Klicken Sie auf der Registerkarte **Listener** auf **Zertifikat auswählen**, und weisen Sie den hinzugefügten AutoErmittlungs-SAN-Einträgen das neue Zertifikat zu. Schließen Sie die Listener- und Webveröffentlichungs-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6e100-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="6e100-156">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6e100-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="6e100-157">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6e100-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="6e100-158">So erstellen Sie eine Webveröffentlichungsregel für Port 80</span><span class="sxs-lookup"><span data-stu-id="6e100-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="6e100-159">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="6e100-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6e100-160">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="6e100-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="6e100-161">Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "Lync AutoErmittlung (HTTP)").</span><span class="sxs-lookup"><span data-stu-id="6e100-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="6e100-162">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="6e100-163">Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="6e100-164">Wählen Sie auf der Seite **Sicherheit der Serververbindung** die Option **Nicht sichere Verbindungen verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="6e100-165">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den internen Webdienste FQDN für Ihre Front-End-Pool ein (beispielsweise lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="6e100-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="6e100-166">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader anstelle des im Feld Interner Websitename angegebenen Forwards**aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="6e100-167">Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6e100-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="6e100-168">Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="6e100-169">Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL).</span><span class="sxs-lookup"><span data-stu-id="6e100-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="6e100-170">Geben \*\*\*\* Sie im Pfad \*\* / \*\*den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="6e100-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="6e100-171">Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** einen Weblistener aus, oder erstellen Sie mit dem Assistenten für neue Weblistenerdefinition einen neuen Weblistener.</span><span class="sxs-lookup"><span data-stu-id="6e100-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="6e100-172">Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, keine direkte Authentifizierung des Clients**.</span><span class="sxs-lookup"><span data-stu-id="6e100-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="6e100-173">Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="6e100-174">Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6e100-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="6e100-175">Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e100-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="6e100-176">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6e100-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="6e100-177">Wählen Sie **Webserver** aus.</span><span class="sxs-lookup"><span data-stu-id="6e100-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="6e100-178">Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.</span><span class="sxs-lookup"><span data-stu-id="6e100-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="6e100-179">Stellen Sie sicher, dass **Anforderungen an SSL-Port umleiten** nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="6e100-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="6e100-180">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e100-180">Click **OK**.</span></span>

17. <span data-ttu-id="6e100-181">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6e100-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="6e100-182">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6e100-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="6e100-183">Stellen Sie sicher, dass die externe AutoErmittlungsdienst-URL für keine andere Webveröffentlichungsregel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e100-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e100-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e100-184">See Also</span></span>


[<span data-ttu-id="6e100-185">Einrichten von Reverse-Proxyservern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e100-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

