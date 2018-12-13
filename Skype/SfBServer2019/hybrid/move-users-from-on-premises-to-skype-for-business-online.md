---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Erfahren Sie, wie Benutzer in Skype für Business Online zu verschieben.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243997"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online

Nachdem Sie einen Benutzer aus der lokalen in Skype für Business Online verschieben, interagiert der Benutzer mit Skype für Business Online für seine Funktionalität. Alle Kontakte, die lokalen vorhanden war, werden in Skype für Business Online verfügbar sein, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert werden so zeigen Sie die Links zu Skype für Business Online auf aktualisiert. Wenn der Benutzer für Audiokonferenzen aktiviert ist, werden die Besprechungen auch Zugriffsnummer für Einwahl Koordinaten enthalten.  Um Benutzer aus einer lokalen Umgebung zu Skype für Business Online zu verschieben, verwenden Sie das Cmdlet Move-CsUser oder die Skype für beide lokalen Tools sind Business Server-Systemsteuerung. 

Werden Sie vor dem Verschieben alle Benutzer, überprüfen Sie die [erforderlichen Komponenten](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in der Cloud zu verschieben.
 
## <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit der Move-CsUser 

Move-CsUser ist von einem lokalen Skype für Business Management Shell PowerShell-Fenster zur Verfügung. Wie beschrieben in [Administratorrechte erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials), benötigen Sie ausreichende Berechtigungen in beiden der lokalen Umgebung sowie wie in der Office 365-Mandanten. Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden oder Sie können eine lokale Skype für Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und Verwenden der `-Credential` Parameter zum Angeben von Anmeldeinformationen für ein Office 365 Konto mit den erforderlichen Office 365-Administratorrolle.

Zum Verschieben eines Benutzers zu online mit der Move-CsUser:

- Geben Sie den Benutzer mit dem Parameter Identity verschieben.
- Geben Sie die - Target-Parameter mit dem Wert "sipfed.online.lync. <span>com ".
- Wenn Sie in beiden auf lokalen und Office 365 nicht über ein Konto mit ausreichenden Berechtigungen verfügen, verwenden Sie den - Credential-Parameter zum Angeben eines Kontos mit ausreichenden Berechtigungen in Office 365.
- Wenn das Konto mit Berechtigungen in Office 365 nicht in "on.microsoft. endet <span>com ", und klicken Sie dann HostedMigrationOverrideUrl - Angabe des Parameters, mit dem richtigen Wert müssen wie unter [administrative Anmeldeinformationen erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Die folgende Sequenz Cmdlet zum Verschieben eines Benutzers in Skype für Business Online verwendet werden, und geht davon aus, die Office 365-Anmeldeinformationen ist ein separates Konto und als Eingabe für die Aufforderung Get-Credential angegeben.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a>Verschieben von Benutzern mit Skype Business Server-Systemsteuerung 

1. Öffnen Sie die Skype für Business-Serversteuerelement Systemsteuerung app.
2. Wählen Sie im linken Navigationsbereich **Benutzer**.
3. Verwenden Sie **Suchen** , um die Benutzer zu suchen, die Sie in Skype für Business Online verschieben möchten.
4. Wählen Sie die Benutzer, und wählen Sie dann aus der Dropdownliste **Aktion** über der Liste **ausgewählte Benutzer in Skype für Business Online zu verschieben**.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie aufgefordert werden, melden Sie sich bei Office 365, mit einem Konto an, die in endet. onmicrosoft.com und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **Weiter**, und klicken Sie dann **Weiter** noch einmal den Benutzer zu verschieben.
8. Beachten Sie, dass Statusnachrichten bezüglich Erfolg oder Fehler am oberen Rand der wichtigsten Systemsteuerung app nicht im Assistenten bereitgestellt werden.

## <a name="see-also"></a>Siehe auch

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)