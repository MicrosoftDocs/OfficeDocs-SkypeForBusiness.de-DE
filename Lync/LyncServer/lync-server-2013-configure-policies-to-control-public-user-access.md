---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a967f186d924a199b007ceba8390bf968253ec72
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520412"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="4d3d8-102">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d3d8-102">Configure policies to control public user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d3d8-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="4d3d8-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="4d3d8-104">Die Verbindung mit öffentlichen Instant Messaging-Verbindungen ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Sofortnachrichten-Dienstanbietern bereitgestellt werden, einschließlich des Windows Live-Netzwerks für Internet Dienste, Yahoo \! und AOL.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="4d3d8-105">Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob öffentliche Benutzer mit internen lync Server Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="4d3d8-106">Die Verbindung mit öffentlichen Instant Messaging-Diensten ist ein zusätzliches Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="4d3d8-107">Es hängt auch von der Einrichtung des Diensts beim öffentlichen Instant Messaging-Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="4d3d8-108">Informationen zum Bereitstellen der Bereitstellung für die Verwendung der öffentlichen Anbieter finden Sie im Leitfaden "Public im Connectivity Provisioning Guide for Microsoft lync Server, Office Communications Server und Live Communications Server". [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="4d3d8-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4d3d8-109">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4d3d8-110">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4d3d8-111">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="4d3d8-112">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4d3d8-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4d3d8-113">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-113">has been announced.</span></span> <span data-ttu-id="4d3d8-114">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="4d3d8-115">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4d3d8-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-116">Messenger.</span></span> <span data-ttu-id="4d3d8-117">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="4d3d8-118">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4d3d8-119">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4d3d8-120">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4d3d8-121">Verwenden Sie den folgenden Link, um auf die Microsoft lync Server-Website für die Konnektivität mit öffentlichen Instant Messaging-Diensten zuzugreifen: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="4d3d8-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="4d3d8-122">Zum Steuern des Zugriffs durch öffentliche Benutzer können Sie Richtlinien auf globaler Ebene und Standort- und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="4d3d8-123">Ausführliche Informationen zu den Typen von Richtlinien, die Sie konfigurieren können, finden Sie unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in der Bereitstellungsdokumentation oder in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="4d3d8-124">Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="4d3d8-125">Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="4d3d8-126">Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="4d3d8-p106">Im Fall von Sofortnachrichten-Einladungen hängt die Antwort von der Clientsoftware ab. Die Anforderung wird akzeptiert, sofern externe Absender nicht ausdrücklich durch eine vom Benutzer konfigurierte Regel (also Einstellungen in der **Zulassungs-** und **Blockierliste** des Benutzers) blockiert werden. Darüber hinaus können Sofortnachrichten-Einladungen blockiert werden, wenn ein Benutzer festlegt, dass alle Sofortnachrichten von Benutzern, die nicht in der **Zulassungsliste** enthalten sind, blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-p106">In the case of IM invitations, the response depends on the client software. The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists). Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d3d8-130">Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch öffentliche Benutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="4d3d8-131">Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="4d3d8-132">Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="4d3d8-133">Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="4d3d8-134">Ausführliche Informationen zum Angeben von öffentlichen Benutzern, die sich bei lync Server anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="4d3d8-135">Gehen Sie folgendermaßen vor, um eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Sofortnachrichtenanbieter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="4d3d8-136">So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch öffentliche Benutzer</span><span class="sxs-lookup"><span data-stu-id="4d3d8-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="4d3d8-137">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d3d8-138">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d3d8-139">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d8-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d3d8-140">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4d3d8-141">Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4d3d8-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4d3d8-142">Um die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="4d3d8-p109">Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="4d3d8-p110">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnablePublicUsers** für eine Benutzerrichtlinie, welche die Kommunikation für öffentliche Benutzer ermöglicht).</span><span class="sxs-lookup"><span data-stu-id="4d3d8-p110">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="4d3d8-147">Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4d3d8-148">(Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="4d3d8-149">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4d3d8-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="4d3d8-150">Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="4d3d8-151">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="4d3d8-152">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-152">Click **Commit**.</span></span>

<span data-ttu-id="4d3d8-153">Um den Zugriff durch öffentliche Benutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="4d3d8-154">Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d8-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="4d3d8-155">Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die mit öffentlichen Benutzern zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="4d3d8-156">Ausführliche Informationen finden Sie unter [Zuweisen von benutzerspezifischen Richtlinien in lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d8-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d3d8-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d3d8-157">See Also</span></span>


[<span data-ttu-id="4d3d8-158">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d3d8-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="4d3d8-159">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d3d8-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

