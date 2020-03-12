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
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren von beschäftigt-Optionen für Skype for Business Server

In diesem Artikel erfahren Sie, wie Sie beschäftigte Optionen in Skype for Business Server installieren und konfigurieren.

Busy options ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit dem Sie konfigurieren können, wie eingehende Anrufe verarbeitet werden, wenn ein Benutzer sich bereits in einem Anruf oder einer Konferenz befindet oder wenn ein Anruf in die Warteschleife gestellt wird. Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen oder an Voicemail weitergeleitet werden.

Wenn beschäftigt-Optionen für die Organisation aktiviert sind, können alle Benutzer im Unternehmen, sowohl Enterprise-VoIP-als auch nicht-Enterprise-VoIP-Benutzer, die folgenden Konfigurationsoptionen verwenden:

- Beschäftigt in "beschäftigt" – in dem neue eingehende Anrufe mit einem Besetztzeichen zurückgewiesen werden, wenn der Benutzer beschäftigt ist.

- Voicemail in "beschäftigt" – bei dem neue eingehende Anrufe an die Voicemail weitergeleitet werden, wenn der Benutzer beschäftigt ist.

Unabhängig davon, wie die beschäftigt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder solche mit einem Anruf in der Warteschleife nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.

Weitere Informationen zur Funktion "beschäftigt-Optionen" finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installieren

Stellen Sie sicher, dass Sie die neueste Version von Skype for Business Server installiert haben und dass Sie den neuesten Patch installiert haben. Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Installationsprogramm für Skype for Business Server Updates wie folgt aus:

1. Führen Sie den Befehl Stop-CsWindowsService aus.

2. Führen Sie das SkypeServerUpdateInstaller. exe-Installationsprogramm auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie das SkypeServerUpdateInstaller. exe-Installationsprogramm auf jeder Survivable Branch Server (SBS) aus, wenn Sie die Unterstützung für Failover für SBS sicherstellen möchten.

Das Installationsprogramm stellt die neueste Version der Anwendung für Beschäftigte Optionen bereit. Die Anwendung ist jedoch standardmäßig nicht aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:

1. Führen Sie das Cmdlet " [CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) " aus, um Beschäftigte Optionen global zu aktivieren, wie im folgenden Beispiel gezeigt:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, müssen Sie die beschäftigt-Optionen für die VoIP-Richtlinie wie folgt aktivieren:

    Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) aus, um den Namen der Website abzurufen:

   ```powershell
   Get-CsSite
   ```

    Verwenden Sie den Identity-Wert (Beispiel: Site: "redmond1"), der von Get-CsSite abgerufen wurde, um die VoIP-Richtlinie der Website wie folgt abzurufen:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn für die Website eine VoIP-Richtlinie vorhanden ist, führen Sie den folgenden Befehl aus:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie als nächstes das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um Beschäftigte Optionen zur Liste der Serveranwendungen hinzuzufügen, wie im folgenden Beispiel gezeigt:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen% FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.

4. Führen Sie als nächstes das Cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten zugriffssteuerungsrollen (Role-Based Access Control, RBAC) für die Cmdlets für beschäftigt-Optionen zu aktualisieren, wie im folgenden Beispiel dargestellt:

   ```powershell
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype for Business Server Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen beschäftigt-Optionen installiert und aktiviert wurden, indem Sie den Befehl [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Konfigurieren

Verwenden Sie zum Konfigurieren von beschäftigt-Optionen das Cmdlet " [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) ".

Mit dem folgenden Befehl werden beispielsweise beschäftigt-Optionen für den Benutzer "Ken Myers" konfiguriert. In dieser Konfiguration gibt jeder Aufruf von "Ken Myers" ein Besetztzeichen zurück, wenn er sich bereits in einem Aufruf befindet:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Im nächsten Beispiel konfiguriert der Befehl die beschäftigt-Optionen für den Benutzer "Chrystal Maya". In dieser Konfiguration werden neue eingehende Anrufe an "Chrystal-Maya" an die Voicemail weitergeleitet, wenn Sie sich bereits in einem Anruf befindet:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Mithilfe des Cmdlets [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) können Sie Konfigurationsinformationen zu den beschäftigt-Optionen abrufen. Im folgenden Beispiel wird die Einstellung für Beschäftigte Optionen für "KenMyer@contoso.com" zurückgegeben:

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Sie können Beschäftigte Optionen mithilfe des Cmdlets [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) entfernen. Mit dem folgenden Befehl werden die beschäftigt-Optionen für "Ken Myers" entfernt:

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von beschäftigt-Optionen verwenden, finden Sie in den technischen Referenz Inhalten für " [Sets-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)", " [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" und " [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)".

## <a name="enable-logging"></a>Protokollierung aktivieren

Geben Sie Folgendes ein, um die Protokollierung für beschäftigt-Optionen mithilfe des zentralisierten Protokollierungsdiensts zu aktivieren:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Überprüfen und Beheben von Problemen

Nach dem Installieren von beschäftigt-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen. Wenn beschäftigt-Optionen ordnungsgemäß installiert sind, sollte die Ausgabe des Cmdlets die Konfiguration der beschäftigt-Optionen wie folgt anzeigen:

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

Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation von beschäftigt-Optionen erfolgreich war und Skype for Business Server beschäftigte Optionen erfolgreich geladen haben. Zum Überprüfen der beschäftigt-Optionen öffnen Sie die **Ereignisanzeige –\> Anwendungs\> -und Dienstprotokolle – Skype (oder lync) Server** , und suchen Sie nach Ereignis-ID = 30253.
