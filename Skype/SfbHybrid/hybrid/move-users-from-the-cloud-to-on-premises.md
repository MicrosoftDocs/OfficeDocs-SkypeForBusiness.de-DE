---
title: Verschieben von Benutzern aus der Cloud in lokale Bereitstellungen
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
description: Erfahren Sie, wie Sie Benutzer von Teams zu lokalen Bereitstellungen verschieben.
ms.openlocfilehash: db1557c3929bdf62557e31a7fce78050569016ee
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574090"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Verschieben von Benutzern aus der Cloud in lokale Bereitstellungen 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Bei Bedarf können Sie einen Benutzer, der zuvor von der lokalen Bereitstellung zu Teams zurück zur lokalen Bereitstellung migriert wurde, verschieben. Um Benutzer aus Skype for Business Online- oder TeamsOnly-Modus zurück in eine lokale Bereitstellung von Skype for Business Server zu verschieben, verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Server Systemsteuerung, die beide lokale Tools sind. Wenn Sie einen Benutzer zurück zu einer lokalen Bereitstellung verschieben, müssen Sie entscheiden, in welchen Pool der Benutzer verschoben werden soll.

> [!Important]
> Wenn sich der Benutzer zuvor im TeamsOnly-Modus befand und Sie eine frühere Version als Skype for Business Server 2015 mit CU8 verwenden, müssen Sie auch die TeamsOnly-Moduszuweisung von TeamsUpgradePolicy für diesen Benutzer entfernen. Lokale Benutzer dürfen nicht über den Modus "TeamsOnly" verfügen.  Nachfolgende Versionen von Skype for Business Server entfernen diese Zuordnung automatisch. Weitere Informationen finden Sie unter [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Voraussetzungen

- Die Organisation muss Azure AD Verbinden ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Konfigurieren von Azure AD Verbinden](configure-azure-ad-connect.md)beschrieben.
- Der Benutzer, der von online zurück in die lokale Umgebung verschoben wird, muss bereits im lokalen Active Directory vorhanden sein.
- Skype for Business Hybrid muss konfiguriert werden, wie unter [Konfigurieren Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md)beschrieben.

## <a name="moving-users-back-to-on-premises"></a>Zurückverlagern von Benutzern zu lokalen Bereitstellungen

Sobald Sie einen Benutzer aus der Cloud zurück in die lokale Bereitstellung verschieben:

- Der Benutzer interagiert aufgrund seiner Funktionalität mit Ihrer Skype for Business Server-Bereitstellung. 
- Alle Kontakte, die in Skype for Business Online oder Teams vorhanden waren, werden zu Skype for Business Server migriert. Die beiden Sätze von Kontakten werden zusammengeführt und dann wieder zur lokalen Bereitstellung migriert.  Darüber hinaus bleiben Kontakte, die bereits in Teams vorhanden sind, in Teams.
- Wenn der Benutzer auch Teams verwendet, kann er weder mit Skype for Business Benutzern zusammenarbeiten noch mit Benutzern in Verbundorganisationen kommunizieren.
- Besprechungen in Skype for Business Online werden *nicht* automatisch zurück zu lokalen Besprechungen migriert. Benutzer sollten ihre Besprechungen entweder neu planen oder, falls gewünscht, das [Besprechungsmigrationstool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)verwenden.

### <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit Move-CsUser

Move-CsUser ist in einem lokalen Skype for Business PowerShell-Fenster der Verwaltungsshell verfügbar. Sie müssen über ausreichende Berechtigungen sowohl in der lokalen Umgebung als auch in der Clouddienstorganisation (Microsoft 365 oder Office 365) verfügen, wie unter [Erforderliche Administratoranmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben. Sie können entweder ein einzelnes Konto verwenden, das in beiden Umgebungen über Berechtigungen verfügt, oder Sie können ein lokales Skype for Business Server Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und den Parameter verwenden, `-Credential` um Anmeldeinformationen für ein Microsoft 365 oder Office 365 Konto mit der erforderlichen Administratorrolle anzugeben.

So verschieben Sie einen Benutzer mit Move-CsUser in die lokale Umgebung:

- Geben Sie den Benutzer an, der mit dem Parameter "Identity" verschoben werden soll.
- Geben Sie den Parameter "-Target" mit dem vollqualifizierten Domänennamen des gewünschten lokalen Pools an, der den Benutzer hosten soll.
- Wenn Sie nicht über ein Konto mit ausreichenden Berechtigungen sowohl im lokalen als auch im Clouddienst (Microsoft 365 oder Office 365) verfügen, verwenden Sie den Parameter "-credential", um einem Konto ausreichende Berechtigungen in Microsoft 365 oder Office 365 zur Verfügung zu stellen.
- Wenn das Konto mit Berechtigungen in Microsoft 365 oder Office 365 nicht mit "on.microsoft.com" endet, müssen Sie den Parameter "-HostedMigrationOverrideUrl" mit dem richtigen Wert angeben, wie unter [Erforderliche Administratoranmeldeinformationen](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)beschrieben.

Die folgende Cmdletsequenz kann verwendet werden, um einen Benutzer in Skype for Business Server zu verschieben. Dabei wird davon ausgegangen, dass die Microsoft 365 oder Office 365 Anmeldeinformationen ein separates Konto sind und als Eingabe für die Get-Credential Eingabeaufforderung angegeben werden.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Verschieben von Benutzern mit der Skype for Business Server Systemsteuerung

1. Öffnen Sie die Skype for Business Server Systemsteuerungs-App.
2. Wählen Sie in der linken Navigationsleiste **Benutzer** aus.
3. Verwenden Sie **"Suchen",** um die Benutzer zu finden, zu denen Sie zurückkehren möchten.
4. Wählen Sie die Benutzer aus, und wählen Sie dann aus der **Dropdownliste "Aktion"** oberhalb der Liste die Option **"Ausgewählte Benutzer lokal verschieben"** aus.
5. Wählen Sie im Assistenten den Benutzerpool aus, der den Benutzer hosten soll, und klicken Sie auf **"Weiter".**
6. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Microsoft 365 oder Office 365 mit einem Konto an, das in onmicrosoft.com endet und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **"Weiter"** und dann noch einmal auf **"Weiter",** um den Benutzer zu verschieben.
8. Beachten Sie, dass Statusmeldungen zu Erfolg oder Fehler oben in der Haupt-Systemsteuerungs-App und nicht im Assistenten bereitgestellt werden.

### <a name="removing-teamsonly-mode"></a>Entfernen des TeamsOnly-Modus

Wenn Sie eine frühere Version als Skype for Business 2015 mit CU8 verwenden und der Benutzer im TeamsOnly-Modus wieder in die lokale Umgebung verschoben wird, müssen Sie die UpgradeToTeams-Instanz entfernen, `TeamsUpgradePolicy` bevor Sie den Benutzer lokal verschieben. Sie können entweder explizit eine Richtlinie mit einem anderen Modus gewähren oder einfach die vorhandene Richtlinienzuweisung für diesen Benutzer entfernen, um die globale Richtlinie zu verwenden (solange die globale Richtlinie Ihres Mandanten kein UpgradeToTeams ist).

Um die Zuweisung von TeamsUpgradePolicy durch den Benutzer zu entfernen, führen Sie das folgende Cmdlet aus einem Skype for Business Online-PowerShell-Fenster aus:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Alternativ können Sie zum Zuweisen einer anderen Instanz von TeamsUpgradePolicy, die nicht über "mode=TeamsOnly" verfügt, den Namen der gewünschten Instanz als Wert des PolicyName-Parameters im Cmdlet angeben. Um eine Liste der verfügbaren Instanzen von TeamsUpgradePolicy anzuzeigen, führen Sie Get-CsTeamsUpgradePolicy aus.


## <a name="see-also"></a>Siehe auch

[Move-CsUser](/powershell/module/skype/move-csuser)