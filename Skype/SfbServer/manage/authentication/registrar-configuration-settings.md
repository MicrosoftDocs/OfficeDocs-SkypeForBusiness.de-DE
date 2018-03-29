---
title: Verwalten der Konfigurationseinstellungen für die Registrierungsstelle in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Zusammenfassung: Verwalten von registrierungskonfigurationseinstellungen für Skype für Business Server 2015.'
ms.openlocfilehash: 5cdcf1cba045f5105b1f375fbcebb22b7b00a25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="f7ff5-103">Verwalten der Konfigurationseinstellungen für die Registrierungsstelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7ff5-103">Manage Registrar configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7ff5-104">**Zusammenfassung:** Verwalten von registrierungskonfigurationseinstellungen für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f7ff5-p101">Mithilfe der Registrierungsstelle können Sie Proxyserver-Authentifizierungsmethoden konfigurieren. Das angegebene Authentifizierungsprotokoll legt fest, welche Art von Authentifizierungsaufforderungen die Server im Pool an die Clients senden. Die folgenden Protokolle sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="f7ff5-108">**Kerberos** Dies ist die sicherste Authentifizierungsschema für Clients verfügbar, aber es ist normalerweise nur für Enterprise-Clients verfügbar, da es Clientverbindung, um ein Schlüsselverteilungscenter (Domänencontroller Kerberos) erfordert.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="f7ff5-109">Diese Einstellung ist geeignet, wenn der Server nur Enterprise Clients authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="f7ff5-110">**NTLM** Dies ist die Authentifizierung von Clients, die auf das Kennwort ein Hashingschema NTLM-verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="f7ff5-111">Für Clients ohne Verbindung mit einem Schlüsselverteilungscenter (Kerberos-Domänencontroller), beispielsweise für Remotebenutzer, steht nur diese Form der Authentifizierung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="f7ff5-112">Wenn ein Server ausschließlich Remotebenutzer authentifiziert, sollten Sie NTLM auswählen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="f7ff5-113">**Zertifikatauthentifizierung** Dies ist die neue Authentifizierungsmethode, wenn der Server benötigt, um Zertifikate von Lync Phone Edition-Clients, Telefone in öffentlichen Bereichen, Skype für Unternehmen und die Lync Windows Store-app beziehen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="f7ff5-114">Klicken Sie auf Lync Phone Edition-Clients, nachdem ein Benutzer anmeldet und wird durch die Bereitstellung einer Persönliche Identifikationsnummer (PIN), den Skype für Business Server 2015 erfolgreich authentifiziert dann Vorschriften, die den SIP-URI an das Telefon und stellt einen Skype für Business Server signiert Zertifikat oder ein Benutzer, die Joe identifiziert (Ex: SN=joe@contoso.com) auf dem Telefon.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server 2015 then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="f7ff5-115">Dieses Zertifikat wird für die Authentifizierung beim Registrierungsdienst und den Webdiensten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7ff5-p105">Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="f7ff5-120">Wenn Sie Lync Windows Store-app-Clients verwenden möchten, müssen Sie die Zertifikatauthentifizierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="f7ff5-121">So erstellen Sie neue Konfigurationseinstellungen für eine Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="f7ff5-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="f7ff5-122">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="f7ff5-123">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f7ff5-124">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="f7ff5-125">Klicken Sie auf der Seite **Registrierungsstelle** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="f7ff5-126">Klicken Sie unter **Dienst auswählen** auf den Dienst, auf den die Registrierungsstelle angewendet werden soll, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="f7ff5-127">Wählen Sie im Abschnitt **Neue Registrierungsstelleneinstellung** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="f7ff5-128">**Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="f7ff5-129">**NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="f7ff5-130">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="f7ff5-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="f7ff5-132">Ändern von vorhandenen Registrierungsstellenkonfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7ff5-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="f7ff5-133">Mithilfe der Registrierungsstelle können Sie Protokolle für die Proxyserverauthentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="f7ff5-134">Informationen zu den verfügbaren Protokolle finden Sie unter [Verwalten von registrierungskonfigurationseinstellungen in Skype für Business Server 2015](registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f7ff5-134">For information about the available protocols, see [Manage Registrar configuration settings in Skype for Business Server 2015](registrar-configuration-settings.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7ff5-p107">Es wird empfohlen, sowohl Kerberos als auch NTLM zu aktivieren, wenn ein Server die Authentifizierung von Remote- und Unternehmensclients unterstützt. Durch eine Kommunikation des Edgeservers mit den internen Servern wird gewährleistet, dass Remoteclients nur die NTLM-Authentifizierung verwenden können. Wenn auf diesen Servern nur Kerberos verwendet wird, ist eine Authentifizierung von Remotebenutzern nicht möglich. Wenn Unternehmensbenutzer sich ebenfalls über den Server authentifizieren, wird Kerberos verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-p107">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="f7ff5-139">Führen Sie die folgenden Schritte aus, um eine vorhandene Registrierungsstelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-139">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="f7ff5-140">So ändern Sie vorhandene Registrierungsstellenkonfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7ff5-140">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="f7ff5-141">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="f7ff5-142">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f7ff5-143">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-143">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="f7ff5-144">Klicken Sie auf der Seite **Registrierungsstelle** auf einen Dienst, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-144">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f7ff5-145">Wählen Sie im Abschnitt **Registrierungsstelleneinstellung bearbeiten** je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-145">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="f7ff5-146">**Kerberos-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe der Kerberos-Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-146">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="f7ff5-147">**NTLM-Authentifizierung aktivieren**: Die Server im Pool stellen Authentifizierungsaufforderungen mithilfe von NTLM aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-147">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="f7ff5-148">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-148">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="f7ff5-149">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-149">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="f7ff5-150">So löschen Sie Registrierungsstellenkonfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7ff5-150">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="f7ff5-151">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-151">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="f7ff5-152">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-152">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f7ff5-153">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-153">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="f7ff5-154">Geben Sie auf der Seite **Registrierungsstelle** in das Suchfeld den vollständigen oder teilweisen Namen der Registrierungsstelle ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-154">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="f7ff5-155">Klicken Sie in der Liste auf die gewünschte Registrierungsstelle, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-155">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="f7ff5-156">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-156">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f7ff5-157">Entfernen der Registrierungskonfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f7ff5-157">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f7ff5-158">Sie können die registrierungskonfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet " **Remove-CsProxyConfiguration** " löschen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-158">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="f7ff5-159">Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-159">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f7ff5-160">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f7ff5-160">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f7ff5-161">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-161">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="f7ff5-162">So entfernen Sie eine bestimmte Gruppe mit Registrierungsstellensicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7ff5-162">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="f7ff5-163">Mithilfe des folgenden Befehls werden die auf den Edgeserver „atl-edge-011.litwareinc.com“ angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-163">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="f7ff5-164">So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die auf den Standortbereich angewendet werden</span><span class="sxs-lookup"><span data-stu-id="f7ff5-164">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="f7ff5-165">Mithilfe des folgenden Befehls werden alle auf den Registrierungsstellendienst angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-165">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="f7ff5-166">So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die die NTLM-Authentifizierung zulassen</span><span class="sxs-lookup"><span data-stu-id="f7ff5-166">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="f7ff5-167">Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierungsstelle gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-167">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="f7ff5-168">Weitere Informationen hierzu finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f7ff5-168">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

