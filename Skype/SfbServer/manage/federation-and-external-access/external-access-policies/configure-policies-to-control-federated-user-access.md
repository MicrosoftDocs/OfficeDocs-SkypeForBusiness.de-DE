---
title: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Verbundbenutzer
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037405"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="9bc05-103">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9bc05-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="9bc05-104">Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen.</span><span class="sxs-lookup"><span data-stu-id="9bc05-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="9bc05-105">Sie können eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit Ihren Skype for Business Server Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="9bc05-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="9bc05-106">Zum Steuern des Zugriffs durch Partnerbenutzer können Sie Richtlinien auf globaler Ebene sowie Standort- und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9bc05-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="9bc05-107">Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bc05-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9bc05-108">Skype for Business Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="9bc05-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9bc05-109">Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="9bc05-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="9bc05-110">Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Partnerbenutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="9bc05-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="9bc05-111">Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9bc05-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="9bc05-112">Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9bc05-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="9bc05-113">Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch Verbundbenutzer angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9bc05-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9bc05-114">So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen</span><span class="sxs-lookup"><span data-stu-id="9bc05-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9bc05-115">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9bc05-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bc05-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9bc05-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="9bc05-117">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9bc05-118">Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9bc05-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9bc05-119">Um die globale Richtlinie für die Unterstützung des Zugriffs durch Partnerbenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9bc05-p103">Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="9bc05-p104">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableFederatedUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Benutzer aus Partnerdomänen ermöglicht).</span><span class="sxs-lookup"><span data-stu-id="9bc05-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="9bc05-124">Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9bc05-125">(Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="9bc05-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="9bc05-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9bc05-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="9bc05-127">Aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bc05-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="9bc05-128">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bc05-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="9bc05-129">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-129">Click **Commit**.</span></span>

<span data-ttu-id="9bc05-130">Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bc05-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="9bc05-131">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9bc05-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="9bc05-132">Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="9bc05-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="9bc05-133">Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="9bc05-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9bc05-134">So konfigurieren Sie eine vorhandene Richtlinie mit Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="9bc05-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9bc05-135">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9bc05-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bc05-136">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bc05-137">Geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9bc05-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="9bc05-138">Der Parameter "EnablePublicCloudAudioVideoAccess" verfügt nicht über eine entsprechende Auswahl in der Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="9bc05-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9bc05-139">So erstellen Sie eine neue Richtlinie mit Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="9bc05-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9bc05-140">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9bc05-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bc05-141">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9bc05-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="9bc05-142">Geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9bc05-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="9bc05-143">Nachstehend finden Sie ein Beispiel für das Erstellen einer neuen Standortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="9bc05-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="9bc05-144">So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="9bc05-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="9bc05-145">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9bc05-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9bc05-146">Geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9bc05-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="9bc05-p107">Nachstehend finden Sie ein Beispiel für das Zurücksetzen der globalen Richtlinie (die Einstellungen der globalen Richtlinie können zwar entfernt, die Richtlinie selbst kann jedoch nicht gelöscht werden):</span><span class="sxs-lookup"><span data-stu-id="9bc05-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="9bc05-149">Geben Sie den folgenden Befehl ein, um eine Standortrichtlinie zu löschen:</span><span class="sxs-lookup"><span data-stu-id="9bc05-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="9bc05-150">Mit diesem Befehl wird die Standortrichtlinie "Redmond" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9bc05-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="9bc05-151">Geben Sie den folgenden Befehl ein, um die Richtlinie "UserEAPPolicy" zu löschen:</span><span class="sxs-lookup"><span data-stu-id="9bc05-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="9bc05-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bc05-152">See Also</span></span>


[<span data-ttu-id="9bc05-153">Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen</span><span class="sxs-lookup"><span data-stu-id="9bc05-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="9bc05-154">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="9bc05-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="9bc05-155">Verwalten von SIP-Verbunddomänen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="9bc05-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="9bc05-156">Verwalten von SIP-Verbund Anbietern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="9bc05-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="9bc05-157">Gruppe-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bc05-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="9bc05-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bc05-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="9bc05-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bc05-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9bc05-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bc05-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="9bc05-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9bc05-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

