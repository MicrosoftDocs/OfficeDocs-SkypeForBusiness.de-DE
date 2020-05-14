---
title: Migrieren von Benutzern aus der Cloud in eine lokale Umgebung
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
description: Hier erfahren Sie, wie Sie Benutzer von Skype for Business Online zu lokal migrieren.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221335"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Migrieren von Benutzern aus der Cloud in eine lokale Umgebung 

Falls erforderlich, können Sie einen Benutzer, der zuvor von lokal in die Cloud migriert wurde (unabhängig davon, ob Sie Skype for Business Online oder nur Teams verwenden) wieder in den lokalen Standort versetzen. Um Benutzer aus dem Skype for Business Online-oder TeamsOnly-Modus wieder in eine lokale Bereitstellung von Skype for Business Server zu versetzen, verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business Server-Systemsteuerung, beide lokale Tools. Wenn Sie einen Benutzer wieder in eine lokale Bereitstellung zurückversetzen, müssen Sie entscheiden, in welchen Pool der Benutzer zu migrieren ist.

> [!Important]
> Wenn sich der Benutzer zuvor im TeamsOnly-Modus befand und Sie eine frühere Version als Skype for Business Server 2015 mit ku8 verwenden, müssen Sie auch die TeamsOnly-Modus-Zuweisung von TeamsUpgradePolicy für diesen Benutzer entfernen. Lokale Benutzer dürfen nicht über Mode = TeamsOnly verfügen.  In nachfolgenden Versionen von Skype for Business Server wird diese Zuordnung automatisch entfernt. Weitere Informationen finden Sie unter [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Voraussetzungen

- Die Organisation muss Azure AD Verbindung ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [configure Azure AD Connect](configure-azure-ad-connect.md)beschrieben.
- Der Benutzer, der von Online wieder in ein lokales Objekt verschoben wird, muss bereits in der lokalen Active Directory vorhanden sein.
- Skype for Business Hybrid muss konfiguriert sein, wie unter [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md)beschrieben.

## <a name="moving-users-back-to-on-premises"></a>Verschieben von Benutzern zurück zu lokal

Nachdem Sie einen Benutzer aus der Cloud wieder in den lokalen Standort zurückversetzen:

- Der Benutzer interagiert mit der Skype for Business Server-Bereitstellung für seine Funktionalität. 
- Alle Kontakte, die in Skype for Business Online oder Teams vorhanden waren, werden zu Skype for Business Server migriert. Die beiden Kontaktgruppen werden zusammengeführt und anschließend wieder zu lokal migriert.  Darüber hinaus verbleiben Kontakte, die in Microsoft Teams bereits vorhanden sind, in Microsoft Teams.
- Wenn der Benutzer auch Teams verwendet, können diese nicht mit Skype for Business-Benutzern zusammenarbeiten und nicht mit Benutzern in Verbundorganisationen kommunizieren.
- Besprechungen in Skype for Business Online werden *nicht* automatisch zurück zu lokal migriert. Benutzer sollten entweder Ihre Besprechungen neu planen oder, falls gewünscht, das [Migrations Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)für die Besprechung verwenden.

### <a name="move-users-with-move-csuser"></a>Migrieren von Benutzern mit "CsUser"

CsUser ist in einem lokalen Skype for Business-Verwaltungsshell PowerShell-Fenster verfügbar. Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch in der Cloud-Dienstorganisation (Microsoft 365 oder Office 365) verfügen, wie unter [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das über Berechtigungen in beiden Umgebungen verfügt, oder Sie können ein lokales Skype for Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365-oder Office 365-Konto mit der erforderlichen Administratorrolle anzugeben.

So stellen Sie einen Benutzer mithilfe von "CsUser" lokal zur Verschiebung ein:

- Geben Sie den zu verschiebenden Benutzer mit dem Parameter Identity an.
- Geben Sie den-target-Parameter mit dem vollqualifizierten Domänennamen des gewünschten lokalen Pools an, in dem der Benutzer gehostet wird.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl im lokalen als auch im clouddienst (Microsoft 365 oder Office 365) verfügen, verwenden Sie den Parameter-Credential, um ein Konto mit ausreichenden Berechtigungen in Microsoft 365 oder Office 365 bereitzustellen.
- Wenn das Konto mit den Berechtigungen in Microsoft 365 oder Office 365 nicht in "on.Microsoft.com" endet, müssen Sie den-HostedMigrationOverrideUrl-Parameter mit dem korrekten Wert wie unter " [erforderliche administrative Anmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)" beschrieben angeben.

Die folgende Cmdlet-Sequenz kann zum Umstellen eines Benutzers in Skype for Business Server verwendet werden, und es wird davon ausgegangen, dass die Anmeldeinformationen von Microsoft 365 oder Office 365 ein separates Konto sind und als Eingabe für die Eingabeaufforderung Get-Credential angegeben werden.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Migrieren von Benutzern mit der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung-app.
2. Wählen Sie im linken Navigationsbereich **Benutzer**aus.
3. Verwenden Sie " **Suchen** ", um nach den Benutzern zu suchen, die Sie wieder lokal zurücksetzen möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann im Dropdownmenü **Aktion** oberhalb der Liste die Option **ausgewählte Benutzer in lokal verlagern**aus.
5. Wählen Sie im Assistenten den Benutzerpool aus, der als Host für den Benutzer verwendet werden soll, und klicken Sie auf **weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in. onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **weiter**und dann auf **weiter** , um den Benutzer zu verlagern.
8. Beachten Sie, dass Statusmeldungen bezüglich Erfolg oder Fehler oben in der Hauptsystem Steuerung-APP, nicht im Assistenten angegeben werden.

### <a name="removing-teamsonly-mode"></a>Entfernen des TeamsOnly-Modus

Wenn Sie eine ältere Version als Skype for Business 2015 mit ku8 verwenden und der Benutzer wieder ins lokale in den TeamsOnly-Modus verschoben wird, müssen Sie die UpgradeToTeams-Instanz entfernen, `TeamsUpgradePolicy` bevor Sie den Benutzer lokal verschieben. Sie können eine Richtlinie entweder explizit mit einem anderen Modus erteilen oder einfach die vorhandene Richtlinienzuweisung für diesen Benutzer entfernen, um die globale Richtlinie zu verwenden (solange die globale Richtlinie des Mandanten nicht UpgradeToTeams ist).

Um die Zuordnung des Benutzers zu TeamsUpgradePolicy zu entfernen, führen Sie das folgende Cmdlet aus einem Skype for Business Online PowerShell-Fenster aus:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Alternativ können Sie den Namen der gewünschten Instanz als Wert des Parameters "PolicyName" im Cmdlet angeben, um eine weitere Instanz von TeamsUpgradePolicy zuzuweisen, die nicht über Mode = TeamsOnly verfügt. Um eine Liste der verfügbaren Instanzen von TeamsUpgradePolicy anzuzeigen, führen Sie Get-CsTeamsUpgradePolicy aus.


## <a name="see-also"></a>Siehe auch

[CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
