---
title: Verwenden von PowerShell für Aufgaben im Clientmenü
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für das Clientmenü.'
ms.openlocfilehash: 1dc0c3a9638af8fdec90fccb633909b9ccf40405
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824653"
---
# <a name="client"></a>Client

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie mit dem **Clientmenüelement** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Client](#client)
  - [Clientversionsrichtlinie](#client-version-policy)
  - [Clientversionskonfiguration](#client-version-configuration)
  - [Geräteaktualisierung](#device-update)
  - [Testgerät](#test-device)
  - [Geräteprotokollkonfiguration](#device-log-configuration)
  - [Gerätekonfiguration](#device-configuration)
  - [Mobilitätsrichtlinie](#mobility-policy)
  - [Konfiguration von Pushbenachrichtigungen](#push-notification-configuration)

## <a name="client-version-policy"></a>Clientversionsrichtlinie

Das Untermenüelement **CLIENTVERSIONSRICHTLINIE** unter dem Menü **"Client"** gibt Informationen zu den Clients zurück, die in Skype for Business Server Umgebung unterstützt werden. Mit einer Clientversionsrichtlinie können Sie die Clients angeben, die sich bei Skype for Business Server System anmelden können.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **CLIENT VERSION POLICY** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Clientversionsrichtlinien

   ![Clientversionsrichtlinie auflisten](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Beispiel***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Szenario 2:** Erstellen einer neuen Clientversionsrichtlinie

   ![Neue Clientversionsrichtlinie](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Beispiel***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Clientversionsrichtlinie

   ![Clientversionsrichtlinie abrufen](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Beispiel***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter Clientversionsrichtlinien

   ![Clientversionsrichtlinie löschen](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Beispiel***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Clientversionsrichtlinie

   ![Aktualisieren der Clientversionsrichtlinie](./media/clientversionpolicy-5.png)

- **Anmerkung 1 – Ergebnis**

    Diese Anmerkung auf dem Bild gibt ein Ergebnis an, d. h. die Daten, die abgerufen und angezeigt werden.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Beispiel***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Anmerkung 2 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. die Details der Clientversionsrichtlinienregeln abzurufen.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Beispiel***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Anmerkung 3 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. eine neue Clientversionsrichtlinienregel zu erstellen.

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Beispiel***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Anmerkung 4 – Option (für den Benutzer)**

    Diese Anmerkung auf dem Bild zeigt eine Option an, die der Benutzer implementieren kann, d. h. die neu erstellte Clientversionsrichtlinienregel zu übernehmen/zu speichern.

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Beispiel***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Clientversionskonfiguration

 Das Untermenüelement **CLIENTVERSIONSKONFIGURATION** gibt Informationen zu den Clients zurück, die in Skype for Business Server Umgebung unterstützt werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer bei der **CLIENTVERSIONSKONFIGURATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Clientversionskonfigurationen

   ![Clientversionskonfiguration auflisten](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Beispiel***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Clientversionskonfiguration

   ![Erstellen der Clientversionskonfiguration](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Beispiel***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Clientversionskonfiguration

   ![Clientversionskonfiguration abrufen](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Beispiel***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter Clientversionskonfigurationen

   ![Löschen der Clientversionskonfiguration](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Beispiel***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Clientversionskonfiguration

   ![Aktualisieren der Clientversionskonfiguration](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Beispiel***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Szenario 6:** Aktivieren/Deaktivieren von Clientversionskonfigurationen

![Aktivieren der Clientversionskonfiguration](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Beispiel***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Geräteaktualisierung

**DEVICE UPDATE-Regeln** werden verwendet, um Firmwareupdates Geräten zuzuordnen, die Skype for Business Telefon Edition ausführen.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **DEVICE UPDATE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Geräteupdates

   ![Geräteupdate auflisten](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Beispiel***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Szenario 2:** Löschen von Geräteupdates

   ![Löschen des Geräteupdates](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Beispiel***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Szenario 3:** Abbrechen von Geräteupdates

   ![Abbrechen der Geräteaktualisierung](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Beispiel***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Szenario 4:** Genehmigen von Geräteupdates

   ![Genehmigen des Geräteupdates](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Beispiel***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Szenario 5:** Wiederherstellen von Geräteupdates

   ![Wiederherstellen des Geräteupdates](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Beispiel***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Testgerät

Das Untermenüelement **"GERÄT TESTEN"** bietet Administratoren die Möglichkeit, Firmwareupdates zu testen, bevor diese Updates an alle Geräte in einer Organisation verteilt werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **TEST DEVICE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Testgeräte

   ![Testgerät auflisten](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Beispiel***

```powershell
 Get-CsTestDevice
```

---

> **Szenario 2:** Erstellen eines neuen Testgeräts

   ![Erstellen eines Testgeräts](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Beispiel***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Szenario 3:** Abrufen von Details zu einem ausgewählten Testgerät

   ![Testgerät abrufen](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Beispiel***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Szenario 4:** Ausgewählte Testgeräte löschen

   ![Testgerät löschen](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Beispiel***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren eines Testgeräts

   ![Aktualisieren des Testgeräts](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Beispiel***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Geräteprotokollkonfiguration

Das Untermenüelement **"DEVICE LOG CONFIGURATION"** hilft beim Verwalten des Device Update-Webdiensts, einer Skype for Business Server-Komponente, mit der Administratoren Firmwareupdates an Telefone und andere Geräte verteilen können, auf denen Skype for Business ausgeführt wird.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **DEVICE LOG CONFIGURATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Geräteprotokollkonfigurationen

   ![Geräteprotokollkonfiguration auflisten](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Beispiel***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Geräteprotokollkonfiguration

   ![Erstellen der Geräteprotokollkonfiguration](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Beispiel***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Geräteprotokollkonfiguration

   ![Abrufen der Geräteprotokollkonfiguration](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Beispiel***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Szenario 4:** Löschen ausgewählter Geräteprotokollkonfigurationen

   ![Löschen der Geräteprotokollkonfiguration](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Beispiel***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Geräteprotokollkonfiguration

   ![Aktualisieren der Geräteprotokollkonfiguration](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Beispiel***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Gerätekonfiguration

Das Untermenüelement **"GERÄTEKONFIGURATION"** hilft bei der Verwaltung von Informationen zu Verwaltungsoptionen für UC-Telefone. Diese Optionen umfassen den erforderlichen Sicherheitsmodus und ob das Telefon nach einem bestimmten Zeitraum der Inaktivität automatisch gesperrt werden soll.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **DEVICE CONFIGURATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Mobilitätsrichtlinien

   ![Gerätekonfiguration auflisten](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Beispiel***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Gerätekonfiguration

   ![Erstellen der Gerätekonfiguration](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Beispiel***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Gerätekonfiguration

   ![Abrufen der Gerätekonfiguration](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Beispiel***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Ausgewählte Gerätekonfigurationen löschen

   ![Löschen der Gerätekonfiguration](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Beispiel***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisiert eine Gerätekonfiguration

   ![Aktualisieren der Gerätekonfiguration](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Beispiel***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Mobilitätsrichtlinie

**Die MOBILITÄTSRICHTLINIE** bestimmt, ob ein Benutzer Skype for Business Mobile verwenden kann. Diese Richtlinien bestimmen ferner, ob ein Benutzer das Feature "Geschäftlich anrufen" nutzen darf, um Anrufe auf seinem Mobiltelefon unter Verwendung seiner geschäftlichen Telefonnummer anstatt seiner Mobilfunknummer zu tätigen und entgegenzunehmen. Mobilitätsrichtlinien können auch verwendet werden, um Wi-Fi Verbindungen beim Tätigen oder Empfangen von Anrufen zu einer Anforderung zu machen.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **MOBILITY POLICY** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Mobilitätsrichtlinien

   ![Mobilitätsrichtlinie auflisten](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Beispiel***

```powershell
 Get-CsMobilityPolicy
```

---

> **Szenario 2:** Erstellen einer neuen Mobilitätsrichtlinie

   ![Erstellen einer Mobilitätsrichtlinie](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Beispiel***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Mobilitätsrichtlinie

   ![Abrufen von Mobilitätsrichtlinien](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Beispiel***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Szenario 4:** Löschen ausgewählter Mobilitätsrichtlinien

   ![Mobilitätsrichtlinie löschen](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Beispiel***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Szenario 5:** Aktualisieren einer Mobilitätsrichtlinie

   ![Aktualisieren der Mobilitätsrichtlinie](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Beispiel***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Konfiguration von Pushbenachrichtigungen

Der Pushbenachrichtigungsdienst (Apple Push Notification Service und Microsoft Push Notification Service) bietet eine Möglichkeit, Benachrichtigungen über Ereignisse wie neue Chatnachrichten oder neue Voicemail an mobile Geräte wie iPhones und Windows Telefone zu senden. Diese Benachrichtigungen sind so konfiguriert, dass sie gesendet werden, auch wenn die Skype for Business-Anwendung auf diesen Geräten derzeit angehalten ist oder im Hintergrund ausgeführt wird.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer bei der KONFIGURATION von **PUSHBENACHRICHTIGUNGen** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Mobilitätsrichtlinien

   ![Konfiguration von Pushbenachrichtigungen auflisten](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Beispiel***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Pushbenachrichtigungskonfiguration

   ![Erstellen einer Pushbenachrichtigungskonfiguration](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Beispiel***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Pushbenachrichtigungskonfiguration

   ![Abrufen der Pushbenachrichtigungskonfiguration](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Beispiel***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Szenario 4:** Ausgewählte Pushbenachrichtigungskonfigurationen löschen

   ![Löschen der Pushbenachrichtigungskonfiguration](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Beispiel***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Szenario 5:** Aktualisieren einer Pushbenachrichtigungskonfiguration

   ![Aktualisieren der Pushbenachrichtigungskonfiguration](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Beispiel***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
