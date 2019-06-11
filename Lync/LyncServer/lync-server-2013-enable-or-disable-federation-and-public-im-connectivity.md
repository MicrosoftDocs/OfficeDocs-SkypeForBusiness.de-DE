---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="ec432-102">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec432-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec432-103">_**Letztes Änderungsdatum des Themas:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="ec432-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="ec432-104">Die Unterstützung für die Föderation ist erforderlich, damit Benutzer, die über ein Konto bei einem vertrauenswürdigen Kunden oder einer Partnerorganisation verfügen, einschließlich Partnerdomänen und Benutzer von öffentlichen Instant Messaging (im)-Anbieter Benutzern, die Sie unterstützen, die Zusammenarbeit mit Benutzern in Ihrem Organisation.</span><span class="sxs-lookup"><span data-stu-id="ec432-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="ec432-105">Föderation muss auch einen gehosteten Exchange-Dienstanbieter verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer sich in einem gehosteten Exchange-Dienst wie Microsoft Exchange Online befinden.</span><span class="sxs-lookup"><span data-stu-id="ec432-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="ec432-106">Wenn Sie eine Vertrauensstellung mit diesen externen Domänen eingerichtet haben, können Sie Benutzer in diesen Domänen autorisieren, auf Ihre Bereitstellung zuzugreifen und an der lync Server-Kommunikation teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec432-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="ec432-107">Diese Vertrauensstellung wird als Föderation bezeichnet und ist nicht mit einer Active Directory-Vertrauensstellung verbunden oder abhängig davon.</span><span class="sxs-lookup"><span data-stu-id="ec432-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="ec432-108">Wenn Sie den Zugriff von Benutzern von Verbunddomänen unterstützen möchten, müssen Sie die Föderation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec432-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="ec432-109">Wenn Sie die Föderation für Ihre Organisation aktivieren, müssen Sie auch angeben, ob die folgenden Optionen implementiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="ec432-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="ec432-110">**Aktivieren der Partnerdomänen Erkennung**   Wenn Sie diese Option aktivieren, verwendet lync Server DNS-Einträge (Domain Name System), um zu versuchen, Domänen zu ermitteln, die nicht in der Liste der zulässigen Domänen aufgeführt sind, und automatisch eingehenden Datenverkehr von erkannten Föderationen ausgewertet Partner und begrenzen oder Blockieren des Datenverkehrs basierend auf der Vertrauensebene, dem Umfang des Datenverkehrs und den Administratoreinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ec432-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ec432-111">Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="ec432-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ec432-112">Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zulässig sein sollen, einschließlich der Beschränkung des Zugriffs auf bestimmte Server, auf denen der Access-Edgedienst in der Verbunddomäne ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec432-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ec432-113">Details zum Steuern des Zugriffs durch Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="ec432-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="ec432-114">**Senden einer Verzichtserklärung zur Archivierung an Föderationspartner**     Haftungsausschluss Hinweis wird an verbundene Partner gesendet, die die Archivierung in Ihrer Bereitstellung durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ec432-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="ec432-115">Wenn Sie die Archivierung externer Kommunikation mit Verbundpartner Domänen unterstützen, sollten Sie die Benachrichtigung über Archivierungs Verzicht aktivieren, um die Partner zu warnen, dass Ihre Nachrichten archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ec432-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="ec432-116">Wenn Sie den Zugriff von Benutzern von Verbunddomänen später vorübergehend oder dauerhaft verhindern möchten, können Sie den Verbund für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec432-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="ec432-117">Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff auf den Verbundbenutzer für Ihre Organisation zu aktivieren oder zu deaktivieren, einschließlich der Angabe der entsprechenden Verbund Optionen, die für Ihre Organisation unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec432-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec432-118">Das Aktivieren des Föderations Unternehmens für Ihre Organisation gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, Routing in Verbunddomänen unterstützen</span><span class="sxs-lookup"><span data-stu-id="ec432-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="ec432-119">Benutzer in Verbunddomänen können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung des Zugriffs von Verbundbenutzern konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="ec432-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="ec432-120">Benutzer von Anbietern öffentlicher Chat Dienste können erst dann an Chats oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie für die Unterstützung öffentlicher Chats konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="ec432-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="ec432-121">Lync Server kann einen gehosteten Exchange-Dienst nicht zum Bereitstellen von Anrufbeantwortung, Outlook Voice Access (einschließlich Voicemail) oder automatischen Telefonzentralen Diensten für Benutzer verwenden, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden, bis Sie eine gehostete Voicemail-Richtlinie konfigurieren. , in dem Routinginformationen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ec432-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="ec432-122">Details zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Verbunddomänen in anderen Organisationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec432-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="ec432-123">Wenn Sie die Kommunikation mit Benutzern von Chat Dienstanbietern unterstützen möchten, müssen Sie außerdem Richtlinien für deren Unterstützung konfigurieren und auch die Unterstützung für die einzelnen Dienstanbieter konfigurieren, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec432-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="ec432-124">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec432-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="ec432-125">Details zum Erstellen einer gehosteten Voicemail-Richtlinie finden Sie unter <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von gehosteten Voicemail-Richtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec432-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="ec432-126">So aktivieren oder deaktivieren Sie den Verbundbenutzer Zugriff für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ec432-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="ec432-127">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ec432-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ec432-128">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ec432-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ec432-129">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ec432-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ec432-130">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ec432-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="ec432-131">Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ec432-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ec432-132">Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ec432-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="ec432-133">Aktivieren Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** , um den Zugriff durch den Verbundbenutzer für Ihre Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ec432-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="ec432-134">Wenn Sie den Verbundbenutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="ec432-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="ec432-135">Wenn Sie das Kontrollkästchen **Kommunikation mit Verbundbenutzern aktivieren** aktiviert haben, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="ec432-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="ec432-136">Wenn Sie die automatische Ermittlung von Partnerdomänen unterstützen möchten, aktivieren Sie das Kontrollkästchen **Discovery-Partnerdomänen Erkennung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="ec432-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="ec432-137">Wenn Ihre Organisation die Archivierung externer Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** .</span><span class="sxs-lookup"><span data-stu-id="ec432-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="ec432-138">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ec432-138">Click **Commit**.</span></span>

<span data-ttu-id="ec432-139">Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch den Verbundbenutzer zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ec432-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="ec432-140">Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec432-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="ec432-141">Informationen zum Steuern des Zugriffs auf bestimmte Föderationsdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec432-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ec432-142">Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ec432-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ec432-143">Verbund-und öffentliche Chat Verbindungen können auch mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ec432-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="ec432-144">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec432-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ec432-145">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="ec432-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="ec432-146">So aktivieren Sie Verbund-und öffentliche Chat Verbindungen</span><span class="sxs-lookup"><span data-stu-id="ec432-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="ec432-147">Um Verbund-und öffentliche Chat Verbindungen zu aktivieren, setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf true ($true):</span><span class="sxs-lookup"><span data-stu-id="ec432-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="ec432-148">So deaktivieren Sie die Verbindung zwischen Föderation und öffentlichen Chats</span><span class="sxs-lookup"><span data-stu-id="ec432-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="ec432-149">Zum Deaktivieren der Konnektivität für Verbund-und öffentliche Chats setzen Sie den Wert der **AllowFederatedUsers** -Eigenschaft auf false ($false):</span><span class="sxs-lookup"><span data-stu-id="ec432-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

