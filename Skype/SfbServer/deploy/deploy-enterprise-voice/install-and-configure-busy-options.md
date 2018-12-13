---
title: Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server
ms.author: crowe
author: CarolynRowe
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
ms.openlocfilehash: a5fdd117f2c812bba69978a7d2943321b940bcc4
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240659"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server

Lesen Sie zum Installieren und Konfigurieren von beschäftigt Optionen in Skype für Business Server.

Wird eine neue VoIP-Richtlinie eingeführt beschäftigt Optionen in der Juli 2016 kumulative Update, mit dem Sie zum Konfigurieren eingehender Anrufe verarbeitet werden, wenn ein Benutzer bereits eines Anrufs oder einer Konferenz oder hat bei einem Anruf auf halten. Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an die Voicemail weitergeleitet werden.

Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer des Unternehmens (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Konfigurationsoptionen verwenden:

- Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.

- Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.

Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.  

Weitere Informationen zur Funktion „Beschäftigt-Optionen“ finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>Installieren 

Stellen Sie sicher, dass Sie die neueste Version von Skype für Business Server installiert haben und dass Sie den neuesten Patch installiert haben. Klicken Sie dazu zunächst beenden Sie alle Dienste, und führen Sie die Skype für Update-Installationsprogramm Business Server wie folgt:

1. Führen Sie den Befehl „Stop-CsWindowsService“ aus.

2. Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Survivable Branch Server (SBS) aus, wenn Sie Failover-Unterstützung auf SBS sicherstellen möchten.

Das Installationsprogramm stellt die aktuelle Version der Beschäftigt-Optionen bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:

1. Führen Sie das Cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) beschäftigt Optionen global aktivieren, wie im folgenden Beispiel gezeigt aus:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn für den Standort eine VoIP-Richtlinie eingerichtet wurde, müssen Sie die Beschäftigt-Optionen dann wie folgt für die VoIP-Richtlinie aktivieren:

    Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) zum Abrufen der Name der Website aus:

   ```
   Get-CsSite
   ```

    Verwenden Sie den Identitätswert (zum Beispiel: "Site: redmond1") abgerufen, die von Get-CsSite, um die VoIP-Richtlinie der Website wie folgt abzurufen:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, führen Sie folgenden Befehl aus:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie dann das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) beschäftigt Optionen zur Liste der Server-Anwendungen wie im folgenden Beispiel dargestellt hinzuzufügen:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen mit dem vollqualifizierten Domänennamen von einem bestimmten Pool FQDN % ersetzen.

4. Führen Sie dann das [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) -Cmdlet, um die Role-based Access Control (RBAC) Rollen für die Cmdlets beschäftigt Optionen wie im folgenden Beispiel dargestellt zu aktualisieren:

   ```
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype für Business Server Windows-Dienste auf allen Front-End-Servern in den Pools, in dem beschäftigt Optionen installiert und mithilfe des Befehls [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) aktiviert wurde:

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Konfigurieren

Zum Konfigurieren der Beschäftigt-Optionen verwenden Sie das Cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  

Beispiel: Mit dem folgenden Befehl werden die Beschäftigt-Optionen für den Benutzer „Ken Myer“ konfiguriert. In dieser Konfiguration wird für jeden Anruf an „Ken Myer“ ein Besetztzeichen zurückgegeben, wenn er sich bereits in einem Anruf befindet:

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Im nächsten Beispiel konfiguriert der Befehl die Beschäftigt-Optionen für die Benutzerin „Chrystal Velasquez“. In dieser Konfiguration werden neue eingehende Anrufe an „Chrystal Velasquez“ an Voicemail weitergeleitet, wenn sie sich bereits in einem Anruf befindet:

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Sie können Konfigurationsinformationen zu den Beschäftigt-Optionen abrufen, indem Sie das Cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) verwenden. Das folgende Beispiel gibt die Einstellung beschäftigt Optionen für "KenMyer@Contoso.com":

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Entfernen Sie die Beschäftigt-Optionen mit dem Cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). Mit dem folgenden Befehl werden die Beschäftigt-Optionen für „Ken Myer“ entfernt:

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, mit denen Sie beschäftigt Optionen Konfigurieren finden Sie unter den Inhalt technische Referenz für [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)und [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Aktivieren der Protokollierung

Um die Protokollierung für Beschäftigt-Optionen mit dem zentralisierten Protokollierungsdienst zu aktivieren, geben Sie Folgendes an:

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Überprüfung und Fehlerbehebung

Nach der Installation von Optionen für beschäftigt, stellen Sie sicher, dass die Installation erfolgreich war, mit dem [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) -Cmdlet zum Abrufen der Liste der Server-Anwendungen. Wenn die Beschäftigt-Optionen richtig installiert sind, zeigt die Ausgabe des Cmdlets folgende Konfiguration der Beschäftigt-Optionen:

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

Sie können auch Windows-Ereignisanzeige verwenden, um sicherzustellen, dass die Installation beschäftigt Optionen erfolgreich war und dass Skype für Business Server ausgelastet Optionen erfolgreich geladen. Um beschäftigt Optionen zu überprüfen, öffnen Sie **Ereignisanzeige -\> Anwendungs- und Dienstprotokolle -\> Skype (oder Lync) Server** und suchen Sie nach der Ereignis-ID = 30253.
