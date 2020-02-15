---
title: 'Lync Server 2013: Konfigurieren des Reverse-Proxys für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f37da0858cde92cb28b5f7b67421a49ae77d211
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="1360e-102">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1360e-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1360e-103">_**Letztes Änderungsstand des Themas:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="1360e-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="1360e-104">Wenn Sie die AutoErmittlung für die Clients mobiler Geräte verwenden möchten, müssen Sie eine neue Webveröffentlichungsregel für den Reverseproxy erstellen oder eine vorhandene bearbeiten, ganz gleich, ob Sie die Listen der alternativen Antragstellernamen für die Reverseproxyzertifikate aktualisieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="1360e-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="1360e-105">Wenn Sie HTTPS für die anfängliche lync Server 2013 AutoErmittlungs-Dienstanforderungen verwenden und die Listen alternativer Antragstellernamen in den Reverse-Proxy Zertifikaten aktualisieren, müssen Sie das aktualisierte öffentliche Zertifikat dem Secure Sockets Layer (SSL) Listener auf zuweisen. Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="1360e-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="1360e-106">Ausführliche Informationen zu den erforderlichen Einträgen für alternative Antragstellernamen finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="1360e-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="1360e-107">Dann müssen Sie den bestehenden Listener für die externen Webdienste bearbeiten oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen.</span><span class="sxs-lookup"><span data-stu-id="1360e-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="1360e-108">Wenn Sie noch nicht über eine Webveröffentlichungsregel für die externe lync Server 2013 Webdienste-URL für Ihre Front-End-Pool verfügen, müssen Sie auch eine Regel dafür veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1360e-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1360e-109">Die Veröffentlichungsregel und der Listener für Reverseproxys können sowohl für die externen Webdienste als auch für den AutoErmittlungsdienst gelten, solange das dem Listener zugewiesene Zertifikat jeweils den erforderlichen Antragstellernamen und den alternativen Antragstellernamen für beides enthält.</span><span class="sxs-lookup"><span data-stu-id="1360e-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="1360e-110">Ausführliche Informationen zur Standardkonfiguration der Weblistener-und Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="1360e-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="1360e-111">Wenn Sie HTTP für die anfänglichen AutoErmittlungsdienst-Anforderungen verwenden möchten, damit die alternativen Antragstellernamen für den Reverseproxy nicht aktualisiert werden müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1360e-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="1360e-112">Die Vorgehensweisen in diesem Abschnitt beschreiben, wie die neuen Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellt oder bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="1360e-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1360e-p103">Bei diesen Vorgehensweisen wird vorausgesetzt, dass die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert ist. Wenn Sie einen anderen Reverseproxy verwenden, sind die Vorgänge ähnlich, müssen jedoch der Dokumentation für das Drittanbieterprodukt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1360e-p103">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="1360e-115">So erstellen Sie eine Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL</span><span class="sxs-lookup"><span data-stu-id="1360e-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="1360e-116">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1360e-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="1360e-117">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="1360e-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="1360e-118">Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "LyncErmittlungURL").</span><span class="sxs-lookup"><span data-stu-id="1360e-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="1360e-119">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="1360e-120">Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="1360e-121">Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="1360e-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="1360e-122">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Directorpool ein (beispielsweise lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="1360e-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="1360e-123">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie die VIP-Adresse des Hardware Lastenausgleichs (HLB) vor dem Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="1360e-124">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im **Pfad (optional)** als Pfad zu dem zu veröffentlichenden Ordner ein, und wählen Sie dann **den ursprünglichen Hostheader weiterleiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="1360e-125">Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1360e-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="1360e-126">Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="1360e-127">Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL).</span><span class="sxs-lookup"><span data-stu-id="1360e-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="1360e-128">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN für die externe Webdienste auf dem Front-End-Pool ein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1360e-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="1360e-129">Geben \*\*\*\* Sie im Pfad \*\* / \*\*den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="1360e-130">Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** den vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="1360e-131">Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients**.</span><span class="sxs-lookup"><span data-stu-id="1360e-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="1360e-132">Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="1360e-133">Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1360e-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="1360e-134">Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1360e-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="1360e-135">Führen Sie auf der Registerkarte **An** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1360e-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="1360e-136">Wählen Sie **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="1360e-137">Wählen Sie **Ursprung der Anforderungen scheint der Forefront TMG-Computer zu sein** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="1360e-138">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1360e-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="1360e-139">Wählen Sie **Webserver** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="1360e-140">Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="1360e-141">Wählen Sie **Anforderungen an SSL-Port umleiten** aus, und geben Sie als Portnummer **4443** ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="1360e-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1360e-142">Click **OK**.</span></span>

18. <span data-ttu-id="1360e-143">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1360e-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="1360e-144">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="1360e-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="1360e-145">So bearbeiten Sie eine bestehende Webveröffentlichungsregel zum Hinzufügen des externen AutoErmittlungsdienst-SAN und der -URL</span><span class="sxs-lookup"><span data-stu-id="1360e-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="1360e-146">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1360e-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1360e-147">Sie müssen die Bearbeitung für jede Veröffentlichungsregel und jeden Listener wiederholen.</span><span class="sxs-lookup"><span data-stu-id="1360e-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="1360e-148">Normalerweise ist dies eine Regel und ein Listener für die Front-End-Pools und eine für die optionalen Directors-oder Director-Pools, sofern Sie sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="1360e-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="1360e-p107">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, und klicken Sie auf die entsprechende Regel. Klicken Sie auf der Registerkarte **Aufgaben** auf **Ausgewählte Regel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1360e-p107">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="1360e-151">Wählen Sie auf der Registerkarte **Öffentlicher Name** unter **Regel gilt für** den Eintrag **Anforderungen für die folgenden Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="1360e-152">Klicken Sie auf **Hinzufügen**, geben Sie den Namen des neuen AutoErmittlungs-Standorts ein (beispielsweise "lyncdiscover.contoso.com"), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1360e-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="1360e-p108">Klicken Sie auf der Registerkarte **Listener** auf **Zertifikat auswählen**, und weisen Sie den hinzugefügten AutoErmittlungs-SAN-Einträgen das neue Zertifikat zu. Schließen Sie die Listener- und Webveröffentlichungs-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1360e-p108">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="1360e-155">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1360e-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="1360e-156">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="1360e-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="1360e-157">So erstellen Sie eine Webveröffentlichungsregel für Port 80</span><span class="sxs-lookup"><span data-stu-id="1360e-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="1360e-158">Klicken Sie auf **Start**, zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG**, und klicken Sie auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1360e-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="1360e-159">Erweitern Sie im linken Bereich **ServerName**, klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie**, zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="1360e-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="1360e-160">Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "Lync AutoErmittlung (HTTP)").</span><span class="sxs-lookup"><span data-stu-id="1360e-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="1360e-161">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="1360e-162">Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="1360e-163">Wählen Sie auf der Seite **Sicherheit der Serververbindung** die Option **Nicht sichere Verbindungen verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="1360e-164">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**die VIP-Adresse des Hardware Lastenausgleichs (HLB) vor dem Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="1360e-165">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader anstelle des im Feld Interner Websitename angegebenen Forwards**aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="1360e-166">Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1360e-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="1360e-167">Wählen Sie unter **Anforderungen annehmen für:** den Eintrag**Diesen Domänennamen** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="1360e-168">Geben Sie im **öffentlichen Namen** **lyncdiscover.** \<sipdomain "\> (die externe AutoErmittlungsdienst-URL).</span><span class="sxs-lookup"><span data-stu-id="1360e-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="1360e-169">Geben \*\*\*\* Sie im Pfad \*\* / \*\*den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="1360e-170">Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** einen Weblistener aus, oder erstellen Sie mit dem Assistenten für neue Weblistenerdefinition einen neuen Weblistener.</span><span class="sxs-lookup"><span data-stu-id="1360e-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="1360e-171">Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, keine direkte Authentifizierung des Clients**.</span><span class="sxs-lookup"><span data-stu-id="1360e-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="1360e-172">Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="1360e-173">Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1360e-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="1360e-174">Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1360e-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="1360e-175">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1360e-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="1360e-176">Wählen Sie **Webserver** aus.</span><span class="sxs-lookup"><span data-stu-id="1360e-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="1360e-177">Wählen Sie **Anforderungen an HTTP-Port umleiten** aus, und geben Sie als Portnummer**8080** ein.</span><span class="sxs-lookup"><span data-stu-id="1360e-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="1360e-178">Stellen Sie sicher, dass **Anforderungen an SSL-Port umleiten** nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="1360e-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="1360e-179">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1360e-179">Click **OK**.</span></span>

17. <span data-ttu-id="1360e-180">Klicken Sie im Detailbereich auf **Übernehmen**, um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1360e-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="1360e-181">Klicken Sie auf **Regel testen**, um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="1360e-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="1360e-182">Stellen Sie sicher, dass die externe AutoErmittlungsdienst-URL für keine andere Webveröffentlichungsregel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1360e-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1360e-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1360e-183">See Also</span></span>


[<span data-ttu-id="1360e-184">Einrichten von Reverse-Proxyservern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1360e-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="1360e-185">Technische Anforderungen für die Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1360e-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

