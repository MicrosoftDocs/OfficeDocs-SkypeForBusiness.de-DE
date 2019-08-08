---
title: Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Weitere Informationen zum Installieren und Konfigurieren von busy-Optionen in Skype for Business Server.
ms.openlocfilehash: a0fd235d5db645035ac9a6344c233dfe12a78b7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240310"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installieren und Konfigurieren der Beschäftigt-Optionen für Skype for Business Server

Weitere Informationen zum Installieren und Konfigurieren von busy-Optionen in Skype for Business Server.

"Busy Options" ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde, mit dem Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde. Neue oder eingehende Anrufe können mit einem Busy-Signal zurückgewiesen oder an die Voicemail weitergeleitet werden.

Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer des Unternehmens (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Konfigurationsoptionen verwenden:

- Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.

- Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.

Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.  

Weitere Informationen zur Funktion „Beschäftigt-Optionen“ finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>Installieren 

Stellen Sie sicher, dass Sie die neueste Version von Skype for Business Server installiert haben und dass Sie den neuesten Patch installiert haben. Beenden Sie dazu zunächst alle Dienste, und führen Sie dann das Installationsprogramm für Skype for Business Server Update wie folgt aus:

1. Führen Sie den Befehl „Stop-CsWindowsService“ aus.

2. Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Front-End-Server in einem Pool aus.

3. Führen Sie das Installationsprogramm „SkypeServerUpdateInstaller.exe“ auf jedem Survivable Branch Server (SBS) aus, wenn Sie Failover-Unterstützung auf SBS sicherstellen möchten.

Das Installationsprogramm stellt die aktuelle Version der Beschäftigt-Optionen bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:

1. Führen Sie das Cmdlet " [Satz-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) " aus, um die Optionen für die globale Auslastung zu aktivieren, wie im folgenden Beispiel gezeigt:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Wenn für den Standort eine VoIP-Richtlinie eingerichtet wurde, müssen Sie die Beschäftigt-Optionen dann wie folgt für die VoIP-Richtlinie aktivieren:

    Führen Sie zuerst [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) aus, um den Namen der Website abzurufen:

   ```
   Get-CsSite
   ```

    Verwenden Sie den Wert für Identity (Beispiel: Website: "redmond1"), der von Get-CsSite abgerufen wird, um die VoIP-Richtlinie der Website wie folgt abzurufen:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Wenn für den Standort eine VoIP-Richtlinie vorhanden ist, führen Sie folgenden Befehl aus:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Führen Sie als nächstes das Cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) aus, um der Liste der Serveranwendungen beschäftigte Optionen hinzuzufügen, wie im folgenden Beispiel gezeigt:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Sie müssen% FQDN% durch den vollqualifizierten Domänennamen eines bestimmten Pools ersetzen.

4. Führen Sie als nächstes das Cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) aus, um die rollenbasierten zugriffssteuerungsrollen für die Cmdlets "busy-Optionen" zu aktualisieren, wie im folgenden Beispiel gezeigt:

   ```
   Update-CsAdminRole
   ```

5. Starten Sie schließlich die Skype for Business Server-Windows-Dienste auf allen Front-End-Servern in allen Pools, in denen busy-Optionen installiert und aktiviert wurden, indem Sie den Befehl [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ausführen:

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

Sie können Konfigurationsinformationen zu den Beschäftigt-Optionen abrufen, indem Sie das Cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) verwenden. Im folgenden Beispiel wird die Einstellung für busy-Optionen für "KenMyer@contoso.com" zurückgegeben:

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Entfernen Sie die Beschäftigt-Optionen mit dem Cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). Mit dem folgenden Befehl werden die Beschäftigt-Optionen für „Ken Myer“ entfernt:

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Ausführliche Informationen zu den Cmdlets, die Sie zum Konfigurieren von busy-Optionen verwenden, finden Sie in den technischen Referenz Inhalten für " [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)", " [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" und " [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)".

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

Nach der Installation von busy-Optionen können Sie überprüfen, ob die Installation erfolgreich war, indem Sie das Cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) verwenden, um die Liste der Serveranwendungen abzurufen. Wenn die Beschäftigt-Optionen richtig installiert sind, zeigt die Ausgabe des Cmdlets folgende Konfiguration der Beschäftigt-Optionen:

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

Sie können auch die Windows-Ereignisanzeige verwenden, um zu überprüfen, ob die Installation von busy-Optionen erfolgreich war und dass Skype for Business Server die busy-Optionen erfolgreich geladen hat. Öffnen Sie zum Überprüfen der Auslastungs Optionen die **Ereignisanzeige –\> Anwendungs\> -und Dienstprotokolle – Skype (oder lync) Server** , und suchen Sie nach Ereignis-ID = 30253.
