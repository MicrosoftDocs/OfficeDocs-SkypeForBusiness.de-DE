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
ms.openlocfilehash: 55ca35ace807c5e8e551295f3d395e85d514b901
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="c617d-102">Verwalten von Richtlinien für den externen Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c617d-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c617d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c617d-104">Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Zugriffs aktivieren, die für Ihre Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c617d-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="c617d-p101">In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c617d-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="c617d-109">**Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie die Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c617d-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="c617d-110">Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c617d-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="c617d-111">Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c617d-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="c617d-112">Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="c617d-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="c617d-113">Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="c617d-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="c617d-114">Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c617d-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="c617d-115">**Standortrichtlinie**   Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch externe Benutzer auf bestimmte Websites einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="c617d-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="c617d-116">Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort.</span><span class="sxs-lookup"><span data-stu-id="c617d-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="c617d-117">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c617d-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="c617d-118">Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="c617d-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="c617d-119">**Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="c617d-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="c617d-120">Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c617d-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="c617d-121">Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c617d-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="c617d-122">Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.</span><span class="sxs-lookup"><span data-stu-id="c617d-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c617d-123">Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c617d-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c617d-124">Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="c617d-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c617d-125">Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="c617d-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="c617d-126">Diese Optionen umfassen folgende Arten des externen Zugriffs:</span><span class="sxs-lookup"><span data-stu-id="c617d-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="c617d-127">**Aktivieren der Kommunikation mit Verbundbenutzern**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Verbundpartner Domänen unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="c617d-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="c617d-128">Mit dieser Einstellung wird die Möglichkeit für Benutzer konfiguriert, mit anderen SIP-Verbunddomänen zu kommunizieren, sowie gehostete Anbieter wie Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c617d-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="c617d-129">Wenn Sie diese Einstellung auswählen, können Sie die Option zum Zulassen der Kommunikation mit XMPP-Verbunddomänen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c617d-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="c617d-p107">Sie können die Option **Kommunikation mit XMPP-Verbundpartnern aktivieren** auswählen, wenn Sie zuvor die Option **Kommunikation mit Partnerbenutzern aktivieren** ausgewählt haben. XMPP-Verbünde sind Verbünde mit Organisationen, die das Extensible Messaging and Presence Protocol (XMPP) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c617d-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c617d-132">Wenn Sie den XMPP-Partnerverbund aktivieren, müssen Sie auch im Abschnitt Edge-Pools-Konfiguration des Topologie-Generators die Option zum Bereitstellen des <STRONG>XMPP-Verbunds</STRONG> auswählen.</span><span class="sxs-lookup"><span data-stu-id="c617d-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="c617d-133">Bei der Konfiguration für XMPP Federation wird ein XMPP-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c617d-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="c617d-134">**Kommunikation mit Remotebenutzern**   aktivieren aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die sich auf Reisen befinden, eine Verbindung mit lync Server über das Internet herstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="c617d-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="c617d-135">**Kommunikation mit öffentlichen Benutzern**   aktivieren aktivieren Sie diese Option, wenn Sie möchten, dass interne Benutzer mit öffentlichen Chat Dienstanbieter-Kontakten kommunizieren können, beispielsweise die von Windows Live\!, Yahoo und America Online (AOL) bereitgestellten.</span><span class="sxs-lookup"><span data-stu-id="c617d-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="c617d-136">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c617d-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c617d-137">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c617d-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c617d-138">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="c617d-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="c617d-139">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c617d-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c617d-140">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="c617d-140">has been announced.</span></span> <span data-ttu-id="c617d-141">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c617d-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c617d-142">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c617d-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c617d-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="c617d-143">Messenger.</span></span> <span data-ttu-id="c617d-144">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c617d-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c617d-145">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="c617d-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c617d-146">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c617d-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c617d-147">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="c617d-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="c617d-148">Neben dem Aktivieren der Unterstützung für den externen Benutzerzugriff müssen Sie auch Richtlinien konfigurieren, um die Verwendung des externen Benutzerzugriffs in Ihrer Organisation zu steuern, bevor den Benutzern ein beliebiger Typ des externen Benutzerzugriffs zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="c617d-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="c617d-149">Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c617d-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c617d-150">**So zeigen Sie Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**</span><span class="sxs-lookup"><span data-stu-id="c617d-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="c617d-151">Sie können Richtlinien für den externen Zugriff anzeigen, indem Sie lync Server-Verwaltungsshell und das Cmdlet **Get-CsExternalAccessPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="c617d-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="c617d-152">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="c617d-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c617d-153">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c617d-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="c617d-154">Um Informationen zu allen ihren Richtlinien für den externen Zugriff anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="c617d-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="c617d-155">Mit diesem Befehl werden Informationen nach folgendem Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c617d-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="c617d-156">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c617d-156">In This Section</span></span>

  - [<span data-ttu-id="c617d-157">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="c617d-158">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundbenutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="c617d-159">Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="c617d-160">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="c617d-161">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="c617d-162">Zurücksetzen oder Löschen von Richtlinien für den externen Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c617d-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

