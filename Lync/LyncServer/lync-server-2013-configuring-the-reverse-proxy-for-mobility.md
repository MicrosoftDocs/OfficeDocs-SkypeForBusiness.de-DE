---
title: 'Lync Server 2013: Konfigurieren des Reverseproxys für Mobilität'
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
ms.openlocfilehash: 51fffae60df68a6aa2843919f95d7a00590ddd65
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="0657c-102">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0657c-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0657c-103">_**Letztes Änderungsdatum des Themas:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="0657c-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="0657c-104">Wenn Sie die automatische Ermittlung für Clients für mobile Geräte verwenden möchten, müssen Sie eine vorhandene oder eine neue Webveröffentlichungsregel für den Reverseproxy ändern, unabhängig davon, ob Sie die Listen Betreff alternativer Name auf den Reverse-Proxy Zertifikaten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0657c-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="0657c-105">Wenn Sie sich entschließen, HTTPS für anfängliche lync Server 2013-Erkennungsdienst Anforderungen zu verwenden und die Listen Betreff Alternative Namen auf den Reverse-Proxy Zertifikaten zu aktualisieren, müssen Sie das aktualisierte öffentliche Zertifikat dem Secure Sockets Layer (SSL)-Listener auf Ihr Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="0657c-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="0657c-106">Details zu den erforderlichen Einträgen für Alternativen Betreff finden Sie unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="0657c-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="0657c-107">Anschließend müssen Sie den vorhandenen Listener für die externen Webdienste ändern oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen.</span><span class="sxs-lookup"><span data-stu-id="0657c-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="0657c-108">Wenn Sie noch keine Webveröffentlichungsregel für die externe lync Server 2013-Webdienste-URL für Ihren Front-End-Pool besitzen, müssen Sie auch eine Regel dafür veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="0657c-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0657c-109">Die Reverse Proxy-Veröffentlichungsregel und der Listener können sowohl die externen Webdienste als auch den AutoErmittlungsdienst bedienen, solange das dem Listener zugewiesene Zertifikat den erforderlichen Namen und die alternativen Subjektnamen für beide enthält.</span><span class="sxs-lookup"><span data-stu-id="0657c-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="0657c-110">Details zur Standardkonfiguration der Weblistener-und Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</A> für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0657c-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="0657c-111">Wenn Sie sich entschließen, http für anfängliche AutoErmittlungsdienst Anforderungen zu verwenden, damit Sie keine alternativen Antragstellernamen für den Reverse-Proxy aktualisieren müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="0657c-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="0657c-112">Die Verfahren in diesem Abschnitt beschreiben, wie Sie die Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="0657c-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0657c-113">Bei diesen Verfahren wird davon ausgegangen, dass Sie die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="0657c-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="0657c-114">Wenn Sie einen anderen Reverseproxy verwenden, sind die Verfahren ähnlich, müssen aber der Dokumentation des Drittanbieterprodukts zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="0657c-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="0657c-115">So erstellen Sie eine Webveröffentlichungsregel für die externe Auto Ermittlungs-URL</span><span class="sxs-lookup"><span data-stu-id="0657c-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="0657c-116">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="0657c-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="0657c-117">Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="0657c-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="0657c-118">Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die neue Veröffentlichungsregel ein (beispielsweise LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="0657c-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="0657c-119">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="0657c-120">Wählen Sie auf der Seite **Veröffentlichungs** **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="0657c-121">Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **SSL verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="0657c-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="0657c-122">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihres Director-Pools ein (beispielsweise "lyncdir01. contoso. local").</span><span class="sxs-lookup"><span data-stu-id="0657c-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="0657c-123">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie die VIP-Adresse des Hardware Load Balancer (HLB) vor dem Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="0657c-124">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** unter **Pfad (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader weiterleiten**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="0657c-125">Führen Sie auf der Seite " **Details zum öffentlichen Namen** " die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0657c-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="0657c-126">Wählen Sie unter **Anforderungen annehmen für** **den folgenden Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="0657c-127">Geben Sie in **Öffentlicher Name** **lyncdiscover.** \<sipdomain\> (die URL des externen AutoErmittlungsdiensts).</span><span class="sxs-lookup"><span data-stu-id="0657c-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="0657c-128">Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Pool erstellen, geben Sie den FQDN für die externen Webdienste in Ihrem Front-End-Pool ein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0657c-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="0657c-129">Geben \*\*\*\* Sie in Pfad \*\* / \*\*den Text ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="0657c-130">Wählen Sie auf der Seite **Weblistener auswählen** im **Weblistener**Ihren vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="0657c-131">Wählen Sie auf der Seite **Authentifizierungsdelegierung** **keine Delegierung aus, aber der Client kann sich direkt authentifizieren**.</span><span class="sxs-lookup"><span data-stu-id="0657c-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="0657c-132">Wählen Sie auf der Seite **Benutzer festlegen** **alle Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="0657c-133">Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="0657c-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="0657c-134">Doppelklicken Sie in der Liste der Forefront TMG-Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0657c-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="0657c-135">Führen Sie auf der Registerkarte **an** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0657c-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="0657c-136">Wählen Sie **den ursprünglichen Hostheader anstelle des tatsächlichen weiterleiten**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="0657c-137">Select- **Anforderungen scheinen vom Forefront TMG-Computer zu stammen**.</span><span class="sxs-lookup"><span data-stu-id="0657c-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="0657c-138">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0657c-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="0657c-139">Wählen Sie **Webserver**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="0657c-140">Wählen Sie **Anforderungen an http-Port umleiten**aus, und geben Sie **8080** für die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="0657c-141">Wählen Sie **Anforderungen an SSL-Port umleiten**aus, und geben Sie **4443** für die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="0657c-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0657c-142">Click **OK**.</span></span>

18. <span data-ttu-id="0657c-143">Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0657c-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="0657c-144">Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="0657c-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="0657c-145">So ändern Sie eine vorhandene Webveröffentlichungsregel, um den externen Auto Ermittlungs-San und die URL hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="0657c-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="0657c-146">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="0657c-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0657c-147">Sie werden die Änderung für jede Veröffentlichungsregel und jeden Listener wiederholen, die Sie haben.</span><span class="sxs-lookup"><span data-stu-id="0657c-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="0657c-148">In der Regel handelt es sich um eine Regel und einen Listener für die Front-End-Pools und einen für die optionalen Directors-oder Director-Pools, wenn Sie diese bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0657c-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="0657c-149">Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, und klicken Sie auf die entsprechende Regel.</span><span class="sxs-lookup"><span data-stu-id="0657c-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="0657c-150">Klicken Sie auf der Registerkarte **Aufgaben** auf **ausgewählte Regel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0657c-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="0657c-151">Wählen Sie auf der Registerkarte **Öffentlicher Name** in **dieser Regel gilt**für **die Option Anforderungen für die folgenden Websites**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="0657c-152">Klicken Sie auf **Hinzufügen**, geben Sie den Namen der neuen Auto Ermittlungs Website ein (beispielsweise "lyncdiscover.contoso.com"), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0657c-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="0657c-153">Klicken Sie auf der Registerkarte **Listener** auf **Zertifikat auswählen** , und weisen Sie dem hinzugefügten San-Eintrag für die AutoErmittlung das neue Zertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="0657c-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="0657c-154">Schließen Sie die Listener-und Webveröffentlichungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0657c-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="0657c-155">Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0657c-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="0657c-156">Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="0657c-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="0657c-157">So erstellen Sie eine Webveröffentlichungsregel für Port 80</span><span class="sxs-lookup"><span data-stu-id="0657c-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="0657c-158">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Forefront TMG**, und klicken Sie dann auf **Forefront TMG-Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="0657c-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="0657c-159">Erweitern Sie im linken Bereich **Servername**, klicken Sie mit der rechten Maustaste auf **Firewall-Richtlinie**, zeigen Sie auf **neu**, und klicken Sie dann auf **Website Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="0657c-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="0657c-160">Geben Sie auf der Seite **Willkommen bei der neuen Webveröffentlichungsregel** einen Anzeigenamen für die neue Veröffentlichungsregel ein (beispielsweise lync AutoErmittlung (http)).</span><span class="sxs-lookup"><span data-stu-id="0657c-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="0657c-161">Wählen Sie auf der Seite **Regelaktion auswählen** die Option **zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="0657c-162">Wählen Sie auf der Seite **Veröffentlichungs** **eine einzelne Website oder ein Lastenausgleichsmodul veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="0657c-163">Wählen Sie auf der Seite **Server Verbindungssicherheit** die Option **nicht gesicherte Verbindungen verwenden aus, um eine Verbindung mit dem veröffentlichten Webserver oder der Serverfarm herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="0657c-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="0657c-164">Geben Sie auf der Seite **interne Veröffentlichungs Details** unter **interner Websitename**die VIP-Adresse des Hardware Lastenausgleichs (Hardware Load Balancer, HLB) vor dem Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="0657c-165">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** in **Path (optional)** den Pfad des zu veröffentlichenden Ordners ein, und wählen Sie dann **den ursprünglichen Hostheader anstelle des im Feld Interner Websitename angegebenen weiterleiten**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="0657c-166">Führen Sie auf der Seite " **Details zum öffentlichen Namen** " die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0657c-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="0657c-167">Wählen Sie unter **Anforderungen annehmen für** **den folgenden Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="0657c-168">Geben Sie in **Öffentlicher Name** **lyncdiscover.** \<sipdomain\> (die URL des externen AutoErmittlungsdiensts).</span><span class="sxs-lookup"><span data-stu-id="0657c-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="0657c-169">Geben \*\*\*\* Sie in Pfad \*\* / \*\*den Text ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="0657c-170">Wählen Sie auf der Seite **Weblistener auswählen** im **Weblistener**einen Weblistener aus, oder verwenden Sie den Assistenten für neue Weblistener-Definition, um eine neue zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0657c-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="0657c-171">Wählen Sie auf der Seite **Authentifizierungsdelegierung** **keine Delegierung aus, und der Client kann sich nicht direkt authentifizieren**.</span><span class="sxs-lookup"><span data-stu-id="0657c-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="0657c-172">Wählen Sie auf der Seite **Benutzer festlegen** **alle Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="0657c-173">Überprüfen Sie auf der Seite zum **Abschließen der neuen Webveröffentlichungsregel** , ob die Einstellungen für die Webveröffentlichungsregel richtig sind, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="0657c-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="0657c-174">Doppelklicken Sie in der Liste der Forefront TMG-Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0657c-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="0657c-175">Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0657c-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="0657c-176">Wählen Sie **Webserver**aus.</span><span class="sxs-lookup"><span data-stu-id="0657c-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="0657c-177">Wählen Sie **Anforderungen an http-Port umleiten**aus, und geben Sie **8080** für die Portnummer ein.</span><span class="sxs-lookup"><span data-stu-id="0657c-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="0657c-178">Vergewissern Sie sich, dass " **Anforderungen an SSL-Port umleiten** " nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0657c-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="0657c-179">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0657c-179">Click **OK**.</span></span>

17. <span data-ttu-id="0657c-180">Klicken Sie im Detailbereich auf über **nehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0657c-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="0657c-181">Klicken Sie auf **Regel testen** , um zu überprüfen, ob Ihre neue Regel ordnungsgemäß eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="0657c-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="0657c-182">Überprüfen Sie, ob die URL des externen AutoErmittlungsdiensts in einer anderen Webveröffentlichungsregel nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0657c-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0657c-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0657c-183">See Also</span></span>


[<span data-ttu-id="0657c-184">Einrichten von Reverseproxyservern für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0657c-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="0657c-185">Technische Anforderungen für die Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0657c-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

