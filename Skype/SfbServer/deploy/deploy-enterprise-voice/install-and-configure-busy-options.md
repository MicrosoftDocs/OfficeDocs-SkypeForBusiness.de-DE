---
title: Installieren und Konfigurieren von beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: In diesem Artikel erfahren Sie, wie Sie beschäftigte Optionen in Skype for Business Server installieren und konfigurieren.
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604212"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="dea0d-103">Installieren und Konfigurieren von beschäftigt-Optionen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dea0d-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="dea0d-104">In diesem Artikel erfahren Sie, wie Sie beschäftigte Optionen in Skype for Business Server installieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dea0d-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="dea0d-105">Busy options ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit dem Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer sich bereits in einem Anruf oder einer Konferenz befindet oder wenn ein Anruf in die Warteschleife gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="dea0d-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="dea0d-106">Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen oder an Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="dea0d-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="dea0d-107">Wenn beschäftigt-Optionen für die Organisation aktiviert sind, können alle Benutzer im Unternehmen, sowohl Enterprise-VoIP-als auch nicht-Enterprise-VoIP-Benutzer, die folgenden Konfigurationsoptionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="dea0d-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="dea0d-108">Beschäftigt in "beschäftigt" – in dem neue eingehende Anrufe mit einem Besetztzeichen zurückgewiesen werden, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="dea0d-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="dea0d-109">Voicemail in "beschäftigt" – bei dem neue eingehende Anrufe an die Voicemail weitergeleitet werden, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="dea0d-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="dea0d-110">Unabhängig davon, wie die beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder solche mit einem Anruf in der Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="dea0d-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="dea0d-111">Weitere Informationen zur Funktion "beschäftigt-Optionen" finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="dea0d-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="dea0d-112">Installieren</span><span class="sxs-lookup"><span data-stu-id="dea0d-112">Install</span></span>

<span data-ttu-id="dea0d-113">Stellen Sie sicher, dass Sie die neueste Version von Skype for Business Server installiert haben und dass Sie den neuesten Patch installiert haben.</span><span class="sxs-lookup"><span data-stu-id="dea0d-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="dea0d-114">Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Installationsprogramm für Skype for Business Server Updates wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="dea0d-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="dea0d-115">Führen Sie den Befehl Stop-CsWindowsService aus.</span><span class="sxs-lookup"><span data-stu-id="dea0d-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="dea0d-116">Führen Sie das SkypeServerUpdateInstaller. exe-Installationsprogramm auf jedem Front-End-Server in einem Pool aus.</span><span class="sxs-lookup"><span data-stu-id="dea0d-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="dea0d-117">Führen Sie das SkypeServerUpdateInstaller. exe-Installationsprogramm auf jeder Survivable Branch Server (SBS) aus, wenn Sie die Unterstützung für Failover für SBS sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="dea0d-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="dea0d-118">Das Installationsprogramm stellt die neueste Version der Anwendung für Beschäftigte Optionen bereit.</span><span class="sxs-lookup"><span data-stu-id="dea0d-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="dea0d-119">Die Anwendung ist jedoch standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dea0d-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="dea0d-120">Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="dea0d-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="dea0d-121">Führen Sie das Cmdlet " [CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) " aus, um Beschäftigte Optionen global zu aktivieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dea0d-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="dea0d-122">Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, müssen Sie die beschäftigt-Optionen für die VoIP-Richtlinie wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="dea0d-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="dea0d-123">Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) aus, um den Namen der Website abzurufen:</span><span class="sxs-lookup"><span data-stu-id="dea0d-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="dea0d-124">Verwenden Sie den Identity-Wert (Beispiel: Site: "redmond1"), der von Get-CsSite abgerufen wurde, um die VoIP-Richtlinie der Website wie folgt abzurufen:</span><span class="sxs-lookup"><span data-stu-id="dea0d-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="dea0d-125">Wenn für die Website eine VoIP-Richtlinie vorhanden ist, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dea0d-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="dea0d-126">Führen Sie als nächstes das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um Beschäftigte Optionen zur Liste der Serveranwendungen hinzuzufügen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="dea0d-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="dea0d-127">Sie müssen% FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.</span><span class="sxs-lookup"><span data-stu-id="dea0d-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="dea0d-128">Führen Sie als nächstes das Cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten zugriffssteuerungsrollen (Role-Based Access Control, RBAC) für die Cmdlets für beschäftigt-Optionen zu aktualisieren, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="dea0d-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="dea0d-129">Starten Sie schließlich die Skype for Business Server Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen beschäftigt-Optionen installiert und aktiviert wurden, indem Sie den Befehl [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:</span><span class="sxs-lookup"><span data-stu-id="dea0d-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="dea0d-130">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="dea0d-130">Configure</span></span>

<span data-ttu-id="dea0d-131">Verwenden Sie zum Konfigurieren von beschäftigt-Optionen das Cmdlet " [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) ".</span><span class="sxs-lookup"><span data-stu-id="dea0d-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="dea0d-132">Mit dem folgenden Befehl werden beispielsweise beschäftigt-Optionen für den Benutzer "Ken Myers" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="dea0d-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="dea0d-133">In dieser Konfiguration gibt jeder Aufruf von "Ken Myers" ein Besetztzeichen zurück, wenn er sich bereits in einem Aufruf befindet:</span><span class="sxs-lookup"><span data-stu-id="dea0d-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="dea0d-134">Im nächsten Beispiel konfiguriert der Befehl die beschäftigt-Optionen für den Benutzer "Chrystal Maya".</span><span class="sxs-lookup"><span data-stu-id="dea0d-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="dea0d-135">In dieser Konfiguration werden neue eingehende Anrufe an "Chrystal-Maya" an die Voicemail weitergeleitet, wenn Sie sich bereits in einem Anruf befindet:</span><span class="sxs-lookup"><span data-stu-id="dea0d-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="dea0d-136">Mithilfe des Cmdlets [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) können Sie Konfigurationsinformationen zu den beschäftigt-Optionen abrufen.</span><span class="sxs-lookup"><span data-stu-id="dea0d-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="dea0d-137">Im folgenden Beispiel wird die Einstellung für Beschäftigte Optionen für "KenMyer@contoso.com" zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="dea0d-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="dea0d-138">Sie können Beschäftigte Optionen mithilfe des Cmdlets [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) entfernen.</span><span class="sxs-lookup"><span data-stu-id="dea0d-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="dea0d-139">Mit dem folgenden Befehl werden die beschäftigt-Optionen für "Ken Myers" entfernt:</span><span class="sxs-lookup"><span data-stu-id="dea0d-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="dea0d-140">Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von beschäftigt-Optionen verwenden, finden Sie in den technischen Referenz Inhalten für " [Sets-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)", " [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" und " [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)".</span><span class="sxs-lookup"><span data-stu-id="dea0d-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="dea0d-141">Protokollierung aktivieren</span><span class="sxs-lookup"><span data-stu-id="dea0d-141">Enable logging</span></span>

<span data-ttu-id="dea0d-142">Geben Sie Folgendes ein, um die Protokollierung für beschäftigt-Optionen mithilfe des zentralisierten Protokollierungsdiensts zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="dea0d-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="dea0d-143">Überprüfen und Beheben von Problemen</span><span class="sxs-lookup"><span data-stu-id="dea0d-143">Verify and troubleshoot</span></span>

<span data-ttu-id="dea0d-144">Nach dem Installieren von beschäftigt-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dea0d-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="dea0d-145">Wenn beschäftigt-Optionen ordnungsgemäß installiert sind, sollte die Ausgabe des Cmdlets die Konfiguration der beschäftigt-Optionen wie folgt anzeigen:</span><span class="sxs-lookup"><span data-stu-id="dea0d-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="dea0d-146">Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation von beschäftigt-Optionen erfolgreich war und Skype for Business Server beschäftigte Optionen erfolgreich geladen haben.</span><span class="sxs-lookup"><span data-stu-id="dea0d-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="dea0d-147">Zum Überprüfen der beschäftigt-Optionen öffnen Sie die **Ereignisanzeige –\> Anwendungs\> -und Dienstprotokolle – Skype (oder lync) Server** , und suchen Sie nach Ereignis-ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="dea0d-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
