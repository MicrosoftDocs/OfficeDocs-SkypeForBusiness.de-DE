---
title: Installieren und Konfigurieren von Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Erfahren Sie, wie Sie Beschäftigt-Optionen in Skype for Business Server installieren und konfigurieren.
ms.openlocfilehash: 5e0dde157fc39ab7c24ddd297e858ce5a06e888f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835913"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren von Beschäftigt-Optionen für Skype for Business Server

Erfahren Sie, wie Sie Beschäftigt-Optionen in Skype for Business Server installieren und konfigurieren.

Beschäftigt-Optionen ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit der Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf gehalten wird. Neue oder eingehende Anrufe können mit einem Besetzt-Signal abgelehnt oder an Voicemail weitergeleitet werden.

Wenn beschäftigt-Optionen für die Organisation aktiviert ist, können alle Benutzer am Enterprise, sowohl Enterprise-VoIP als auch nicht Enterprise-VoIP Benutzer, die folgenden Konfigurationsoptionen verwenden:

- Beschäftigt bei Beschäftigt – In dem neue eingehende Anrufe mit einem Besetzt-Signal abgelehnt werden, wenn der Benutzer ausgelastet ist.

- Voicemail bei Beschäftigt – In dem neue eingehende Anrufe an Voicemail weitergeleitet werden, wenn der Benutzer ausgelastet ist.

Unabhängig davon, wie ihre Beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder personen mit einer Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.

Weitere Informationen zum Feature Beschäftigt-Optionen finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installieren

Stellen Sie sicher, dass Sie die neueste Version von Skype for Business Server installiert haben und dass Sie den neuesten Patch installiert haben. Beenden Sie hierzu zunächst alle Dienste, und führen Sie dann das Installationsprogramm für Skype for Business Server Update wie folgt aus:

1. Führen Sie den Befehl Stop-CsWindowsService aus.

2. Führen Sie das Installationsprogramm SkypeServerUpdateInstaller.exe auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie das SkypeServerUpdateInstaller.exe Installationsprogramm auf jedem Survivable Branch Server (SBS) aus, wenn Sie die Unterstützung für Failover auf SBS sicherstellen möchten.

Das Installationsprogramm stellt die neueste Version der Beschäftigt-Optionen-Anwendung bereit. Die Anwendung ist jedoch nicht standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:

1. Führen Sie das Cmdlet ["Set-CsVoicePolicy"](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) aus, um beschäftigt-Optionen global zu aktivieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn auf dem Standort eine VoIP-Richtlinie vorhanden ist, müssen Sie als Nächstes die Beschäftigt-Optionen für die VoIP-Richtlinie wie folgt aktivieren:

    Führen Sie zunächst ["Get-CsSite"](/powershell/module/skype/get-cssite?view=skype-ps) aus, um den Namen der Website abzurufen:

   ```powershell
   Get-CsSite
   ```

    Verwenden Sie den Identitätswert (z. B. Site:Redmond1), der von Get-CsSite abgerufen wurde, um die VoIP-Richtlinie des Standorts wie folgt abzurufen:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn für die Website eine VoIP-Richtlinie vorhanden ist, führen Sie den folgenden Befehl aus:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie als Nächstes das Cmdlet ["New-CsServerApplication" aus,](/powershell/module/skype/new-csserverapplication?view=skype-ps) um der Liste der Serveranwendungen Beschäftigt-Optionen hinzuzufügen, wie im folgenden Beispiel gezeigt:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen %FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.

4. Führen Sie als Nächstes das Cmdlet ["Update-CsAdminRole"](/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die Rollen der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) für die Beschäftigt-Optionen-Cmdlets zu aktualisieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype for Business Server Windows Dienste auf allen Front-End-Servern in allen Pools, in denen Beschäftigt-Optionen installiert und aktiviert wurden, indem Sie den Befehl ["Start-CsWindowsService"](/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Konfigurieren

Verwenden Sie zum Konfigurieren von Beschäftigt-Optionen das Cmdlet ["Set-CsBusyOptions".](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Mit dem folgenden Befehl werden beispielsweise beschäftigt-Optionen für den Benutzer "Ken Myer" konfiguriert. In dieser Konfiguration gibt jeder Aufruf von "Ken Myer" ein besetztes Signal zurück, wenn er sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Im nächsten Beispiel konfiguriert der Befehl beschäftigt Optionen für den Benutzer "Chrystal Velasquez". In dieser Konfiguration werden neue eingehende Anrufe an "Chrystal Velasquez" an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Mit dem Cmdlet ["Get-CsBusyOptions"](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) können Sie Konfigurationsinformationen zu Beschäftigt-Optionen abrufen. Im folgenden Beispiel wird die Einstellung "Beschäftigt-Optionen" für "KenMyer@Contoso.com" zurückgegeben:

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Sie können Beschäftigt-Optionen mithilfe des [Cmdlets "Remove-CsBusyOptions"](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) entfernen. Mit dem folgenden Befehl werden beschäftigt-Optionen für "Ken Myer" entfernt:

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von Beschäftigt-Optionen verwenden, finden Sie in den technischen Referenzinhalten für ["Set-CsBusyOptions",](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) ["Get-CsBusyOptions"](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)und ["Remove-CsBusyOptions".](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)

## <a name="enable-logging"></a>Protokollierung aktivieren

Geben Sie Folgendes an, um die Protokollierung für Beschäftigt-Optionen mithilfe des zentralisierten Protokollierungsdiensts zu aktivieren:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Überprüfen und Problembehandlung

Nach der Installation von Beschäftigt-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet ["Get-CsServerApplication"](/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen. Wenn die Beschäftigt-Optionen ordnungsgemäß installiert sind, sollte in der Ausgabe des Cmdlets die Konfiguration der Beschäftigt-Optionen wie folgt angezeigt werden:

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

Sie können auch Windows Ereignisanzeige verwenden, um zu überprüfen, ob die Installation der Beschäftigt-Optionen erfolgreich war und dass die Beschäftigt-Optionen erfolgreich geladen Skype for Business Server. Öffnen Sie zum Überprüfen der Beschäftigt-Optionen **die Ereignisanzeige – \> Anwendungs- und Dienstprotokolle – \> Skype (oder Lync)-Server,** und suchen Sie nach der Ereignis-ID = 30253.