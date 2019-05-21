---
title: Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Weitere Informationen zum Installieren und Konfigurieren von busy-Optionen in Skype for Business Server.
ms.openlocfilehash: 13f529ddd7bd3b83f9d065599d3a213662da31a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281601"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="d46e4-103">Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d46e4-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="d46e4-104">Weitere Informationen zum Installieren und Konfigurieren von busy-Optionen in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d46e4-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="d46e4-105">"Busy Options" ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit dem Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="d46e4-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="d46e4-106">Neue oder eingehende Anrufe können mit einem Busy-Signal zurückgewiesen oder an die Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d46e4-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="d46e4-107">Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer des Unternehmens (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Konfigurationsoptionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="d46e4-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="d46e4-108">Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="d46e4-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="d46e4-109">Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="d46e4-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="d46e4-110">Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.  </span><span class="sxs-lookup"><span data-stu-id="d46e4-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="d46e4-111">Weitere Informationen zur Funktion „Beschäftigt-Optionen“ finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="d46e4-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="d46e4-112">Installieren </span><span class="sxs-lookup"><span data-stu-id="d46e4-112">Install</span></span>

<span data-ttu-id="d46e4-113">Stellen Sie sicher, dass Sie die neueste Version von Skype for Business Server installiert haben und dass Sie den neuesten Patch installiert haben.</span><span class="sxs-lookup"><span data-stu-id="d46e4-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="d46e4-114">Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Installationsprogramm für Skype for Business Server Update wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d46e4-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="d46e4-115">Führen Sie den Befehl „Stop-CsWindowsService“ aus.</span><span class="sxs-lookup"><span data-stu-id="d46e4-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="d46e4-116">Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Front-End-Server in einem Pool aus.</span><span class="sxs-lookup"><span data-stu-id="d46e4-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="d46e4-117">Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Survivable Branch Server (SBS) aus, wenn Sie Failover-Unterstützung auf SBS sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d46e4-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="d46e4-p103">Das Installationsprogramm stellt die aktuelle Version der Beschäftigt-Optionen bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="d46e4-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="d46e4-121">Führen Sie das Cmdlet " [Satz-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) " aus, um die Optionen für die globale Auslastung zu aktivieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d46e4-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="d46e4-122">Wenn für den Standort eine VoIP-Richtlinie eingerichtet wurde, müssen Sie die Beschäftigt-Optionen dann wie folgt für die VoIP-Richtlinie aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d46e4-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="d46e4-123">Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) aus, um den Namen der Website abzurufen:</span><span class="sxs-lookup"><span data-stu-id="d46e4-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="d46e4-124">Verwenden Sie den Wert für Identity (Beispiel: Website: "redmond1"), der von Get-CsSite abgerufen wird, um die VoIP-Richtlinie der Website wie folgt abzurufen:</span><span class="sxs-lookup"><span data-stu-id="d46e4-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="d46e4-125">Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d46e4-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="d46e4-126">Führen Sie als nächstes das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um der Liste der Serveranwendungen beschäftigte Optionen hinzuzufügen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d46e4-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="d46e4-127">Sie müssen% FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d46e4-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="d46e4-128">Führen Sie als nächstes das Cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten zugriffssteuerungsrollen für die Cmdlets "busy-Optionen" zu aktualisieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d46e4-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="d46e4-129">Starten Sie schließlich die Skype for Business Server-Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen busy-Optionen installiert und aktiviert wurden, indem Sie den Befehl [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:</span><span class="sxs-lookup"><span data-stu-id="d46e4-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="d46e4-130">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d46e4-130">Configure</span></span>

<span data-ttu-id="d46e4-131">Zum Konfigurieren der Beschäftigt-Optionen verwenden Sie das Cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  </span><span class="sxs-lookup"><span data-stu-id="d46e4-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="d46e4-p104">Beispiel: Mit dem folgenden Befehl werden die Beschäftigt-Optionen für den Benutzer „Ken Myer“ konfiguriert. In dieser Konfiguration wird für jeden Anruf an „Ken Myer“ ein Besetztzeichen zurückgegeben, wenn er sich bereits in einem Anruf befindet:</span><span class="sxs-lookup"><span data-stu-id="d46e4-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="d46e4-134">Im nächsten Beispiel konfiguriert der Befehl die Beschäftigt-Optionen für die Benutzerin „Chrystal Velasquez“.</span><span class="sxs-lookup"><span data-stu-id="d46e4-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="d46e4-135">In dieser Konfiguration werden neue eingehende Anrufe an „Chrystal Velasquez“ an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:</span><span class="sxs-lookup"><span data-stu-id="d46e4-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="d46e4-136">Sie können Konfigurationsinformationen zu den Beschäftigt-Optionen abrufen, indem Sie das Cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d46e4-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="d46e4-137">Im folgenden Beispiel wird die Einstellung für busy-Optionen für "KenMyer@contoso.com" zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="d46e4-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="d46e4-138">Entfernen Sie die Beschäftigt-Optionen mit dem Cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="d46e4-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="d46e4-139">Mit dem folgenden Befehl werden die Beschäftigt-Optionen für „Ken Myer“ entfernt:</span><span class="sxs-lookup"><span data-stu-id="d46e4-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="d46e4-140">Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von busy-Optionen verwenden, finden Sie in den technischen Referenz Inhalten für " [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)", " [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" und " [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)".</span><span class="sxs-lookup"><span data-stu-id="d46e4-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="d46e4-141">Aktivieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="d46e4-141">Enable logging</span></span>

<span data-ttu-id="d46e4-142">Um die Protokollierung für Beschäftigt-Optionen mit dem zentralisierten Protokollierungsdienst zu aktivieren, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="d46e4-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="d46e4-143">Überprüfung und Fehlerbehebung</span><span class="sxs-lookup"><span data-stu-id="d46e4-143">Verify and troubleshoot</span></span>

<span data-ttu-id="d46e4-144">Nach der Installation von busy-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d46e4-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="d46e4-145">Wenn die Beschäftigt-Optionen richtig installiert sind, zeigt die Ausgabe des Cmdlets folgende Konfiguration der Beschäftigt-Optionen:</span><span class="sxs-lookup"><span data-stu-id="d46e4-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

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

<span data-ttu-id="d46e4-146">Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation von busy-Optionen erfolgreich war und dass Skype for Business Server die busy-Optionen erfolgreich geladen hat.</span><span class="sxs-lookup"><span data-stu-id="d46e4-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="d46e4-147">Öffnen Sie zum Überprüfen der Auslastungs Optionen die **Ereignisanzeige –\> Anwendungs\> -und Dienstprotokolle – Skype (oder lync) Server** , und suchen Sie nach Ereignis-ID = 30253.</span><span class="sxs-lookup"><span data-stu-id="d46e4-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
