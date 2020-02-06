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
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn Sie Richtlinien für die Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Verbunddomänen. '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818316"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="72eb0-103">Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="72eb0-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="72eb0-104">Wenn Sie Richtlinien für die Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="72eb0-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="72eb0-105">Sie können eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit Ihren Skype for Business Server-Benutzern zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="72eb0-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="72eb0-106">Zum Steuern des Zugriffs von Verbundbenutzern können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="72eb0-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="72eb0-107">Skype for Business Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="72eb0-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="72eb0-108">Die Priorität der Skype for Business Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss).</span><span class="sxs-lookup"><span data-stu-id="72eb0-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="72eb0-109">Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="72eb0-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="72eb0-110">Sie können Richtlinien zum Steuern des Zugriffs von Verbundbenutzern konfigurieren, auch wenn Sie den Verbund für Ihre Organisation nicht aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="72eb0-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="72eb0-111">Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="72eb0-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="72eb0-112">Details zum Aktivieren von Föderationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="72eb0-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="72eb0-113">Wenn Sie eine Benutzerrichtlinie zum Steuern des Zugriffs von Verbundbenutzern angeben, gilt die Richtlinie zudem nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="72eb0-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="72eb0-114">So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="72eb0-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="72eb0-115">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="72eb0-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72eb0-116">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="72eb0-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="72eb0-117">Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="72eb0-118">Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="72eb0-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="72eb0-119">Klicken Sie zum Konfigurieren der globalen Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="72eb0-120">Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="72eb0-121">Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="72eb0-122">Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="72eb0-123">Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableFederatedUsers** für eine Benutzerrichtlinie, die die Kommunikation für Verbunddomänen Benutzer aktiviert).</span><span class="sxs-lookup"><span data-stu-id="72eb0-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="72eb0-124">Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="72eb0-125">Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.</span><span class="sxs-lookup"><span data-stu-id="72eb0-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="72eb0-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="72eb0-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="72eb0-127">Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie aktivieren möchten, aktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="72eb0-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="72eb0-128">Wenn Sie den Verbundbenutzer Zugriff für die Richtlinie deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit verbundenen Benutzern aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="72eb0-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="72eb0-129">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-129">Click **Commit**.</span></span>

<span data-ttu-id="72eb0-130">Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="72eb0-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="72eb0-131">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="72eb0-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="72eb0-132">Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="72eb0-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="72eb0-133">Ausführliche Informationen finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="72eb0-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="72eb0-134">So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="72eb0-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="72eb0-135">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="72eb0-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72eb0-136">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="72eb0-137">Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72eb0-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="72eb0-138">Der Parameter "EnablePublicCloudAudioVideoAccess" hat in der Skype for Business Server-Systemsteuerung keine entsprechende Auswahl.</span><span class="sxs-lookup"><span data-stu-id="72eb0-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="72eb0-139">So erstellen Sie eine neue Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="72eb0-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="72eb0-140">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="72eb0-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72eb0-141">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="72eb0-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="72eb0-142">Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72eb0-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="72eb0-143">Ein Beispiel für das Erstellen einer neuen Website Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="72eb0-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="72eb0-144">So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zurück, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="72eb0-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="72eb0-145">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="72eb0-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72eb0-146">Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72eb0-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="72eb0-147">Ein Beispiel für das Zurücksetzen der globalen Richtlinie (für die globale Richtlinie kann nur die Einstellung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="72eb0-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="72eb0-148">Die Richtlinie kann nicht gelöscht werden):</span><span class="sxs-lookup"><span data-stu-id="72eb0-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="72eb0-149">Um eine Website Richtlinie zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72eb0-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="72eb0-150">Löscht die Website Richtlinie Redmond.</span><span class="sxs-lookup"><span data-stu-id="72eb0-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="72eb0-151">Zum Löschen einer Benutzerrichtlinie mit dem Namen UserEAPPolicy geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="72eb0-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="72eb0-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72eb0-152">See Also</span></span>


[<span data-ttu-id="72eb0-153">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="72eb0-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="72eb0-154">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="72eb0-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="72eb0-155">Verwalten von SIP-Partnerdomänen für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="72eb0-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="72eb0-156">Verwalten von SIP-Partnerverbundanbietern für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="72eb0-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="72eb0-157">Satz-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="72eb0-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="72eb0-158">Neu – CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="72eb0-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="72eb0-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="72eb0-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="72eb0-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="72eb0-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="72eb0-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="72eb0-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

