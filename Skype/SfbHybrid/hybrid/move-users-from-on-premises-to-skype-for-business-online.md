---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
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
description: Informationen zum Migrieren von Benutzern zu Skype for Business Online.
ms.openlocfilehash: d77bef77204a2b33d8fa8001cc54e19bf447b55f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779691"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online

Nachdem Sie einen Benutzer von lokal in Skype for Business Online umgezogen haben, interagiert der Benutzer mit Skype for Business Online für seine Funktionalität. Alle Kontakte, die lokal vorhanden waren, werden in Skype for Business Online zur Verfügung stehen, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert hat, werden so aktualisiert, dass die Links auf Skype for Business Online verweisen. Wenn der Benutzer für Audiokonferenzen aktiviert ist, enthalten die Besprechungen auch Einwahl Koordinaten.  Um Benutzer aus einer lokalen Umgebung in Skype for Business Online zu migrieren, verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business Server-Systemsteuerung, beide lokale Tools. 

Lesen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen](move-users-between-on-premises-and-cloud.md#prerequisites) , um Benutzer in die Cloud zu verschieben.
 
## <a name="move-users-with-move-csuser"></a>Migrieren von Benutzern mit "CsUser" 

CsUser ist in einem lokalen Skype for Business-Verwaltungsshell PowerShell-Fenster verfügbar. Sie müssen sowohl in der lokalen Umgebung als auch in der Office 365 Organisation über ausreichende Berechtigungen verfügen, wie unter [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den `-Credential` Parameter verwenden, um Anmeldeinformationen für ein Office 365 Konto mit der erforderlichen Office 365 Administratorrolle anzugeben.

So stellen Sie einen Benutzer mithilfe von "CsUser" in "Online" ein:

- Geben Sie den zu verschiebenden Benutzer mit dem Parameter Identity an.
- Geben Sie den-target-Parameter mit dem Wert "sipfed. online. lync" an. <span>com ".
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch Office 365 verfügen, verwenden Sie den Parameter-Credential, um ein Konto mit ausreichenden Berechtigungen in Office 365 bereitzustellen.
- Wenn das Konto mit den Berechtigungen in Office 365 nicht in ". onmicrosoft" endet. <span>com ", müssen Sie den-HostedMigrationOverrideUrl-Parameter mit dem korrekten Wert angeben, wie unter" [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)"beschrieben.

Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer zu Skype for Business Online zu migrieren, und es wird davon ausgegangen, dass die Office 365 Credential ein separates Konto ist und als Eingabe für die Get-Credential-Eingabeaufforderung angegeben wird.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Wenn das Administratorkonto MFA (Multi-Factor Authentication) aktiviert ist, geben Sie den Parameter-Credential nicht an. Der Administrator wird zur Eingabe von Anmeldeinformationen aufgefordert.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Benutzer mit Skype for Business Server-Systemsteuerung migrieren 

1. Öffnen Sie die Skype for Business Server-Systemsteuerung-app.
2. Wählen Sie im linken Navigationsbereich **Benutzer**aus.
3. Verwenden Sie **Suchen** , um die Benutzer zu finden, die Sie in Skype for Business Online verschieben möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **Aktion** oberhalb der Liste die Option **ausgewählte Benutzer in Skype for Business Online verlagern**aus.
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Office 365 mit einem Konto an, das in. onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **weiter**und dann auf **weiter** , um den Benutzer zu verlagern.
8. Beachten Sie, dass Statusmeldungen bezüglich Erfolg oder Fehler oben in der Hauptsystem Steuerung-APP, nicht im Assistenten angegeben werden.

## <a name="see-also"></a>Siehe auch

[CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
