---
title: Installieren und Konfigurieren von Gebucht-Optionen für Skype for Business Server
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
description: Lesen Sie, wie Sie Gebucht-Optionen in Skype for Business Server installieren und konfigurieren.
ms.openlocfilehash: 04690e9f2c7fbf16b67432526fe5c8fd6e5b95af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106311"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren von Gebucht-Optionen für Skype for Business Server

Lesen Sie, wie Sie Gebucht-Optionen in Skype for Business Server installieren und konfigurieren.

Bei den Gebucht-Optionen handelt es sich um eine neue Voicerichtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde. Mit dieser Können Sie konfigurieren, wie eingehende Anrufe verarbeitet werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in warteschleifen muss. Neue oder eingehende Anrufe können mit einem Gebucht-Signal abgelehnt oder an Voicemail weitergeleitet werden.

Wenn Die Gebucht-Optionen für die Organisation aktiviert sind, können alle Benutzer im Unternehmen, sowohl Enterprise-VoIP als auch Nicht-Enterprise-VoIP-Benutzer, die folgenden Konfigurationsoptionen verwenden:

- Busy on Busy : Bei dem neue eingehende Anrufe mit einem Gebucht-Signal zurückgewiesen werden, wenn der Benutzer ausgelastet ist.

- Voicemail on Busy – Bei der neue eingehende Anrufe an Voicemail weitergeleitet werden, wenn der Benutzer ausgelastet ist.

Unabhängig davon, wie ihre Gebucht-Optionen konfiguriert sind, sind Benutzer in einem Anruf oder einer Konferenz oder personen mit einem Halteanruf nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.

Weitere Informationen zum Feature "Gebucht"-Optionen finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installieren

Stellen Sie sicher, dass die neueste Version von Skype for Business Server installiert ist und dass Sie den neuesten Patch installiert haben. Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Skype for Business Server-Updateinstallationsprogramm wie folgt aus:

1. Führen Sie den Stop-CsWindowsService aus.

2. Führen Sie SkypeServerUpdateInstaller.exe Installationsprogramm auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie SkypeServerUpdateInstaller.exe Installationsprogramm auf jedem Survivable Branch Server (SBS) aus, wenn Sie die Unterstützung für Failover auf SBS sicherstellen möchten.

Das Installationsprogramm stellt die neueste Version der Anwendung "Gebucht-Optionen" zur Verfügung. Die Anwendung ist jedoch standardmäßig nicht aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:

1. Führen Sie [das Cmdlet Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) aus, um gebuchte Optionen global zu aktivieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn auf der Website als Nächstes eine Voicerichtlinie vorhanden ist, müssen Sie die Option "Gebucht" für die Voicerichtlinie wie folgt aktivieren:

    Führen Sie zunächst [Get-CsSite aus,](/powershell/module/skype/get-cssite?view=skype-ps) um den Namen der Website abzurufen:

   ```powershell
   Get-CsSite
   ```

    Verwenden Sie den Identitätswert (z. B. Site:Redmond1), der von Get-CsSite abgerufen wurde, um die Voicerichtlinie des Standorts wie folgt abzurufen:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn eine Sprachrichtlinie für den Standort vorhanden ist, führen Sie den folgenden Befehl aus:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie als Nächstes [das Cmdlet New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um der Liste der Serveranwendungen Gebucht-Optionen hinzuzufügen, wie im folgenden Beispiel gezeigt:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen %FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.

4. Führen Sie als Nächstes das [Cmdlet Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten Zugriffssteuerungsrollen für die Cmdlets "Busy Options" wie im folgenden Beispiel dargestellt zu aktualisieren:

   ```powershell
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype for Business Server -Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen Gebucht-Optionen installiert und aktiviert wurden, indem Sie den [Befehl Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Konfigurieren

Verwenden Sie zum Konfigurieren von [Gebucht-Optionen das Cmdlet Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Mit dem folgenden Befehl werden beispielsweise die Gebucht-Optionen für den Benutzer "Ken Myer" konfiguriert. In dieser Konfiguration gibt jeder Aufruf von "Ken Myer" ein Gebucht-Signal zurück, wenn er sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Im nächsten Beispiel konfiguriert der Befehl Die Gebucht-Optionen für den Benutzer "Chrystal Velasquez". In dieser Konfiguration werden neue eingehende Anrufe an "Chrystal Velasquez" an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Sie können Konfigurationsinformationen zu Gebucht-Optionen mithilfe des [Cmdlets Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) abrufen. Im folgenden Beispiel wird die Einstellung Gebucht-Optionen für "KenMyer@Contoso.com" zurückgegeben:

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Sie können gebuchte Optionen mithilfe des [Cmdlets Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) entfernen. Mit dem folgenden Befehl werden gebuchte Optionen für "Ken Myer" entfernt:

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von Busy-Optionen verwenden, finden Sie im technischen Referenzinhalt für [Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)und [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Aktivieren der Protokollierung

Um die Protokollierung für Gebucht-Optionen mithilfe des zentralisierten Protokollierungsdiensts zu aktivieren, geben Sie Folgendes an:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Überprüfen und Beheben von Problemen

Nach der Installation von Busy-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das [Cmdlet Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen. Wenn Die Gebucht-Optionen ordnungsgemäß installiert sind, sollte in der Ausgabe des Cmdlets die Konfiguration der Gebucht-Optionen wie folgt angezeigt werden:

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

Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation von Gebucht-Optionen erfolgreich war und dass Skype for Business Server die Gebucht-Optionen erfolgreich geladen hat. Öffnen Sie zum Überprüfen von Gebucht-Optionen die Ereignisanzeige - Anwendungs- und Dienstprotokolle **\> - Skype \> (oder Lync)-Server,** und suchen Sie nach Ereignis-ID = 30253.