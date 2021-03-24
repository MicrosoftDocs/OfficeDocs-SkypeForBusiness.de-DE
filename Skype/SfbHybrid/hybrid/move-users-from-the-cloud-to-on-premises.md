---
title: Verschieben von Benutzern aus der Cloud in die lokale Cloud
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
description: Erfahren Sie, wie Sie Benutzer von Skype for Business Online zu lokal verschieben.
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110611"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Verschieben von Benutzern aus der Cloud in die lokale Cloud 

Bei Bedarf können Sie einen Benutzer, der zuvor aus der lokalen Cloud in die Cloud migriert wurde (unabhängig davon, ob er Skype for Business Online oder Nur Teams verwendet) zurück in die lokale Cloud verschieben. Verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Server-Systemsteuerung, die beide lokale Tools sind, um Benutzer aus dem Skype for Business Online- oder TeamsOnly-Modus zurück in eine lokale Bereitstellung von Skype for Business Server zu verschieben. Wenn Sie einen Benutzer wieder in eine lokale Bereitstellung verschieben, müssen Sie entscheiden, in welchen Pool der Benutzer umziehen soll.

> [!Important]
> Wenn sich der Benutzer zuvor im TeamsOnly-Modus befindet und Sie eine frühere Version als Skype for Business Server 2015 mit CU8 verwenden, müssen Sie auch die TeamsOnly-Moduszuweisung von TeamsUpgradePolicy für diesen Benutzer entfernen. Lokale Benutzer dürfen nicht über mode= TeamsOnly verfügen.  Nachfolgende Versionen von Skype for Business Server entfernen diese Zuordnung automatisch. Weitere Informationen finden Sie unter [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Voraussetzungen

- Die Organisation muss Azure AD Connect ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Configure Azure AD Connect beschrieben.](configure-azure-ad-connect.md)
- Der Benutzer, der von online zurück zu lokal verschoben wird, muss bereits im lokalen Active Directory vorhanden sein.
- Skype for Business hybrid muss konfiguriert werden, wie unter [Configure Skype for Business hybrid beschrieben.](configure-federation-with-skype-for-business-online.md)

## <a name="moving-users-back-to-on-premises"></a>Verschieben von Benutzern zurück zu lokal

Sobald Sie einen Benutzer aus der Cloud zurück in die lokale Cloud verschieben:

- Der Benutzer interagiert mit Ihrer Skype for Business Server-Bereitstellung für seine Funktionalität. 
- Alle Kontakte, die in Skype for Business Online oder Teams vorhanden waren, werden zu Skype for Business Server migriert. Die beiden Kontaktgruppen werden zusammengeführt und dann wieder zu lokal migriert.  Darüber hinaus verbleiben Kontakte, die in Teams bereits vorhanden sind, in Teams.
- Wenn der Benutzer auch Teams verwendet, kann er weder mit Skype for Business-Benutzern zusammenarbeiten noch mit Benutzern in Verbundorganisationen kommunizieren.
- Besprechungen in Skype for Business Online *werden nicht* automatisch wieder zu lokal migriert. Benutzer sollten ihre Besprechungen neu terminieren oder, falls gewünscht, das Tool für die [Besprechungsmigration verwenden.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)

### <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit Move-CsUser

Move-CsUser ist über ein lokales Skype for Business Management Shell PowerShell-Fenster verfügbar. Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch in der Clouddienstorganisation (Microsoft 365 oder Office 365) verfügen, wie unter Erforderliche Administratoranmeldeinformationen [beschrieben.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden oder ein lokales Skype for Business Server Management Shell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, um Anmeldeinformationen für ein `-Credential` Microsoft 365- oder Office 365-Konto mit der erforderlichen Administratorrolle anzugeben.

So verschieben Sie einen Benutzer mithilfe von Move-CsUser zu lokal:

- Geben Sie den Benutzer an, der mit dem Parameter Identity bewegt werden soll.
- Geben Sie den -Target-Parameter mit dem vollqualifizierten Domänennamen des gewünschten lokalen Pools an, der den Benutzer hosten soll.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl lokal als auch im Clouddienst verfügen (Microsoft 365 oder Office 365), verwenden Sie den Parameter -credential, um ein Konto mit ausreichenden Berechtigungen in Microsoft 365 oder Office 365 zu versorgen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 oder Office 365 nicht in "on.microsoft.com" endet, müssen Sie den Parameter -HostedMigrationOverrideUrl angeben, mit dem richtigen Wert, wie unter [Erforderliche](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)administrative Anmeldeinformationen beschrieben.

Die folgende Cmdletsequenz kann verwendet werden, um einen Benutzer zu Skype for Business Server zu verschieben, und es wird davon ausgegangen, dass die Microsoft 365- oder Office 365-Anmeldeinformationen ein separates Konto sind und als Eingabe für die Eingabeaufforderung Get-Credential werden.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Verschieben von Benutzern mit der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer aus.**
3. Verwenden **Sie Suchen,** um die Benutzer zu finden, die Sie wieder lokal verwenden möchten.
4. Wählen Sie die Benutzer aus,  und wählen Sie dann im Dropdownmenü Aktion über der Liste ausgewählte Benutzer in **lokale Verschieben aus.**
5. Wählen Sie im Assistenten den Benutzerpool aus, der den Benutzer hosten soll, und klicken Sie auf **Weiter**.
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in .onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken **Sie auf Weiter,** und klicken Sie dann **noch** einmal, um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.

### <a name="removing-teamsonly-mode"></a>Entfernen des TeamsOnly-Modus

Wenn Sie eine Frühere Version als Skype for Business 2015 mit CU8 verwenden und der Benutzer im TeamsOnly-Modus wieder in den lokalen Modus verschoben wird, müssen Sie die UpgradeToTeams-Instanz entfernen, bevor Sie den Benutzer lokal `TeamsUpgradePolicy` verschieben. Sie können einer Richtlinie entweder explizit einen anderen Modus erteilen oder einfach die vorhandene Richtlinienzuweisung für diesen Benutzer entfernen, damit er die globale Richtlinie verwenden kann (solange die globale Richtlinie Ihres Mandanten nicht UpgradeToTeams ist).

Führen Sie das folgende Cmdlet aus einem Skype for Business Online PowerShell-Fenster aus, um die Zuweisung von TeamsUpgradePolicy durch den Benutzer zu entfernen:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Alternativ können Sie zum Zuweisen einer anderen Instanz von TeamsUpgradePolicy, die nicht über mode=TeamsOnly verfügt, den Namen der gewünschten Instanz als Wert des PolicyName-Parameters im Cmdlet angeben. Führen Sie Get-CsTeamsUpgradePolicy aus, um eine Liste der verfügbaren Instanzen von TeamsUpgradePolicy zu sehen.


## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)