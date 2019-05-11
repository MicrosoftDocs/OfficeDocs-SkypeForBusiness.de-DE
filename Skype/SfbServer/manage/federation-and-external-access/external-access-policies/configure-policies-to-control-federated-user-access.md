---
title: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Beim Konfigurieren von Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern wenden Sie die Richtlinien für Benutzer von Partnerdomänen. '
ms.openlocfilehash: 81eced8db10c9ffd017b5b79a54980b773b300bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920658"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="23805-103">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzer in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="23805-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="23805-104">Beim Konfigurieren von Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern wenden Sie die Richtlinien für Benutzer von Partnerdomänen.</span><span class="sxs-lookup"><span data-stu-id="23805-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="23805-105">Sie können eine oder mehrere externe Benutzer Zugriffsrichtlinien zur Steuerung konfigurieren, ob Benutzer von Partnerdomänen mit Ihrer Skype für Business Server-Benutzer zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="23805-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="23805-106">Zur Steuerung des Zugriffs Verbundbenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="23805-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="23805-107">Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="23805-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="23805-108">Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen).</span><span class="sxs-lookup"><span data-stu-id="23805-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="23805-109">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="23805-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="23805-110">Auch wenn Sie nicht den Verbund für Ihre Organisation aktiviert haben, können Sie Richtlinien zum Steuern der partnerbenutzerzugriff, konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="23805-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="23805-111">Die Richtlinien, die Sie konfigurieren, werden jedoch in Kraft nur, wenn Sie den Verbund für Ihre Organisation aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="23805-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="23805-112">Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="23805-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="23805-113">Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs Verbundbenutzer angeben, gilt die Richtlinie darüber hinaus nur für Benutzer, die für Skype für Business Server aktiviert und so konfiguriert, dass die Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="23805-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="23805-114">So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen</span><span class="sxs-lookup"><span data-stu-id="23805-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="23805-115">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="23805-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23805-116">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="23805-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="23805-117">Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="23805-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="23805-118">Führen Sie auf der Seite **Richtlinie für den externen Zugriff** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="23805-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="23805-119">Um die globale Richtlinie zur Unterstützung der partnerbenutzerzugriff zu konfigurieren, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="23805-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="23805-120">Erstellen einer neuen Standortrichtlinie, klicken Sie auf **neu**, und klicken Sie dann auf **Standortrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="23805-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="23805-121">Klicken Sie im **Dialogfeld Standort auswählen**auf den geeigneten Standort aus der Liste aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="23805-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="23805-122">Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="23805-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="23805-123">Erstellen Sie in **Neue Richtlinie für den externen Zugriff**einen eindeutigen Namen im Feld **Name** , das angibt, welche Benutzer Richtlinie Hintergrund (beispielsweise **EnableFederatedUsers** für eine Benutzerrichtlinie, mit dem verbunddomäne Benutzern können).</span><span class="sxs-lookup"><span data-stu-id="23805-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="23805-124">Um eine vorhandene Richtlinie zu ändern, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="23805-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="23805-125">(Optional) Wenn Sie hinzufügen oder bearbeiten eine Beschreibung möchten, geben Sie die Informationen für die Richtlinie im Feld **Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="23805-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="23805-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="23805-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="23805-127">Um den partnerbenutzerzugriff für die Richtlinie zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="23805-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="23805-128">Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den partnerbenutzerzugriff für die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23805-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="23805-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="23805-129">Click **Commit**.</span></span>

<span data-ttu-id="23805-130">Um partnerbenutzerzugriff zu aktivieren, müssen Sie auch Unterstützung für den Verbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="23805-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="23805-131">Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des partnerverbunds und öffentlichen Instant Messaging-Diensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="23805-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="23805-132">Ist dies eine Benutzerrichtlinie, müssen Sie auch die Richtlinie für Benutzer anwenden, die für die Zusammenarbeit mit Verbundbenutzer enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="23805-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="23805-133">Weitere Informationen hierzu finden Sie unter [Zuweisen eine Richtlinie für den externen Benutzerzugriff](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="23805-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="23805-134">So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen</span><span class="sxs-lookup"><span data-stu-id="23805-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="23805-135">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="23805-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23805-136">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="23805-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="23805-137">Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="23805-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="23805-138">Der Parameter "EnablePublicCloudAudioVideoAccess" weist eine entsprechende Auswahl in der Skype Business Server-Systemsteuerung keinen</span><span class="sxs-lookup"><span data-stu-id="23805-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="23805-139">Zum Erstellen einer neuen Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen</span><span class="sxs-lookup"><span data-stu-id="23805-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="23805-140">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="23805-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23805-141">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="23805-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="23805-142">Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell:</span><span class="sxs-lookup"><span data-stu-id="23805-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="23805-143">Ein Beispiel zum Erstellen einer neuen Standortrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="23805-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="23805-144">Löschen oder Zurücksetzen eine Richtlinie mit Windows PowerShell für Zugriff durch Benutzer von Partnerdomänen zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="23805-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="23805-145">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="23805-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23805-146">Geben Sie Folgendes in die Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="23805-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="23805-147">Ein Beispiel für das Zurücksetzen der globalen Richtlinie (die globale Richtlinie kann nur müssen die Einstellung entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="23805-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="23805-148">Die Richtlinie kann nicht gelöscht werden):</span><span class="sxs-lookup"><span data-stu-id="23805-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="23805-149">Um eine Standortrichtlinie zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="23805-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="23805-150">Die Richtlinien für den Standort "Redmond" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23805-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="23805-151">Um eine Benutzerrichtlinie mit dem Namen UserEAPPolicy zu löschen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="23805-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="23805-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23805-152">See Also</span></span>


[<span data-ttu-id="23805-153">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="23805-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="23805-154">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="23805-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="23805-155">Verwalten von SIP-Partnerdomänen für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="23805-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="23805-156">Verwalten von SIP-Partnerverbundanbietern für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="23805-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="23805-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="23805-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="23805-158">Neue CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="23805-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="23805-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="23805-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="23805-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="23805-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="23805-161">GRANT-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="23805-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

