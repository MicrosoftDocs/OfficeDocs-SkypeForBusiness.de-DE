---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429d1751f9b9628df98c05112838715de2b249d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="97ba8-102">Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ba8-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ba8-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="97ba8-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="97ba8-104">Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob Remotebenutzer mit internen lync Server Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="97ba8-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="97ba8-105">Zum Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="97ba8-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="97ba8-106">Standortrichtlinien setzen die globale Richtlinie außer Kraft, und Benutzerrichtlinien setzen Standort- und globale Richtlinien außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="97ba8-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="97ba8-107">Ausführliche Informationen zu den Typen von Richtlinien, die Sie konfigurieren können, finden Sie unter [Managing Federation and External Access to lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="97ba8-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="97ba8-108">Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="97ba8-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="97ba8-109">Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="97ba8-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="97ba8-110">Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="97ba8-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97ba8-111">Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer konfigurieren, wenn Sie den Zugriff durch Remotebenutzer für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="97ba8-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="97ba8-112">Die von Ihnen konfigurierten Richtlinien treten jedoch erst in Kraft, wenn der Zugriff durch Remotebenutzer für Ihre Organisation aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="97ba8-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="97ba8-113">Ausführliche Informationen zum Aktivieren des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="97ba8-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="97ba8-114">Wenn Sie außerdem eine Benutzerrichtlinie zur Steuerung des Remotebenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="97ba8-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="97ba8-115">Ausführliche Informationen zum Angeben von Benutzern, die sich bei lync Server von Remotestandorten aus anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="97ba8-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="97ba8-116">Führen Sie die folgenden Schritte aus, um die einzelnen Richtlinien für den externen Zugriff zu konfigurieren, die zur Steuerung des Remotebenutzerzugriffs verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="97ba8-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97ba8-117">In diesem Verfahren wird beschrieben, wie Sie eine Richtlinie nur für die Kommunikation mit Remotebenutzern konfigurieren, aber jede Richtlinie, die Sie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, kann auch den Verbundbenutzer Zugriff und den Zugriff durch öffentliche Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="97ba8-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="97ba8-118">Ausführliche Informationen zum Konfigurieren von Richtlinien zur Unterstützung von Verbundbenutzern finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="97ba8-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="97ba8-119">Ausführliche Informationen zum Konfigurieren von Richtlinien zur Unterstützung öffentlicher Benutzer finden Sie unter <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="97ba8-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="97ba8-120">So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="97ba8-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="97ba8-121">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="97ba8-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97ba8-122">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="97ba8-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97ba8-123">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97ba8-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97ba8-124">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="97ba8-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="97ba8-125">Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="97ba8-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="97ba8-126">Um die globale Richtlinie für die Unterstützung des Zugriffs durch Remotebenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="97ba8-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="97ba8-p105">Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="97ba8-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="97ba8-p106">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableRemoteUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Remotebenutzer ermöglicht).</span><span class="sxs-lookup"><span data-stu-id="97ba8-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="97ba8-131">Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="97ba8-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="97ba8-132">(Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="97ba8-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="97ba8-133">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="97ba8-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="97ba8-134">Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren**, um den Zugriff durch Remotebenutzer für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="97ba8-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="97ba8-135">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren**, um den Zugriff durch Remotebenutzer für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="97ba8-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="97ba8-136">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="97ba8-136">Click **Commit**.</span></span>

<span data-ttu-id="97ba8-137">Um den Zugriff durch Remotebenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Remotebenutzerzugriff in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="97ba8-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="97ba8-138">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen im-Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="97ba8-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="97ba8-139">Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, für die Sie eine Remoteverbindung zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="97ba8-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="97ba8-140">Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="97ba8-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

