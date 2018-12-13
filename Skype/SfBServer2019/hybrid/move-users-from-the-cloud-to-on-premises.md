---
title: Verschieben Sie Benutzer aus der Cloud, um lokal
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Erfahren Sie, wie Benutzer lokal von Skype für Business Online zu verschieben.
ms.openlocfilehash: fadb3a485cac691a97f0786aea78000b6b48c344
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247665"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Verschieben Sie Benutzer aus der Cloud, um lokal 

Falls erforderlich, können Sie ein Benutzer, der zuvor von lokal in die Cloud migriert wurde (ob Skype für Business Online oder Teams nur mit) wieder zu wechseln lokal. Um Benutzer aus beiden Skype für Business Online-oder TeamsOnly wieder in einer lokalen Bereitstellung von Skype für Business Server verschieben, verwenden Sie das Cmdlet Move-CsUser oder die Skype für beide lokalen Tools sind Business Server-Systemsteuerung. Wenn Sie einen Benutzer wieder zu einer lokalen Bereitstellung verschieben, müssen Sie entscheiden, welcher Pool an den Benutzer zu verschieben.

> [!Important]
> Wenn der Benutzer bereits im TeamsOnly Modus war, und Sie eine frühere Version als Skype für Business Server 2015 mit CU8 verwenden, müssen Sie auch die TeamsOnly Modus Zuweisung von TeamsUpgradePolicy für diesen Benutzer entfernen. Lokale Benutzer müssen keinen Modus = TeamsOnly.  Nachfolgende Versionen von Skype für Business Server entfernen automatisch diese Zuordnung. Weitere Informationen finden Sie unter [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Voraussetzungen

- Die Organisation benötigen Azure AD-Connect ordnungsgemäß konfiguriert und synchronisiert werden alle relevanten Attribute für den Benutzer, wie beschrieben unter [Konfigurieren von Azure AD-Verbindung](configure-azure-ad-connect.md).
- Der Benutzer von online zurück zu lokal verschoben muss im lokalen Active Directory bereits vorhanden sein.
- Skype für hybride Business muss konfiguriert werden, wie beschrieben in [Skype für hybride Business konfigurieren](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Verschieben von Benutzern zu sichern, lokal

Nachdem Sie einen Benutzer aus der Cloud wieder auf lokal verschieben:

- Der Benutzer interagiert mit Ihrer Skype für Business Server-Bereitstellung für seine Funktionalität. 
- Alle Kontakte, die in Skype für Business Online vorhanden war, werden wieder in Skype für Business Server migriert. Derzeit werden Kontakte, die in Teams sind nicht wieder auf lokal migriert.
- Wenn der Benutzer auch Teams verwendet wird, haben sie nicht die Möglichkeit für die Zusammenarbeit mit Skype für Unternehmensbenutzer, noch werden sie mit Benutzern in Partnerorganisationen miteinander kommunizieren können.
- Besprechungen in Skype für Business Online handelt es sich *nicht* automatisch wieder auf lokal migriert. Benutzer verwenden entweder neu zu sollte ihre Besprechungen planen oder, falls gewünscht, Sie das [Migrationstool der Besprechung](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Verschieben von Benutzern mit der Move-CsUser

Move-CsUser ist von einem lokalen Skype für Business Management Shell PowerShell-Fenster zur Verfügung. Wie beschrieben in [Administratorrechte erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials), benötigen Sie ausreichende Berechtigungen in sowohl die lokale Umgebung als auch die Office 365-Mandanten. Sie können entweder ein einzelnes Konto mit Berechtigungen in beiden Umgebungen verwenden oder Sie können eine lokale Skype für Business Server-Verwaltungsshell-Fenster mit lokalen Anmeldeinformationen starten und Verwenden der `-Credential` Parameter zum Angeben von Anmeldeinformationen für ein Office 365 Konto mit den erforderlichen Office 365-Administratorrolle.

Zum Verschieben eines Benutzers auf lokal mit der Move-CsUser:

- Geben Sie den Benutzer mit dem Parameter Identity verschieben.
- Geben Sie die - Target-Parameter, mit dem vollqualifizierten Domänennamen des gewünschten lokalen Pools, die den Benutzer hostet.
- Wenn Sie in beiden auf lokalen und Office 365 nicht über ein Konto mit ausreichenden Berechtigungen verfügen, verwenden Sie den - Credential-Parameter zum Angeben eines Kontos mit ausreichenden Berechtigungen in Office 365.
- Wenn das Konto mit Berechtigungen in Office 365 nicht in "on.microsoft.com" endet, müssen Sie den HostedMigrationOverrideUrl - Parameter mit den richtigen Wert angeben, wie unter [administrative Anmeldeinformationen erforderlich](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Die folgende Sequenz Cmdlet zum Verschieben eines Benutzers in Skype für Business Server verwendet werden, und geht davon aus, die Office 365-Anmeldeinformationen ist ein separates Konto und als Eingabe für die Aufforderung Get-Credential angegeben.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Verschieben von Benutzern mit der Skype Business Server-Systemsteuerung

1. Öffnen Sie die Skype für Business-Serversteuerelement Systemsteuerung app.
2. Wählen Sie im linken Navigationsbereich **Benutzer**.
3. Verwenden Sie **Suchen** , um die Benutzer zu suchen, die Sie lokal wieder zurück in verschieben möchten.
4. Wählen Sie die Benutzer, und wählen Sie dann aus der Dropdownliste **Aktion** über der Liste **ausgewählte Benutzer auf lokal verschieben**.
5. Wählen Sie im Assistenten den Pool des Benutzers, der als host für den Benutzer, und klicken Sie auf **Weiter**.
6. Wenn Sie aufgefordert werden, melden Sie sich bei Office 365, mit einem Konto an, die in endet. onmicrosoft.com und über ausreichende Berechtigungen verfügt.
7. Klicken Sie auf **Weiter**, und klicken Sie dann **Weiter** noch einmal den Benutzer zu verschieben.
8. Beachten Sie, dass Statusnachrichten bezüglich Erfolg oder Fehler am oberen Rand der wichtigsten Systemsteuerung app nicht im Assistenten bereitgestellt werden.

### <a name="removing-teamsonly-mode"></a>Entfernen von TeamsOnly-Modus

Wenn Sie eine Version vor Skype für Business 2015 mit CU8 und der Benutzer wieder auf lokal im TeamsOnly Modus verschoben wird, müssen Sie die UpgradeToTeams-Instanz entfernen `TeamsUpgradePolicy` vor dem Verschieben des Benutzers lokal. Sie können eine Richtlinie mit einem anderen Modus explizit gewähren oder entfernen Sie einfach die vorhandene Richtlinie Aufgabe für diesen Benutzer die globale Richtlinie verwenden (solange die globale Richtlinie Ihres Mandanten nicht UpgradeToTeams ist).

Führen Sie das folgende Cmdlet zum Entfernen des Benutzers Zuweisung von TeamsUpgradePolicy aus einer Skype für Business Online-PowerShell-Fenster:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Alternativ zu einer anderen Instanz von TeamsUpgradePolicy zuweisen, die keinen Modus = TeamsOnly, Sie können den Namen der gewünschten Instanz als der Wert der Parameter "PolicyName" im Cmdlet angeben. Um eine Liste der verfügbaren Instanzen von TeamsUpgradePolicy angezeigt wird, führen Sie Get-CsTeamsUpgradePolicy aus.


## <a name="see-also"></a>Siehe auch

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)