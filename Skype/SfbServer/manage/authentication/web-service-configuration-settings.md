---
title: Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Zusammenfassung: Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: b2a7f287c9386c89d132e03e96aa25e9472f7008
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297575"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b299e-103">Verwalten von Webdienst-Konfigurationseinstellungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b299e-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b299e-104">**Zusammenfassung:** Web Service-Konfigurationseinstellungen in Skype for Business Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="b299e-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b299e-105">Sie können die **Webdienst** Seite verwenden, um die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-Webserver und-Webdienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b299e-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b299e-106">Führen Sie die folgenden Schritte aus, um eine neue Webdienstrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b299e-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="b299e-107">So erstellen Sie neue Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b299e-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="b299e-108">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="b299e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b299e-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b299e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b299e-110">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="b299e-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b299e-111">Klicken Sie auf der Seite **Webdienst** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="b299e-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="b299e-p101">Zum Konfigurieren des Webdiensts für einen Standort klicken Sie auf **Standortkonfiguration**. Klicken Sie in **Standort auswählen** auf den Standort, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b299e-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="b299e-p102">Zum Konfigurieren des Webdiensts für einen Pool klicken Sie auf **Poolkonfiguration**. Klicken Sie in **Dienst auswählen** auf den Dienst, auf den die Webdienstrichtlinie angewendet werden soll, und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b299e-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="b299e-116">Wählen Sie im Abschnitt **Neue Webdiensteinstellung** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.</span><span class="sxs-lookup"><span data-stu-id="b299e-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b299e-117">Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b299e-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b299e-118">**PIN-Authentifizierung aktivieren**: Clients werden über eine PIN authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="b299e-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b299e-119">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="b299e-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b299e-120">**Download einer Zertifikatkette aktivieren**: Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b299e-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b299e-121">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b299e-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b299e-122">Ändern von vorhandenen Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b299e-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="b299e-123">Sie können die **Webdienst** Seite verwenden, um die Authentifizierungsmethoden für den Zugriff auf Skype for Business Server-Webserver und-Webdienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b299e-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b299e-124">Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b299e-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b299e-125">So ändern Sie vorhandene Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b299e-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="b299e-126">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="b299e-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b299e-127">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b299e-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b299e-128">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="b299e-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b299e-129">Klicken Sie auf der Seite **Webdienst** auf eine Konfiguration, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="b299e-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b299e-130">Wählen Sie im Abschnitt **Webdiensteinstellung bearbeiten** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine** aus.</span><span class="sxs-lookup"><span data-stu-id="b299e-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b299e-131">Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung eine oder mehrere der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b299e-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b299e-132">**PIN-Authentifizierung aktivieren**: Clients werden über eine PIN authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="b299e-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b299e-133">**Zertifikatauthentifizierung aktivieren**: Die Server im Pool stellen Zertifikate an Clients aus.</span><span class="sxs-lookup"><span data-stu-id="b299e-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b299e-134">**Download einer Zertifikatkette aktivieren**: Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b299e-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b299e-135">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b299e-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="b299e-136">Löschen von vorhandenen Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b299e-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="b299e-137">Führen Sie die folgenden Schritte aus, um Webdienst-Konfigurationseinstellungen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b299e-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="b299e-138">So löschen Sie vorhandene Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b299e-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="b299e-139">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben. .</span><span class="sxs-lookup"><span data-stu-id="b299e-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b299e-140">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b299e-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b299e-141">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="b299e-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b299e-142">Geben Sie auf der Seite **Webdienst** in das Suchfeld den vollständigen oder teilweisen Namen der Richtlinie ein, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="b299e-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="b299e-143">Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="b299e-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="b299e-144">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b299e-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b299e-145">Löschen von Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b299e-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b299e-146">Sie können Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsWebServiceConfiguration** löschen.</span><span class="sxs-lookup"><span data-stu-id="b299e-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="b299e-147">Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b299e-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b299e-148">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b299e-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b299e-149">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="b299e-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="b299e-150">So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste</span><span class="sxs-lookup"><span data-stu-id="b299e-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="b299e-151">Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort „Redmond“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="b299e-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b299e-152">So löschen Sie alle auf den Standortbereich angewendeten Konfigurationseinstellungen für Webdienste</span><span class="sxs-lookup"><span data-stu-id="b299e-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="b299e-153">Mit dem folgenden Befehl werden alle auf den Dienstbereich angewendeten Webdienstsicherheitseinstellungen entfernt:</span><span class="sxs-lookup"><span data-stu-id="b299e-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="b299e-154">So löschen Sie alle Konfigurationseinstellungen für Webdienste, die eine Zertifikatauthentifizierung zulassen</span><span class="sxs-lookup"><span data-stu-id="b299e-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="b299e-155">Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung zulassen:</span><span class="sxs-lookup"><span data-stu-id="b299e-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="b299e-156">Ausführliche Informationen finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b299e-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

