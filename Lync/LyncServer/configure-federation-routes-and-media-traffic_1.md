---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728175"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="e5e53-102">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="e5e53-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="e5e53-103">Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="e5e53-104">Nachdem Sie die Migration zu Ihrem lync Server 2013-Pilot Pool durchgeführt haben, müssen Sie von der Verbund Route Ihrer Microsoft Office Communications Server 2007 R2-Edgeserver zur Föderations Route ihrer lync Server 2013-Edgeserver wechseln.</span><span class="sxs-lookup"><span data-stu-id="e5e53-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="e5e53-105">Führen Sie die folgenden Verfahren aus, um die Föderations Route und die Medien Verkehrsroute von Ihrem Office Communications Server 2007 R2-Edgeserver und-Director auf Ihren lync Server 2013-Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzustellen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="e5e53-106">Für das Ändern der Route für die Verbund Route und den Mediendatenverkehr müssen Sie Wartungs Ausfälle für die Edgeserver lync Server 2013 und Office Communications Server 2007 R2 planen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="e5e53-107">Dieser gesamte Übergangsprozess bedeutet auch, dass der Verbundzugriff für die Dauer des Ausfalls nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e5e53-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="e5e53-108">Sie sollten die Downtime für eine Zeit planen, wenn Sie eine minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="e5e53-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="e5e53-109">Darüber hinaus sollten Sie den Endbenutzern eine ausreichende Benachrichtigung senden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="e5e53-110">Planen Sie für diesen Ausfall entsprechend, und setzen Sie in Ihrer Organisation angemessene Erwartungen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="e5e53-111">Wenn Ihr Legacy Office Communications Server 2007 R2-Edgeserver so konfiguriert ist, dass derselbe FQDN für den Access-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst verwendet wird, werden die Verfahren in diesem Abschnitt zum Übergang der Verbund Einstellung zu einem lync Server 2013-Edgeserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5e53-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="e5e53-112">Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von Office Communications Server 2007 R2 auf lync Server 2013 migrieren und dann den Office Communications Server 2007 R2-Edgeserver außer Betrieb setzen, bevor Sie die Föderation aktivieren. der lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e5e53-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="e5e53-113">Ausführliche Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e5e53-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e5e53-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Verschieben der verbleibenden Benutzer zu Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="e5e53-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="e5e53-115">"Entfernen von Servern und Serverrollen" unter<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="e5e53-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="e5e53-116">Wenn Ihr XMPP-Verbund über einen lync Server 2013-Edgeserver weitergeleitet wird, können Legacy Office Communications Server 2007 R2-Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013, XMPP-Richtlinien und Es wurden Zertifikate konfiguriert, der XMPP-Verbundpartner wurde auf lync Server 2013 konfiguriert, und zuletzt wurden die DNS-Einträge aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e5e53-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="e5e53-117">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="e5e53-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="e5e53-118">Es ist auch möglich, die richtigen Benutzerrechte und Berechtigungen für das Hinzufügen von Serverrollen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="e5e53-119">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e5e53-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="e5e53-120">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5e53-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="e5e53-121">So entfernen Sie die Legacy Verbund Zuordnung von lync Server 2013-Websites</span><span class="sxs-lookup"><span data-stu-id="e5e53-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="e5e53-122">Öffnen Sie die Topologie des pilotpools mithilfe des Topologie-Generators.</span><span class="sxs-lookup"><span data-stu-id="e5e53-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="e5e53-123">Navigieren Sie im linken Bereich zum Websiteknoten.</span><span class="sxs-lookup"><span data-stu-id="e5e53-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="e5e53-124">Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="e5e53-125">Wählen Sie im linken Bereich die Option **Föderations Route** aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="e5e53-126">Deaktivieren Sie Unterwebsite Verbund-Routenzuordnung das Kontrollkästchen neben **SIP-Verbund aktivieren** , um die Föderations Route über die **BackCompatSite**zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="e5e53-127">![Dialogfeld ' Eigenschaften bearbeiten ', Verbund Route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', Verbund Route")</span><span class="sxs-lookup"><span data-stu-id="e5e53-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="e5e53-128">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="e5e53-129">Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem obersten Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="e5e53-130">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="e5e53-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="e5e53-131">So konfigurieren Sie den Legacy-Edgeserver als nicht-Föderations-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e5e53-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="e5e53-132">Klicken Sie im Menü " **Aktion** " auf der Seite " **Topologie-Generator**" auf **Office Communications Server 2007 R2-Topologie zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="e5e53-133">Klicken Sie auf **Weiter**, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="e5e53-134">Wählen Sie auf der **Seite Edge-Setup angeben**den **internen FQDN des Edge-Servers** aus, der derzeit für den Verbund konfiguriert ist, und klicken Sie dann auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="e5e53-135">![Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups")</span><span class="sxs-lookup"><span data-stu-id="e5e53-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="e5e53-136">Klicken Sie auf **weiter** , und übernehmen Sie die Standardeinstellungen, bis Sie zur Seite **externen Edge angeben** gelangen:</span><span class="sxs-lookup"><span data-stu-id="e5e53-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="e5e53-137">![Topologie-Generator, Seite ' externe Kante angeben '](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topologie-Generator, Seite ' externe Kante angeben '")</span><span class="sxs-lookup"><span data-stu-id="e5e53-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="e5e53-138">Deaktivieren Sie im Feld **externen Rand angeben**das Kontrollkästchen **dieser Edge-Pool wird für Verbund-und öffentliche Chat Verbindungen verwendet** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="e5e53-139">Dadurch wird die Verbund Zuordnung mit dem BackCompatSite entfernt.</span><span class="sxs-lookup"><span data-stu-id="e5e53-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5e53-140">Dieser Schritt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="e5e53-140">This step is important.</span></span> <span data-ttu-id="e5e53-141">Sie müssen diese Option deaktivieren, um die Legacy Federation Association zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="e5e53-142">Klicken Sie auf **weiter** , und übernehmen Sie die Standardeinstellungen der restlichen Seiten des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e5e53-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="e5e53-143">Klicken Sie in **Zusammenfassung**auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="e5e53-144">Überprüfen Sie in der Spalte **Status** , ob der Wert **erfolgreich**ist, und klicken Sie dann auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="e5e53-145">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="e5e53-146">Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="e5e53-147">![Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird")</span><span class="sxs-lookup"><span data-stu-id="e5e53-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="e5e53-148">Wie in der vorherigen Abbildung zu sehen ist, ist der **SIP-Verbund** , der sich unter **Website Verbund-Routenzuordnung** befindet, auf **deaktiviert**festgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e5e53-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="e5e53-149">So konfigurieren Sie Zertifikate auf dem lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e5e53-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e5e53-150">Exportieren Sie das Proxy Zertifikat für den externen Zugriff mit dem privaten Schlüssel aus dem Legacy Office Communications Server 2007 R2 Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="e5e53-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="e5e53-151">Importieren Sie auf dem lync Server 2013-Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="e5e53-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="e5e53-152">Weisen Sie das externe Zertifikat des Zugriffsproxys zur externen lync Server 2013-Schnittstelle des Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="e5e53-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="e5e53-153">Das interne Schnittstellen Zertifikat des lync Server 2013-Edge-Servers sollte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="e5e53-154">So ändern Sie die Office Communications Server 2007 R2-Verbund Route zur Verwendung des lync Server 2013 Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="e5e53-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e5e53-155">Öffnen Sie auf dem Office Communications Server 2007 R2 Standard Edition-Server oder-Front-End-Server das Office Communications Server 2007 R2-Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="e5e53-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="e5e53-156">Erweitern Sie im linken Bereich den obersten Knoten, und klicken Sie dann mit der rechten Maustaste auf den Knoten **Gesamtstruktur** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="e5e53-157">Wählen Sie **Eigenschaften**aus, und klicken Sie dann auf **globale Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="e5e53-158">Klicken Sie auf die Registerkarte **Föderation** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="e5e53-159">Aktivieren Sie das Kontrollkästchen, um Verbund-und öffentliche Chat Verbindungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="e5e53-160">Geben Sie den FQDN des lync Server 2013-Edge-Servers ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="e5e53-161">![Globale OCS-Eigenschaften, Registerkarte "Föderation"](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Globale OCS-Eigenschaften, Registerkarte "Föderation"")</span><span class="sxs-lookup"><span data-stu-id="e5e53-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="e5e53-162">So aktivieren Sie den lync Server 2013-Edgeserver-Verbund</span><span class="sxs-lookup"><span data-stu-id="e5e53-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="e5e53-163">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten lync Server 2013- **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="e5e53-164">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e5e53-165">Der Verbund kann nur für einen einzelnen Edge-Pool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="e5e53-166">Wenn Sie über mehrere Edge-Pools verfügen, wählen Sie eine aus, die Sie als Föderations-Edge-Pool verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e5e53-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="e5e53-167">Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="e5e53-168">![Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren")</span><span class="sxs-lookup"><span data-stu-id="e5e53-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="e5e53-169">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="e5e53-170">Navigieren Sie als nächstes zum Websiteknoten.</span><span class="sxs-lookup"><span data-stu-id="e5e53-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="e5e53-171">Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="e5e53-172">Klicken Sie im linken Bereich auf **Föderations Route**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="e5e53-173">Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann in der Liste den Eintrag lync Server 2013 Edge Server aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="e5e53-174">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="e5e53-175">![Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Bearbeiten von Eigenschaften, allgemein, Verknüpfen des Edge-Pools")</span><span class="sxs-lookup"><span data-stu-id="e5e53-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="e5e53-176">Führen Sie für die Bereitstellung mehrerer Websites dieses Verfahren an jedem Standort aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="e5e53-177">So konfigurieren Sie den ausgehenden Medienpfad von lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e5e53-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="e5e53-178">Navigieren Sie im **Topologie-Generator**zum lync Server 2013-Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="e5e53-179">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e5e53-180">Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** .</span><span class="sxs-lookup"><span data-stu-id="e5e53-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="e5e53-181">Wählen Sie im Dropdownfeld den lync Server 2013-Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="e5e53-182">![Dialogfeld ' Eigenschaften bearbeiten ', Verknüpfung des Edge-Pools](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Dialogfeld ' Eigenschaften bearbeiten ', Verknüpfung des Edge-Pools")</span><span class="sxs-lookup"><span data-stu-id="e5e53-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="e5e53-183">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="e5e53-184">So veröffentlichen Sie Änderungen an Edge-Server-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="e5e53-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="e5e53-185">Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem obersten Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="e5e53-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="e5e53-186">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="e5e53-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="e5e53-187">Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="e5e53-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e5e53-188">Möglicherweise wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e5e53-188">You may see the following message:</span></span><BR><span data-ttu-id="e5e53-189"><STRONG>Warnung: die Topologie enthält mehr als einen Federated-Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet. Überprüfen Sie, ob der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Verbund-Edgeserver bereitstellen möchten, um gleichzeitig aktiv zu sein (also kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Office Communications Server 2007 R2 oder lync Server verwenden. Überprüfen Sie, ob der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.</STRONG></span><span class="sxs-lookup"><span data-stu-id="e5e53-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="e5e53-190">Diese Warnung wird erwartet und kann bedenkenlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="e5e53-191">So überprüfen Sie den Verbund und den Remotezugriff für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="e5e53-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="e5e53-192">Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e5e53-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e5e53-193">Wenn Sie den Status von Föderation und RAS überprüfen möchten, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5e53-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="e5e53-194">Um Föderation und RAS zu aktivieren, geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e5e53-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="e5e53-195">Weitere Informationen zu diesen Cmdlets finden Sie unter den folgenden Themen: [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) und [csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="e5e53-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="e5e53-196">Warten Sie, bis die Replikation abgeschlossen ist, bevor Sie die lync Server 2013-Edgeserver online schalten und den Verbund und externen Zugriff testen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="e5e53-197">So konfigurieren Sie den lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e5e53-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e5e53-198">Bringen Sie alle lync Server 2013-Edgeserver online.</span><span class="sxs-lookup"><span data-stu-id="e5e53-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="e5e53-199">Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwarelastenausgleich, um SIP-Datenverkehr für externen Zugriff (normalerweise Port 443) und Föderation (in der Regel Port 5061) an den lync Server 2013-Edgeserver anstelle des Legacy-Edgeserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e5e53-200">Wenn Sie nicht über ein Hardware-Lastenausgleichsmodul verfügen, müssen Sie den DNS-a-Eintrag für Federation aktualisieren, um den neuen lync Server Access-Edgeserver zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e5e53-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="e5e53-201">Um dies bei minimaler Unterbrechung zu erreichen, verringern Sie den TTL-Wert für den externen lync Server Access-Edge-FQDN, sodass beim Aktualisieren von DNS auf den neuen lync Server Access-Edgeserver die Föderation und der Remotezugriff schnell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="e5e53-202">Beenden Sie als nächstes den **lync Server Access-Edge** von jedem Edgeserver-Computer.</span><span class="sxs-lookup"><span data-stu-id="e5e53-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="e5e53-203">Öffnen Sie auf jedem Legacy-Edgeserver-Computer das Applet **Dienste** in den **Verwaltungs Tools**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="e5e53-204">Suchen Sie in der Liste Dienste nach **Office Communications Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="e5e53-205">Klicken Sie mit der rechten Maustaste auf den Namen der Dienste, und wählen Sie dann **Beenden** aus, um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e5e53-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="e5e53-206">Setzen Sie den Starttyp auf **disabled**.</span><span class="sxs-lookup"><span data-stu-id="e5e53-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="e5e53-207">Klicken Sie auf **OK** , um das **Eigenschaften** Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5e53-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="e5e53-208">So testen Sie die Konnektivität externer Benutzer und des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="e5e53-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="e5e53-209">Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer in lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e5e53-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e5e53-210">Testen Sie Instant Messaging (im), Anwesenheitsinformationen, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="e5e53-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="e5e53-211">Benutzer jedes öffentlichen Chat Dienstanbieters, die von Ihrer Organisation unterstützt werden (und für die Bereitstellung abgeschlossen wurde), die mit einem Benutzer in lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2 kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e5e53-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="e5e53-212">Überprüfen Sie, ob anonyme Benutzer an Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e5e53-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="e5e53-213">Ein Benutzer, der auf Office Communications Server 2007 R2 mithilfe des Remotebenutzerzugriffs (Anmelden bei Office Communications Server 2007 R2 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="e5e53-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e5e53-214">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="e5e53-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="e5e53-215">Ein Benutzer, der auf lync Server 2013 mithilfe des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="e5e53-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e5e53-216">Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="e5e53-216">Test IM, presence, A/V, and desktop sharing.</span></span>

