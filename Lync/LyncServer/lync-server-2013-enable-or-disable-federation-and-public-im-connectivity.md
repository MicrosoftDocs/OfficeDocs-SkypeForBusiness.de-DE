---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad7e1ecce7c292b4022f15075635a5473417db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="d285e-102">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d285e-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d285e-103">_**Letztes Änderungsstand des Themas:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="d285e-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="d285e-104">Die Unterstützung für einen Partnerverbund ist erforderlich, um Benutzern mit einem Konto in einer vertrauenswürdigen Kunden- oder Partnerorganisation – Partnerdomänen und Benutzer eines unterstützten öffentlichen Sofortnachrichtenanbieters eingeschlossen – die Zusammenarbeit mit Benutzern in Ihrer Organisation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d285e-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="d285e-105">Der Partnerverbund ist auch erforderlich, um einen gehosteten Exchange-Dienstanbieter zu verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, z. B. Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d285e-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="d285e-106">Wenn Sie eine Vertrauensstellung mit diesen externen Domänen hergestellt haben, können Sie Benutzer in diesen Domänen autorisieren, um auf Ihre Bereitstellung zuzugreifen und an lync Server Kommunikation teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d285e-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="d285e-107">Diese Vertrauensstellung wird Partnerverbund genannt, und es besteht weder ein Zusammenhang mit noch eine Abhängigkeit von einer Active Directory-Vertrauensstellung.</span><span class="sxs-lookup"><span data-stu-id="d285e-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="d285e-p102">Zur Unterstützung des Benutzerzugriffs auf Partnerdomänen müssen Sie den Partnerverbund aktivieren. Wenn Sie den Partnerverbund für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="d285e-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="d285e-110">**Partnerdomänen Erkennung**   aktivieren Wenn Sie diese Option aktivieren, verwendet lync Server Domain Name System (DNS) Datensätze, um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zugelassenen Domänen aufgeführt sind, und den eingehenden Datenverkehr von ermittelten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf der Vertrauensebene, dem Umfang des Datenverkehrs und den Administratoreinstellungen einschränken oder blockieren</span><span class="sxs-lookup"><span data-stu-id="d285e-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="d285e-111">Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d285e-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="d285e-112">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen die Zugriffs-Edgedienst in der Verbunddomäne aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d285e-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="d285e-113">Ausführliche Informationen zum Steuern des Zugriffs durch Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="d285e-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="d285e-114">**Senden eines Haftungsausschlusses an Verbundpartner**     Haftungsausschluss Hinweis wird an Verbundpartner gesendet, dass die Archivierung in Ihrer Bereitstellung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d285e-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="d285e-115">Wenn Sie die Archivierung der externen Kommunikation mit Verbundpartnerdomänen unterstützen, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten in Kenntnis zu setzen.</span><span class="sxs-lookup"><span data-stu-id="d285e-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="d285e-p105">Wenn Sie den Zugriff durch Benutzer von Partnerdomänen zu einem späteren Zeitpunkt temporär oder dauerhaft unterbinden möchten, können Sie den Partnerverbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Partnerbenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren und um die geeigneten Partnerverbundoptionen festzulegen, die für Ihre Organisation unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d285e-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d285e-118">Das Aktivieren des partnerverbunds für Ihre Organisation gibt nur an, dass Ihre Server mit dem Zugriffs-Edgedienst Routing an Verbunddomänen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d285e-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="d285e-119">Benutzer in Verbunddomänen können erst an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d285e-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="d285e-120">Benutzer von öffentlichen Instant Messaging-Dienstanbietern können erst dann an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d285e-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="d285e-121">Lync Server können einen gehosteten Exchange-Dienst nicht verwenden, um Mailboxansage, Outlook Voice Access (einschließlich Voicemail) oder automatische Telefonzentralendienste für Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine Richtlinie für gehostete Voicemail konfigurieren , die Routinginformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d285e-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="d285e-122">Ausführliche Informationen zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d285e-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="d285e-123">Wenn Sie außerdem die Kommunikation mit Benutzern von Chat Dienstanbietern unterstützen möchten, müssen Sie Richtlinien zur Unterstützung dieser Dienste konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="d285e-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="d285e-124">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d285e-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="d285e-125">Ausführliche Informationen zum Erstellen einer Richtlinie für gehostete Voicemail finden Sie unter <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage Hosted Voice Mail Policies in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d285e-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="d285e-126">So aktivieren oder deaktivieren Sie den Partnerbenutzerzugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d285e-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="d285e-127">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d285e-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d285e-128">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d285e-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d285e-129">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d285e-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d285e-130">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="d285e-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="d285e-131">Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d285e-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d285e-132">Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d285e-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="d285e-133">Aktivieren Sie das Kontrollkästchen **Zugriff durch Remotebenutzer aktivieren**, um den Zugriff durch Remotebenutzer für Ihre Organisation zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="d285e-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="d285e-134">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Partnerbenutzerzugriff für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d285e-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="d285e-135">Führen Sie nach Aktivierung des Kontrollkästchens **Kommunikation mit Partnerbenutzern aktivieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d285e-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="d285e-136">Aktivieren Sie das Kontrollkästchen **Suche von Partnerdomänen aktivieren**, um die automatische Suche von Partnerdomänen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d285e-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="d285e-137">Wenn Ihre Organisation die Archivierung der externen Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden**.</span><span class="sxs-lookup"><span data-stu-id="d285e-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="d285e-138">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d285e-138">Click **Commit**.</span></span>

<span data-ttu-id="d285e-139">Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Verbundbenutzer Zugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d285e-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="d285e-140">Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d285e-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="d285e-141">Informationen zum Steuern des Zugriffs auf bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d285e-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d285e-142">Aktivieren oder Deaktivieren von Verbund-und öffentlichen Instant Messaging-Verbindungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d285e-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d285e-143">Verbund-und öffentliche Instant Messaging-Verbindungen können auch mit Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d285e-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d285e-144">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d285e-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d285e-145">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="d285e-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="d285e-146">So aktivieren Sie Partnerverbund und Verbindungen mit öffentlichen Chat Diensten</span><span class="sxs-lookup"><span data-stu-id="d285e-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="d285e-147">Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "True" ($True) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d285e-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="d285e-148">So deaktivieren Sie Verbund-und öffentliche Instant Messaging-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d285e-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="d285e-149">Legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "False" ($False) fest, um den Partnerverbund und die Verbindung mit öffentlichen Sofortnachrichtendiensten zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="d285e-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

