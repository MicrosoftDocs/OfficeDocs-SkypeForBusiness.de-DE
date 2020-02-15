---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Verbundbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40b2a1fa071c7dd7f93e384418679ffcead38c0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="a9339-102">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9339-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9339-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="a9339-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="a9339-104">Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen.</span><span class="sxs-lookup"><span data-stu-id="a9339-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="a9339-105">Sie können eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit ihren lync Server 2013 Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="a9339-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="a9339-106">Zum Steuern des Zugriffs durch Partnerbenutzer können Sie Richtlinien auf globaler Ebene sowie Standort- und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a9339-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="a9339-107">Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9339-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="a9339-108">Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="a9339-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="a9339-109">Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="a9339-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9339-110">Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Partnerbenutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="a9339-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="a9339-111">Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a9339-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="a9339-112">Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9339-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="a9339-113">Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch Verbundbenutzer angeben, gilt die Richtlinie nur für Benutzer, die für lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a9339-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a9339-114">So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen</span><span class="sxs-lookup"><span data-stu-id="a9339-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a9339-115">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a9339-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a9339-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a9339-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a9339-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9339-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a9339-118">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="a9339-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="a9339-119">Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a9339-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a9339-120">Um die globale Richtlinie für die Unterstützung des Zugriffs durch Partnerbenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a9339-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="a9339-p104">Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9339-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="a9339-p105">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableFederatedUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Benutzer aus Partnerdomänen ermöglicht).</span><span class="sxs-lookup"><span data-stu-id="a9339-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="a9339-125">Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a9339-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a9339-126">(Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="a9339-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="a9339-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a9339-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="a9339-128">Aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a9339-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="a9339-129">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a9339-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="a9339-130">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a9339-130">Click **Commit**.</span></span>

<span data-ttu-id="a9339-131">Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a9339-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="a9339-132">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a9339-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="a9339-133">Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="a9339-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a9339-134">Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="a9339-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a9339-135">So konfigurieren Sie eine vorhandene Richtlinie mit Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="a9339-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a9339-136">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a9339-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a9339-137">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a9339-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a9339-138">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a9339-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="a9339-139">Nachstehend finden Sie ein Beispiel für einen Befehl, mit dem die globale Richtlinie für den Zugriff durch Partnerbenutzer, der Zugriff auf die XMPP-Domäne, der Zugriff für Remotebenutzer sowie der Zugriff für öffentliche Anbieter auf "aktiviert" festgelegt und die Audio- und Videounterstützung für entsprechende öffentliche Anbieter zugelassen wird:</span><span class="sxs-lookup"><span data-stu-id="a9339-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a9339-140">Der Parameter "EnablePublicCloudAudioVideoAccess" verfügt nicht über eine entsprechende Auswahl in der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a9339-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a9339-141">So erstellen Sie eine neue Richtlinie mit Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="a9339-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a9339-142">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a9339-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a9339-143">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a9339-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a9339-144">Geben Sie im lync Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a9339-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="a9339-145">Nachstehend finden Sie ein Beispiel für das Erstellen einer neuen Standortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="a9339-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a9339-146">So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="a9339-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a9339-147">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a9339-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a9339-148">Geben Sie Folgendes in das lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="a9339-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="a9339-p108">Nachstehend finden Sie ein Beispiel für das Zurücksetzen der globalen Richtlinie (die Einstellungen der globalen Richtlinie können zwar entfernt, die Richtlinie selbst kann jedoch nicht gelöscht werden):</span><span class="sxs-lookup"><span data-stu-id="a9339-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="a9339-151">Geben Sie den folgenden Befehl ein, um eine Standortrichtlinie zu löschen:</span><span class="sxs-lookup"><span data-stu-id="a9339-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="a9339-152">Mit diesem Befehl wird die Standortrichtlinie "Redmond" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a9339-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="a9339-153">Geben Sie den folgenden Befehl ein, um die Richtlinie "UserEAPPolicy" zu löschen:</span><span class="sxs-lookup"><span data-stu-id="a9339-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9339-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9339-154">See Also</span></span>


[<span data-ttu-id="a9339-155">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9339-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="a9339-156">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9339-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="a9339-157">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9339-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="a9339-158">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9339-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="a9339-159">Gruppe-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a9339-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="a9339-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a9339-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="a9339-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a9339-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="a9339-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a9339-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="a9339-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a9339-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

