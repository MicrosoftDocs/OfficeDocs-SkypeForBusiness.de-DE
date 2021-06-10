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
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863196"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus lokalen Bereitstellungen nach Skype for Business Online

Nachdem Sie einen Benutzer aus der lokalen Umgebung zu Skype for Business Online verschoben haben, interagiert der Benutzer mit Skype for Business Online für seine Funktionalität. Alle lokalen Kontakte sind in Skype for Business Online verfügbar, und alle vorhandenen Besprechungen, die der Benutzer für die Zukunft organisiert hat, werden aktualisiert, sodass die Links auf Skype for Business Online verweisen. Wenn der Benutzer für Audiokonferenzen aktiviert ist, enthalten die Besprechungen auch Einwahlkoordinaten.  Um Benutzer aus einer lokalen Umgebung zu Skype for Business Online zu verschieben, verwenden Sie entweder das Cmdlet Move-CsUser oder die Skype for Business Server Systemsteuerung, die beide lokale Tools sind. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Überprüfen Sie vor dem Verschieben von Benutzern unbedingt die [Voraussetzungen,](move-users-between-on-premises-and-cloud.md#prerequisites) um Benutzer in die Cloud zu verschieben.

> [!NOTE]
> Zur Vorbereitung auf die bevorstehende Einstellung von Skype for Business Online hat Microsoft die Umstellung von Organisationen auf Teams vereinfacht. Wenn Benutzer aus der lokalen Umgebung in die Cloud verschoben werden, wird den Benutzern jetzt automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus der lokalen Umgebung werden automatisch in Teams Besprechungen konvertiert, als ob der `-MoveToTeams` Switch angegeben worden wäre, unabhängig davon, ob der Switch tatsächlich angegeben wurde.  Vor der Einstellung von Skype for Business Online können Organisationen, die Benutzer von der lokalen Umgebung zu Skype for Business Online verschieben müssen, dies in zwei Schritten erreichen, indem sie den Modus des Benutzers aktualisieren, *nachdem der Benutzer zu TeamsOnly verschoben wurde.* In naher Zukunft wird es jedoch nicht mehr möglich sein, Benutzern, die in der Cloud verwaltet werden, einen anderen Modus als TeamsOnly zuzuweisen.  
 
## <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit Move-CsUser 

Move-CsUser ist in einem lokalen powerShell-Fenster Skype for Business Verwaltungsshell verfügbar. Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch in der Microsoft 365 Organisation verfügen, wie unter [Erforderliche Administratoranmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das in beiden Umgebungen über Berechtigungen verfügt, oder Sie können ein lokales Skype for Business Server Verwaltungsshellfenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365 Konto mit der erforderlichen Administratorrolle anzugeben.

So verschieben Sie einen Benutzer mit Move-CsUser ins Internet:

- Geben Sie den Benutzer an, der mit dem Parameter "Identity" verschoben werden soll.
- Geben Sie den Parameter "-Target" mit dem Wert "sipfed.online.lync" an. <span> <span>.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen für lokale und Microsoft 365 verfügen, verwenden Sie den Parameter "-credential", um einem Konto ausreichende Berechtigungen in Microsoft 365 zur Verfügung zu stellen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 nicht in ".onmicrosoft" endet. <span> com", dann müssen Sie den Parameter -HostedMigrationOverrideUrl angeben, mit dem richtigen Wert, wie unter [Erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben.

Die folgende Cmdlet-Sequenz kann verwendet werden, um einen Benutzer in Skype for Business Online zu verschieben und dem Benutzer den Mandantenstandardmodus zuzuweisen. Es wird davon ausgegangen, dass die Microsoft 365 Anmeldeinformationen ein separates Konto ist und als Eingabe für die Get-Credential Eingabeaufforderung angegeben wird.

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

Wenn das Administratorkonto MFA (Multi-Factor Authentication) aktiviert ist, geben Sie nicht den Parameter "-Credential" an. Der Administrator wird zur Eingabe von Anmeldeinformationen aufgefordert.

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>Verschieben von Benutzern mit Skype for Business Server Systemsteuerung und Teams Admin Center

1. Öffnen Sie die Skype for Business Server Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer** aus.
3. Verwenden Sie **"Suchen",** um die Benutzer zu suchen, die Sie zu Skype for Business Online verschieben möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **"Aktion"** über der Liste **"Ausgewählte Benutzer in Skype for Business Online** verschieben" oder **"Ausgewählte Benutzer in Teams verschieben"** aus. Beide Optionen verschieben den Benutzer zunächst in den TeamsOnly-Modus, aber nach der Verschiebung können Sie einen anderen Modus zuweisen. 
5. Klicken Sie im Assistenten auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 mit einem Konto an, das auf .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **"Weiter"** und dann noch einmal auf **"Weiter",** um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Haupt-Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.
9. Öffnen Sie das Teams Admin Center, und wählen Sie im linken Navigationsbereich "Benutzer" aus. 
10. Klicken Sie in der Listenansicht auf den gewünschten Benutzer. 
11. Klicken Sie im Abschnitt mit der Meldung **Teams Upgrade auf** **"Bearbeiten".**
12. Wählen Sie im rechten Flyout den gewünschten Koexistenzmodus aus, und klicken Sie auf **"Übernehmen".**
 

## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)
