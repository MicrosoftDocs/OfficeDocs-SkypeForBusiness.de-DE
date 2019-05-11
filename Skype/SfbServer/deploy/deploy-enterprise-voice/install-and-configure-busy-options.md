---
title: Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Lesen Sie zum Installieren und Konfigurieren von beschäftigt Optionen in Skype für Business Server.
ms.openlocfilehash: 5e68dd61ce668a80ccbdeb3faae5875825992650
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892363"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="2ddae-103">Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ddae-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="2ddae-104">Lesen Sie zum Installieren und Konfigurieren von beschäftigt Optionen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ddae-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="2ddae-105">Wird eine neue VoIP-Richtlinie eingeführt beschäftigt Optionen in der Juli 2016 kumulative Update, mit dem Sie zum Konfigurieren eingehender Anrufe verarbeitet werden, wenn ein Benutzer bereits eines Anrufs oder einer Konferenz oder hat bei einem Anruf auf halten.</span><span class="sxs-lookup"><span data-stu-id="2ddae-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="2ddae-106">Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an die Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2ddae-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="2ddae-107">Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer des Unternehmens (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Konfigurationsoptionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="2ddae-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="2ddae-108">Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="2ddae-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="2ddae-109">Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="2ddae-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="2ddae-110">Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.  </span><span class="sxs-lookup"><span data-stu-id="2ddae-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="2ddae-111">Weitere Informationen zur Funktion „Beschäftigt-Optionen“ finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="2ddae-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="2ddae-112">Installieren </span><span class="sxs-lookup"><span data-stu-id="2ddae-112">Install</span></span>

<span data-ttu-id="2ddae-113">Stellen Sie sicher, dass Sie die neueste Version von Skype für Business Server installiert haben und dass Sie den neuesten Patch installiert haben.</span><span class="sxs-lookup"><span data-stu-id="2ddae-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="2ddae-114">Klicken Sie dazu zunächst beenden Sie alle Dienste, und führen Sie die Skype für Update-Installationsprogramm Business Server wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2ddae-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="2ddae-115">Führen Sie den Befehl „Stop-CsWindowsService“ aus.</span><span class="sxs-lookup"><span data-stu-id="2ddae-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="2ddae-116">Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Front-End-Server in einem Pool aus.</span><span class="sxs-lookup"><span data-stu-id="2ddae-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="2ddae-117">Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Survivable Branch Server (SBS) aus, wenn Sie Failover-Unterstützung auf SBS sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2ddae-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="2ddae-p103">Das Installationsprogramm stellt die aktuelle Version der Beschäftigt-Optionen bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="2ddae-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="2ddae-121">Führen Sie das Cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) beschäftigt Optionen global aktivieren, wie im folgenden Beispiel gezeigt aus:</span><span class="sxs-lookup"><span data-stu-id="2ddae-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="2ddae-122">Wenn für den Standort eine VoIP-Richtlinie eingerichtet wurde, müssen Sie die Beschäftigt-Optionen dann wie folgt für die VoIP-Richtlinie aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2ddae-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="2ddae-123">Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) zum Abrufen der Name der Website aus:</span><span class="sxs-lookup"><span data-stu-id="2ddae-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="2ddae-124">Verwenden Sie den Identitätswert (zum Beispiel: "Site: redmond1") abgerufen, die von Get-CsSite, um die VoIP-Richtlinie der Website wie folgt abzurufen:</span><span class="sxs-lookup"><span data-stu-id="2ddae-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="2ddae-125">Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2ddae-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="2ddae-126">Führen Sie dann das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) beschäftigt Optionen zur Liste der Server-Anwendungen wie im folgenden Beispiel dargestellt hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="2ddae-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="2ddae-127">Sie müssen mit dem vollqualifizierten Domänennamen von einem bestimmten Pool FQDN % ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2ddae-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="2ddae-128">Führen Sie dann das [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) -Cmdlet, um die Role-based Access Control (RBAC) Rollen für die Cmdlets beschäftigt Optionen wie im folgenden Beispiel dargestellt zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="2ddae-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="2ddae-129">Starten Sie schließlich die Skype für Business Server Windows-Dienste auf allen Front-End-Servern in den Pools, in dem beschäftigt Optionen installiert und mithilfe des Befehls [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) aktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="2ddae-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="2ddae-130">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2ddae-130">Configure</span></span>

<span data-ttu-id="2ddae-131">Zum Konfigurieren der Beschäftigt-Optionen verwenden Sie das Cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  </span><span class="sxs-lookup"><span data-stu-id="2ddae-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="2ddae-p104">Beispiel: Mit dem folgenden Befehl werden die Beschäftigt-Optionen für den Benutzer „Ken Myer“ konfiguriert. In dieser Konfiguration wird für jeden Anruf an „Ken Myer“ ein Besetztzeichen zurückgegeben, wenn er sich bereits in einem Anruf befindet:</span><span class="sxs-lookup"><span data-stu-id="2ddae-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="2ddae-134">Im nächsten Beispiel konfiguriert der Befehl die Beschäftigt-Optionen für die Benutzerin „Chrystal Velasquez“.</span><span class="sxs-lookup"><span data-stu-id="2ddae-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="2ddae-135">In dieser Konfiguration werden neue eingehende Anrufe an „Chrystal Velasquez“ an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:</span><span class="sxs-lookup"><span data-stu-id="2ddae-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="2ddae-136">Sie können Konfigurationsinformationen zu den Beschäftigt-Optionen abrufen, indem Sie das Cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ddae-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="2ddae-137">Das folgende Beispiel gibt die Einstellung beschäftigt Optionen für "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="2ddae-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="2ddae-138">Entfernen Sie die Beschäftigt-Optionen mit dem Cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ddae-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="2ddae-139">Mit dem folgenden Befehl werden die Beschäftigt-Optionen für „Ken Myer“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="2ddae-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="2ddae-140">Ausführliche Informationen zu den Cmdlets, mit denen Sie beschäftigt Optionen Konfigurieren finden Sie unter den Inhalt technische Referenz für [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)und [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ddae-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="2ddae-141">Aktivieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="2ddae-141">Enable logging</span></span>

<span data-ttu-id="2ddae-142">Um die Protokollierung für Beschäftigt-Optionen mit dem zentralisierten Protokollierungsdienst zu aktivieren, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="2ddae-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="2ddae-143">Überprüfung und Fehlerbehebung</span><span class="sxs-lookup"><span data-stu-id="2ddae-143">Verify and troubleshoot</span></span>

<span data-ttu-id="2ddae-144">Nach der Installation von Optionen für beschäftigt, stellen Sie sicher, dass die Installation erfolgreich war, mit dem [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) -Cmdlet zum Abrufen der Liste der Server-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2ddae-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="2ddae-145">Wenn die Beschäftigt-Optionen richtig installiert sind, zeigt die Ausgabe des Cmdlets folgende Konfiguration der Beschäftigt-Optionen:</span><span class="sxs-lookup"><span data-stu-id="2ddae-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="2ddae-146">Sie können auch Windows-Ereignisanzeige verwenden, um sicherzustellen, dass die Installation beschäftigt Optionen erfolgreich war und dass Skype für Business Server ausgelastet Optionen erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="2ddae-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="2ddae-147">Um beschäftigt Optionen zu überprüfen, öffnen Sie **Ereignisanzeige -\> Anwendungs- und Dienstprotokolle -\> Skype (oder Lync) Server** und suchen Sie nach der Ereignis-ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="2ddae-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
