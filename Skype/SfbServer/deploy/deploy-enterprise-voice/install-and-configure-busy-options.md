---
title: Installieren und Konfigurieren der Besetzt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Erfahren Sie, wie Sie die Besetzt-Optionen in Skype for Business Server installieren und konfigurieren.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830805"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren der Besetzt-Optionen für Skype for Business Server

Erfahren Sie, wie Sie die Besetzt-Optionen in Skype for Business Server installieren und konfigurieren.

Bei den Besetztoptionen handelt es sich um eine neue, im kumulativen Update vom Juli 2016 eingeführte Sprachrichtlinie, mit der Sie konfigurieren können, wie eingehende Anrufe behandelt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in der Warteschleife platziert wurde. Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an Voicemail weitergeleitet werden.

Wenn die Gebucht-Optionen für die Organisation aktiviert sind, können alle Benutzer im Unternehmen, sowohl Enterprise-VoIP als auch Benutzer ohne Enterprise-VoIP, die folgenden Konfigurationsoptionen verwenden:

- Beschäftigt bei Gebucht: Neue eingehende Anrufe werden mit einem Besetztzeichen zurückgewiesen, wenn der Benutzer ausgelastet ist.

- Voicemail bei Gebucht- Dabei werden neue eingehende Anrufe an Voicemail weitergeleitet, wenn der Benutzer ausgelastet ist.

Unabhängig davon, wie die Gebucht-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Benutzer mit einem Anruf in der Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.

Weitere Informationen zum Feature "Gebucht-Optionen" finden Sie unter ["Plan for Busy Options for Skype for Business Server ".](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>Installieren

Stellen Sie sicher, dass Die neueste Version von Skype for Business Server installiert ist und dass Sie den neuesten Patch installiert haben. Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Updateinstallationsprogramm für Skype for Business Server wie folgt aus:

1. Führen Sie den Stop-CsWindowsService aus.

2. Führen Sie SkypeServerUpdateInstaller.exe Installationsprogramm auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie SkypeServerUpdateInstaller.exe Installationsprogramm auf jedem Survivable Branch Server (SBS) aus, wenn Sie die Unterstützung für Failover auf SBS sicherstellen möchten.

Das Installationsprogramm stellt die neueste Version der Anwendung "Besetzt-Optionen" zur Verfügung. Die Anwendung ist jedoch nicht standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:

1. Führen Sie [das Cmdlet "Set-CsVoicePolicy"](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) aus, um die Beschäftigt-Optionen global zu aktivieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn für den Standort eine Standortrichtlinie vorhanden ist, müssen Sie als Nächstes die Besetzt-Optionen für die Sprachrichtlinie wie folgt aktivieren:

    Führen Sie zunächst ["Get-CsSite" aus,](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) um den Namen der Website abzurufen:

   ```powershell
   Get-CsSite
   ```

    Verwenden Sie den Identitätswert (z. B. "Site:Redmond1"), der von Get-CsSite abgerufen wurde, um die Sprachrichtlinie des Standorts wie folgt abzurufen:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn für den Standort eine Sprachrichtlinie vorhanden ist, führen Sie den folgenden Befehl aus:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie als Nächstes das [Cmdlet "New-CsServerApplication"](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um der Liste der Serveranwendungen wie im folgenden Beispiel gezeigt die Beschäftigt-Optionen hinzuzufügen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen %FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.

4. Führen Sie als Nächstes das [Cmdlet "Update-CsAdminRole"](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten Zugriffssteuerungsrollen (Role-based Access Control, RBAC) für die Cmdlets "Busy Options" zu aktualisieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype for Business Server-Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen die Besetzt-Optionen installiert und aktiviert wurden, indem Sie den Befehl ["Start-CsWindowsService"](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Konfigurieren

Verwenden Sie das Cmdlet ["Set-CsBusyOptions",](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) um die Beschäftigt-Optionen zu konfigurieren.

Mit dem folgenden Befehl werden beispielsweise die Besetzt-Optionen für den Benutzer "Ken Myer" konfiguriert. In dieser Konfiguration gibt jeder Aufruf von "Ken Myer" ein Besetztzeichen zurück, wenn er sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Im nächsten Beispiel konfiguriert der Befehl die Besetzt-Optionen für den Benutzer "Chrystal Velasquez". In dieser Konfiguration werden neue eingehende Anrufe an "Chrystal Velasquez" an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Mit dem Cmdlet ["Get-CsBusyOptions"](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) können Sie Konfigurationsinformationen zu den Beschäftigt-Optionen abrufen. Im folgenden Beispiel wird die Einstellung "Busy Options" für "KenMyer@Contoso.com" zurückgegeben:

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Sie können die Beschäftigt-Optionen mithilfe des [Cmdlets "Remove-CsBusyOptions"](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) entfernen. Mit dem folgenden Befehl werden die Besetzt-Optionen für "Ken Myer" entfernt:

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von Beschäftigt-Optionen verwenden, finden Sie in den technischen Referenzinhalten für [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)und [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Aktivieren der Protokollierung

Geben Sie Folgendes an, um die Protokollierung für Die Gebucht-Optionen mithilfe des zentralisierten Protokollierungsdiensts zu aktivieren:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Überprüfen und Beheben von Problemen

Nach der Installation der "Busy"-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet ["Get-CsServerApplication"](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen. Wenn die Besetzt-Optionen ordnungsgemäß installiert sind, sollte in der Ausgabe des Cmdlets die Konfiguration der Besetzt-Optionen wie folgt angezeigt werden:

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

Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation der Besetzt-Optionen erfolgreich war und ob Skype for Business Server die Besetzt-Optionen erfolgreich geladen hat. Um die Besetzt-Optionen zu überprüfen, öffnen Sie die Ereignisanzeige – Anwendungs- und Dienstprotokolle **\> – Skype \> (oder Lync)-Server,** und suchen Sie nach der Ereignis-ID = 30253.
