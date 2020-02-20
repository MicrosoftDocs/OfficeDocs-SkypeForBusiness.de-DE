---
title: Veröffentlichen von Office-webapps-Servern mithilfe eines Reverse-Proxyservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6964c111fa6ca7225c25884c52d02564314ececf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="bac8a-102">Veröffentlichen von Office-webapps-Servern in lync Server 2013 mithilfe eines Reverse-Proxyservers</span><span class="sxs-lookup"><span data-stu-id="bac8a-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac8a-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="bac8a-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="bac8a-104">Wenn Sie möchten, dass externe Benutzer (also Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf Office-webapps Server-PowerPoint-Präsentationen haben, müssen Sie Office-webappsserver und einen Reverse-Proxy Server wie Microsoft Forefront verwenden. Threat Management-Gateway.</span><span class="sxs-lookup"><span data-stu-id="bac8a-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="bac8a-105">Das bedeutet auch, dass Sie eine Website-Veröffentlichungsregel erstellen und konfigurieren müssen. Diese Regel hilft sicherzustellen, dass Benutzer eine Verbindung mit dem Server herstellen können.</span><span class="sxs-lookup"><span data-stu-id="bac8a-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="bac8a-106">Wenn Sie keinen Zugriff auf externe Benutzer benötigen, müssen Sie keine Website-Veröffentlichungsregel konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bac8a-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="bac8a-107">Führen Sie das folgende Verfahren aus, um in Forefront Threat Management Gateway eine Website-Veröffentlichungsregel zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="bac8a-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="bac8a-108">Klicken Sie im \*\*Startmenü \*\*auf **Alle Programme**, dann auf **Microsoft Forefront TMG** und anschließend auf **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="bac8a-109">Klicken Sie in Forefront TMG mit der rechten Maustaste auf **Firewallrichtlinie** zeigen Sie auf **Neu**, und klicken Sie dann auf **Website-Veröffentlichungsregel**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="bac8a-110">Geben Sie im Assistenten für neue Webveröffentlichungsregeln auf der **Willkommensseite** im Feld **Name der Webveröffentlichungsregel** einen Namen für Ihre neue Regel ein (z. B. **Office Web Apps-Serverregel**), und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="bac8a-111">Klicken Sie auf der Seite **Regelaktion festlegen** auf **Zulassen** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="bac8a-112">Aktivieren Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="bac8a-113">Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="bac8a-p102">Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Interner Sitename** den FQDN Ihres Office Web Apps-Servers ein (z. B. **officewebapps01.contoso.com**), und klicken Sie dann auf **Weiter**. Der im Feld **Interner Sitename** eingegebene Name muss im Betrefffeld oder dem Feld "Alternativer Antragstellername" des Zertifikats angezeigt werden, das Sie dem Office Web Apps-Server zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="bac8a-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="bac8a-116">\*\*Geben / \*\* Sie auf der Seite **interne Veröffentlichungs Details** im Feld **Pfad (optional)** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="bac8a-117">Mithilfe der\* /-Syntax wird sichergestellt, dass alle Ordner und Unterordner für die Website veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="bac8a-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="bac8a-118">Wählen Sie auf der Seite **Details des öffentlichen Namen** in der Dropdownliste **Anforderungen annehmen für** die Option **Diesen Domänennamen (unten eingeben)**, und geben Sie dann den vollqualifizierten Domänennamen für Ihren Office Web Apps-Server in das Feld "Öffentlicher Name" ein.</span><span class="sxs-lookup"><span data-stu-id="bac8a-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="bac8a-119">Dieser Name sollte der Name für den Zugriff auf Ihre Website sein.</span><span class="sxs-lookup"><span data-stu-id="bac8a-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="bac8a-120">Wenn beispielsweise über die URL http://officewebapps01.contoso.com auf Ihre Website zugegriffen wird, sollten Sie **officewebapps01.contoso.com** in das Feld **Öffentlicher Name** eingeben.</span><span class="sxs-lookup"><span data-stu-id="bac8a-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="bac8a-121">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-121">Click **Next**.</span></span>

11. <span data-ttu-id="bac8a-122">Klicken Sie auf der Seite **Weblistener auswählen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="bac8a-123">Geben Sie im Assistenten für neue Weblistenerdefinition im Feld **Weblistenername**einen Namen für den neuen Weblistener ein (z. B. **SSL**), und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="bac8a-124">Wählen Sie auf der Seite **Sicherheit der Clientverbindung** die Option **Sichere SSL-Verbindungen mit Clients erforderlich** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="bac8a-125">Wählen Sie auf der Seite **Weblistener-IP-Adressen** die Optionen **Extern** und **Intern**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="bac8a-126">Wählen Sie auf der Seite **Listener-SSL-Zertifikate** die Option **Ein einziges Zertifikat für diesen Weblistener verwenden**, und klicken Sie dann auf **Zertifikat auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="bac8a-127">Wählen Sie im Dialogfeld **Zertifikat auswählen** das Zertifikat aus, das für diesen Weblistener verwendet werden soll, und klicken Sie dann auf **Auswählen**</span><span class="sxs-lookup"><span data-stu-id="bac8a-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="bac8a-128">Klicken Sie auf der Seite **Listener-SSL-Zertifikate** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="bac8a-129">Wählen Sie auf der Seite **Authentifizierungseinstellungen** in der Dropdownliste **Legen Sie fest, wie die Clients die Anmeldeinformationen an Forefront TMG übermitteln sollen** die Option **Keine Authentifizierung** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="bac8a-130">Klicken Sie auf der Seite **Einstellungen für einmaliges Anmelden (SSO)** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="bac8a-p105">Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Zusammenfassung der Konfigurationsauswahlen, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="bac8a-133">Klicken Sie auf der Seite **Weblistener auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="bac8a-134">Wählen Sie auf der Seite **Authentifizierungsdelegierung** in der Dropdownliste **Legen Sie die Methode fest, mit der Forefront TMG sich beim veröffentlichten Webserver authentifizieren soll** die Option **Keine Delegierung, aber direkte Authentifizierung des Clients**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="bac8a-p106">Bestätigen Sie auf der Seite **Benutzersätze**, dass die richtigen Benutzersätze aufgeführt sind. Standardmäßig ist dies der Benutzersatz **Alle Benutzer**. Klicken Sie auf **Hinzufügen**, um ggf. andere Benutzersätze hinzuzufügen, die Sie definiert haben. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="bac8a-139">Klicken Sie auf der Seite **Fertigstellen des Assistenten** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="bac8a-p107">Beachten Sie, dass der Prozess nicht durch Klicken auf **Fertig stellen** abgeschlossen ist, d. h. die neue Regel wird dadurch nicht angewendet und aktiviert. Stattdessen müssen Sie auf der Forefront TMG- Benutzeroberfläche auf die Schaltfläche **Anwenden** klicken. Wenn Sie auf **Anwenden** klicken, wird das Dialogfeld **Configuration Change Description** angezeigt. Klicken Sie in diesem Dialogfeld auf **Anwenden**, um die neue Veröffentlichungsregel zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bac8a-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="bac8a-144">Nachdem die neue Regel angewendet wurde, müssen Sie einige geringfügige Änderungen an der Regel vornehmen, um sicherzustellen, dass Benutzer die neuen PowerPoint-Präsentationsfunktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bac8a-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="bac8a-145">Verwenden Sie hierzu das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="bac8a-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="bac8a-146">Klicken Sie in Forefront TMG mit der rechten Maustaste auf die neue Veröffentlichungsregel, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="bac8a-147">Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Bis** die Option **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="bac8a-148">Klicken Sie auf der Registerkarte **Verkehr** auf **Filtern** und dann auf **HTTP konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="bac8a-149">Deaktivieren Sie im Dialogfeld **HTTP-Richtlinie für diese Regel konfigurieren** das Kontrollkästchen **Normalisierung überprüfen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="bac8a-150">Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="bac8a-p109">Klicken Sie in Forefront TMG auf **Anwenden**, um die Änderungen zu übernehmen. Wenn das Dialogfeld **Configuration Change Description** angezeigt wird, klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="bac8a-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="bac8a-153">Nach Abschluss der Installation können Sie Ihren Office-webapps-Server mithilfe der Verfahren im Thema über [Prüfen der Konfiguration von Office-webapps Server in lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)testen.</span><span class="sxs-lookup"><span data-stu-id="bac8a-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

