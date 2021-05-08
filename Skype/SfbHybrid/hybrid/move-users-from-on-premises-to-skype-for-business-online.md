---
title: Verschieben von Benutzern aus lokalen Bereitstellungen nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Erfahren Sie, wie Sie Benutzer zu Skype for Business Online verschieben.
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237961"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Skype for Business Online

Nachdem Sie einen Benutzer von lokal zu Skype for Business Online verschieben, interagiert der Benutzer mit Skype for Business Online für seine Funktionalität. Alle Kontakte, die lokal vorhanden waren, sind in Skype for Business Online verfügbar, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert hat, werden auf aktualisiert, sodass die Links auf Skype for Business Online verweisen. Wenn der Benutzer für Audiokonferenzen aktiviert ist, enthalten die Besprechungen auch Einwahlkoordinaten.  Um Benutzer aus einer lokalen Umgebung zu Skype for Business Online zu verschieben, verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Server-Systemsteuerung, die beide lokale Tools sind. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die Voraussetzungen, [um](move-users-between-on-premises-and-cloud.md#prerequisites) Benutzer in die Cloud zu verschieben.
 
## <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit Move-CsUser 

Move-CsUser ist über ein lokales Skype for Business Management Shell PowerShell-Fenster verfügbar. Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch in der Microsoft 365/Office 365-Organisation verfügen, wie unter Erforderliche administrative [Anmeldeinformationen beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Sie können entweder ein einzelnes Konto verwenden, das in beiden Umgebungen über Berechtigungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshellfenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, um Anmeldeinformationen für ein Microsoft 365- oder Office 365-Konto mit der erforderlichen Administratorrolle `-Credential` anzugeben.

So verschieben Sie einen Benutzer mithilfe von Move-CsUser ins Internet:

- Geben Sie den Benutzer an, der mit dem Parameter Identity bewegt werden soll.
- Geben Sie den -Target-Parameter mit dem Wert "sipfed.online.lync" an. <span> com".
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch Office 365 verfügen, verwenden Sie den Parameter -credential, um einem Konto ausreichende Berechtigungen in Office 365.
- Wenn das Konto mit Berechtigungen in Office 365 nicht in ".onmicrosoft" endet. <span> com", müssen Sie den Parameter -HostedMigrationOverrideUrl mit dem richtigen Wert angeben, wie unter [Erforderliche administratorische Anmeldeinformationen beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

Die folgende Cmdletsequenz kann verwendet werden, um einen Benutzer zu Skype for Business verschieben. Es wird davon ausgegangen, Microsoft 365 oder Office 365 ein separates Konto ist und als Eingabe für die Eingabeaufforderung Get-Credential wird.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Wenn das Administratorkonto MFA (Multi-Factor Authentication) aktiviert ist, geben Sie den Parameter -Credential nicht an. Der Administrator wird zur Eingabe von Anmeldeinformationen aufgefordert.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Verschieben von Benutzern Skype for Business Server Systemsteuerung 

1. Öffnen Sie Skype for Business Server Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer aus.**
3. Verwenden **Sie Suchen,** um die Benutzer zu finden, die Sie zu Skype for Business online verschieben möchten.
4. Wählen Sie die Benutzer aus, und  wählen Sie dann im Dropdownmenü Aktion über der Liste die Option Ausgewählte Benutzer in Skype for Business **Verschieben aus.**
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich Microsoft 365 oder Office 365 mit einem Konto an, das in .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken **Sie auf Weiter,** und klicken Sie dann **noch** einmal, um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.

## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)