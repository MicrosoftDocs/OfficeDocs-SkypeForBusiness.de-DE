---
title: 'Lync Server 2013: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afc2b1599551cfc3b7ee7341e441946610166ba0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="7d642-102">Verwalten von Richtlinien für den externen Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d642-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="7d642-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="7d642-104">Nach der Bereitstellung eines oder mehrerer Edge-Server müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d642-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="7d642-p101">In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7d642-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="7d642-109">**Globale Richtlinie**   Die globale Richtlinie wird bei der Bereitstellung der Edgeserver erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d642-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="7d642-110">Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d642-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="7d642-111">Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7d642-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="7d642-112">Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="7d642-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="7d642-113">Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="7d642-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="7d642-114">Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7d642-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="7d642-115">**Standortrichtlinie**   Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch externe Benutzer auf bestimmte Standorte einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="7d642-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="7d642-116">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="7d642-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="7d642-117">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d642-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="7d642-118">Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="7d642-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="7d642-119">**Benutzerrichtlinie**   Die Konfiguration der Benutzerrichtlinie überschreibt die globale Richtlinie und die Standortrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="7d642-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="7d642-120">Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7d642-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="7d642-121">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7d642-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="7d642-122">Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.</span><span class="sxs-lookup"><span data-stu-id="7d642-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7d642-123">Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d642-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7d642-124">Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="7d642-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7d642-125">Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.</span><span class="sxs-lookup"><span data-stu-id="7d642-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="7d642-126">Diese Optionen umfassen die folgenden Arten des externen Zugriffs:</span><span class="sxs-lookup"><span data-stu-id="7d642-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="7d642-127">**Kommunikation mit Verbundbenutzern aktivieren**   Aktivieren Sie diese Option, wenn Sie den Benutzerzugriff auf Verbundpartnerdomänen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d642-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="7d642-128">Mit dieser Einstellung wird die Möglichkeit für Benutzer konfiguriert, mit anderen SIP-Verbunddomänen zu kommunizieren, sowie gehostete Anbieter wie Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d642-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="7d642-129">Wenn Sie diese Einstellung auswählen, können Sie die Option zum Zulassen der Kommunikation mit XMPP-Verbunddomänen auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d642-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="7d642-p107">Sie können die Option **Kommunikation mit XMPP-Verbundpartnern aktivieren** auswählen, wenn Sie zuvor die Option **Kommunikation mit Partnerbenutzern aktivieren** ausgewählt haben. XMPP-Verbünde sind Verbünde mit Organisationen, die das Extensible Messaging and Presence Protocol (XMPP) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d642-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d642-132">Wenn Sie den XMPP-Partnerverbund aktivieren, müssen Sie auch im Abschnitt Edge-Pools-Konfiguration des Topologie-Generators die Option zum Bereitstellen des <STRONG>XMPP-Verbunds</STRONG> auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d642-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="7d642-133">Bei der Konfiguration für XMPP Federation wird ein XMPP-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7d642-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="7d642-134">**Aktivieren der Kommunikation mit Remotebenutzern**     Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die sich auf Reisen befinden, eine Verbindung mit lync Server über das Internet herstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="7d642-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="7d642-135">**Aktivieren der Kommunikation mit öffentlichen Benutzern**     Aktivieren Sie diese Option, wenn interne Benutzer mit öffentlichen Chat Dienstanbieter-Kontakten kommunizieren können sollen, beispielsweise die von Windows Live, Yahoo \! und America Online (AOL) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d642-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7d642-136">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d642-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7d642-137">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7d642-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7d642-138">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="7d642-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="7d642-139">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7d642-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7d642-140">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="7d642-140">has been announced.</span></span> <span data-ttu-id="7d642-141">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d642-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7d642-142">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7d642-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7d642-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7d642-143">Messenger.</span></span> <span data-ttu-id="7d642-144">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7d642-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7d642-145">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="7d642-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7d642-146">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d642-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7d642-147">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="7d642-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="7d642-148">Neben dem Aktivieren der Unterstützung für den externen Benutzerzugriff müssen Sie auch Richtlinien konfigurieren, um die Verwendung des externen Benutzerzugriffs in Ihrer Organisation zu steuern, bevor den Benutzern ein beliebiger Typ des externen Benutzerzugriffs zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7d642-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="7d642-149">Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d642-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7d642-150">**So zeigen Sie Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**</span><span class="sxs-lookup"><span data-stu-id="7d642-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="7d642-151">Sie können Richtlinien für den externen Zugriff anzeigen, indem Sie lync Server-Verwaltungsshell und das Cmdlet **Get-CsExternalAccessPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d642-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="7d642-152">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7d642-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7d642-153">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="7d642-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="7d642-154">Um Informationen über alle Richtlinien für den externen Zugriff anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="7d642-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="7d642-155">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="7d642-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d642-156">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7d642-156">In This Section</span></span>

  - [<span data-ttu-id="7d642-157">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="7d642-158">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundbenutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="7d642-159">Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="7d642-160">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="7d642-161">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="7d642-162">Zurücksetzen oder Löschen von Richtlinien für den externen Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d642-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

