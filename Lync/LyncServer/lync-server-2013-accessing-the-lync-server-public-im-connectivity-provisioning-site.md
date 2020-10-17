---
title: Zugreifen auf die lync Server-Website für die Konnektivität mit öffentlichen Instant Messaging-Diensten
description: Zugreifen auf die lync Server-Website für die Konnektivität mit öffentlichen Instant Messaging-Diensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571131"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="1fad2-103">Zugreifen auf die lync Server-Website für die Konnektivität von öffentlichen Instant Messaging-Diensten von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fad2-103">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fad2-104">_**Letztes Änderungsstand des Themas:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="1fad2-104">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="1fad2-105">Der Bereitstellung-Prozess für Lync-Skype Konnektivität wurde im Vergleich zu früheren PIC-Bereitstellung Methoden geändert.</span><span class="sxs-lookup"><span data-stu-id="1fad2-105">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="1fad2-106">Dieser Bereitstellung Vorgang kann bis zu dreißig Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="1fad2-106">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="1fad2-107">Es wird empfohlen, dass Sie zuerst diesen Prozess starten, bevor Sie die restlichen Schritte in diesem Dokument abschließen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-107">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="1fad2-108">Nachdem der Lync-Skype Bereitstellung für Ihr Konto abgeschlossen wurde, wird das Konto aktiviert, und die berechtigten Benutzer sind für die Verbindung mit öffentlichen Chat Diensten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1fad2-108">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="1fad2-109">Um Lync-Skype Konnektivität anbieten zu können, benötigen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="1fad2-109">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="1fad2-110">Microsoft-Vertragsnummer</span><span class="sxs-lookup"><span data-stu-id="1fad2-110">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="1fad2-111">Zugriffs-Edgedienst vollqualifizierter Domänenname (FQDN)</span><span class="sxs-lookup"><span data-stu-id="1fad2-111">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="1fad2-112">SIP (Session Initiation Protocol)-Domäne (n)</span><span class="sxs-lookup"><span data-stu-id="1fad2-112">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="1fad2-113">Alle zusätzlichen Zugriffs-Edgedienst FQDNs</span><span class="sxs-lookup"><span data-stu-id="1fad2-113">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="1fad2-114">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="1fad2-114">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1fad2-115">Ab April 2019 werden wir die Erfassung und Aufbewahrung von Kontaktinformationen für Kunden beenden, die über die PIC.lync.com-Website für Skype Federation vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="1fad2-115">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="1fad2-116">Diese Änderung wird vorgenommen, um sicherzustellen, dass das PIC.lync.com-Bereitstellung System den Microsoft-Datenschutzrichtlinien entspricht.</span><span class="sxs-lookup"><span data-stu-id="1fad2-116">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="1fad2-117">Sobald diese Änderung aktiv ist, können wir keine e-Mail-Updates mehr für ausstehende Bereitstellung Änderungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-117">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="1fad2-118">PIC-prodie Änderungen werden normalerweise innerhalb von 24-48 Stunden nach der Eingabe abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-118">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="1fad2-119">Wenn Sie noch immer Probleme mit dem Skype-Verbund haben 48 Stunden nach dem Einreichen einer proprovisionierung, wenden Sie sich an den technischen Support von Microsoft, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1fad2-119">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fad2-120">Im Rahmen dieser Änderung werden alle zuvor eingegebenen Kontaktinformationen bis Ende April 2019 aus unserem System gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1fad2-120">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="1fad2-121">So initiieren Sie den Bereitstellung-Prozess für Lync-Skype Konnektivität:</span><span class="sxs-lookup"><span data-stu-id="1fad2-121">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="1fad2-122">Melden Sie sich mit <strong>https://pic.lync.com</strong> Ihrer Microsoft Windows Live ID bei der Website an.</span><span class="sxs-lookup"><span data-stu-id="1fad2-122">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="1fad2-123">Wählen Sie den Typ Microsoft-Lizenzvertrag aus.</span><span class="sxs-lookup"><span data-stu-id="1fad2-123">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="1fad2-124">Aktivieren Sie das Kontrollkästchen, um sicherzustellen, dass Sie die Produktnutzungsrechte für lync Server gelesen und akzeptiert haben.</span><span class="sxs-lookup"><span data-stu-id="1fad2-124">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="1fad2-125">Klicken Sie auf der Seite zum <strong>Initiieren einer proaktivierungs Anforderung</strong> auf den entsprechenden Link, um eine Anforderung für die Weiterleitung zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="1fad2-125">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="1fad2-126">Geben Sie auf der Seite <strong>Informationen zur Datenangabe angeben</strong> den <strong>Zugriffs-Edgedienst FQDN</strong>ein.</span><span class="sxs-lookup"><span data-stu-id="1fad2-126">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="1fad2-127">Beispiel: <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="1fad2-127">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="1fad2-128">Nach dem 1. Juli 2017 Microsoft außerdem, dass Kunden den Verbund-DNS-SRV-Eintrag für öffentliche Chat Verbindungen bereitstellen müssen, damit Sie weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1fad2-128">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="1fad2-129">Geben Sie mindestens einen SIP-Domänennamen ein, und klicken Sie dann auf <strong>Hinzufügen</strong>.</span><span class="sxs-lookup"><span data-stu-id="1fad2-129">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="1fad2-130">Mindestens ein Zugriffs-Edgeserver und eine SIP-Domäne sind erforderlich, um den Bereitstellung-Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-130">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="1fad2-131">Die SIP-Domäne und der Zugriffs-Edgeserver müssen aktiv, funktionsfähig und im Netzwerk erreichbar sein.</span><span class="sxs-lookup"><span data-stu-id="1fad2-131">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="1fad2-132">Wählen Sie in der Liste der <strong>öffentlichen Sofortnachrichten-Dienstanbieter</strong> <strong>Skype aus,</strong> und klicken Sie auf <strong>weiter</strong> , um Kontaktinformationen hinzuzufügen, und senden Sie die Anforderung für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="1fad2-132">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1fad2-133">Nachdem die Übermittlungsanforderung übermittelt wurde, kann es bis zu 30 Tage dauern, bis das Konto aktiviert ist und Benutzer für die Verbindung mit öffentlichen Chat Diensten aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="1fad2-133">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="1fad2-134">Aktivieren von Verbund-und Public Chat-Konnektivität (PIC)</span><span class="sxs-lookup"><span data-stu-id="1fad2-134">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="1fad2-135">Nachdem Sie die Bereitstellung angefordert haben, können Sie sich auf die lync Server Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren Lync-Skype Konnektivität erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1fad2-135">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="1fad2-136">In diesem Abschnitt wird davon ausgegangen, dass der lync Server Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="1fad2-136">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="1fad2-137">Weitere Informationen zum Konfigurieren des externen Zugriffs für lync Server finden Sie unter "Planen des Zugriffs durch externe Benutzer" unter [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) und "Bereitstellen des Zugriffs auf externe Benutzer" unter [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .</span><span class="sxs-lookup"><span data-stu-id="1fad2-137">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="1fad2-138">Um die lync Server Umgebung für Lync-Skype Konnektivität vorzubereiten, muss der lync Server Administrator die folgenden drei Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="1fad2-138">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="1fad2-139">1\.</span><span class="sxs-lookup"><span data-stu-id="1fad2-139">1\.</span></span> <span data-ttu-id="1fad2-140">Konfigurieren von Partnerverbund und PIC</span><span class="sxs-lookup"><span data-stu-id="1fad2-140">Configure Federation and PIC</span></span>

<span data-ttu-id="1fad2-141">Partnerverbund ist erforderlich, damit Skype-Benutzer mit lync-Benutzern in Ihrer Organisation kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="1fad2-141">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="1fad2-142">Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre lync-Benutzer mit Skype-Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="1fad2-142">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="1fad2-143">Partnerverbund und PIC werden mithilfe der lync Server-Systemsteuerung, unten dargestellt, konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1fad2-143">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1fad2-144">PIC Federation wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1fad2-144">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="1fad2-145">Die unterstützten Plattformen für den PIC-Verbund umfassen lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1fad2-145">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="1fad2-146">2\.</span><span class="sxs-lookup"><span data-stu-id="1fad2-146">2\.</span></span> <span data-ttu-id="1fad2-147">Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer</span><span class="sxs-lookup"><span data-stu-id="1fad2-147">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="1fad2-148">Mit dem lync Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1fad2-148">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="1fad2-149">3\.</span><span class="sxs-lookup"><span data-stu-id="1fad2-149">3\.</span></span> <span data-ttu-id="1fad2-150">Konfigurieren der Skype PIC-Anbieter Einstellung für lync</span><span class="sxs-lookup"><span data-stu-id="1fad2-150">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="1fad2-151">Mit dem lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1fad2-151">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1fad2-152">Benutzer von PIC-Dienstanbietern (Public Instant Messaging Connectivity) können nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1fad2-152">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="1fad2-153">Informationen zum Konfigurieren von Partnerverbund und PIC finden Sie unter "aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .</span><span class="sxs-lookup"><span data-stu-id="1fad2-153">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="1fad2-154">Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer finden Sie unter "configure Policies to Control Public User Access" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .</span><span class="sxs-lookup"><span data-stu-id="1fad2-154">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="1fad2-155">Öffnen Sie in einer lync Server Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1fad2-155">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1fad2-156">Führen Sie die folgenden zwei Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="1fad2-156">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="1fad2-157">Wenn in Ihrer Umgebung noch kein PIC-Anbieter vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-157">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="1fad2-158">In lync Server 2013 CU5 &amp; lync-Desktop-Client in Office 2013 SP1 hinzugefügt, verbessern NameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "dekorieren", um diese zu identifizieren und an Skype weiterzuleiten (das Format: User (contoso. com) @MSN. com).</span><span class="sxs-lookup"><span data-stu-id="1fad2-158">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="1fad2-159">Diese neuen Einstellungen ermöglichen die automatische Formatierung der Adresse des Benutzers eingeben im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (die auf MSN.com festgelegt werden sollte), wenn Sie nicht die Domänen im NameDecorationExcludedDomainList enthält (wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-159">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="1fad2-160">Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie Ihr Microsoft-Konto angeben.</span><span class="sxs-lookup"><span data-stu-id="1fad2-160">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="1fad2-161">Darüber hinaus kann ein Skype-Benutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="1fad2-161">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="1fad2-162">Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="1fad2-162">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="1fad2-163">Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [using Lync-Skype Connectivity in lync Server 2013 as a End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="1fad2-163">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="1fad2-164">Ausführliche Informationen zum Ändern gehosteter Anbieter finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern" unter [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="1fad2-164">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="1fad2-165">Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1fad2-165">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="1fad2-166">Sie sind nun für Lync-Skype Konnektivität eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="1fad2-166">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="1fad2-167">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1fad2-167">Additional Resources</span></span>

[<span data-ttu-id="1fad2-168">Verwenden Lync-Skype Konnektivität in lync Server 2013 als Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="1fad2-168">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="1fad2-169">Leitfaden zur Anleitung zur Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fad2-169">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

