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
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030749"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online

**Zusammenfassung:** Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.

Bevor tatsächlich einen Benutzer in Office 365 verschieben, sollten Sie zunächst sicherstellen, dass die Benutzerkonten in der Cloud synchronisiert werden und ihnen eine Lizenz zuweisen. Dazu verwenden Sie die Office 365-Verwaltungskonsole.

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Wie Sie sicherstellen, dass ein lokales Benutzerkonto mit Office 365 synchronisiert worden ist

1. Öffnen Sie im Office 365 Administrationscenter mit einem Mandanten-Administratorkonto für Ihre Mandanten.  Mandanten Administratorkonten sollten beide den Skype für Business-Administratorrolle und der Verwaltungsrolle Benutzer (oder der globalen Administratorrolle) zum Ausführen dieser Funktion in Office 365 erteilt werden.

2. Klicken Sie im linken Navigationsbereich auf klicken Sie auf **Benutzer**, und klicken Sie dann auf **Aktive Benutzer**.

3. Klicken Sie auf **Suche nach Benutzer** und geben Sie den Namen des Benutzers ein.

4. Vergewissern Sie sich, dass der Benutzer sehen und deren Status **Synched mit Active Directory**ist.

    Sofern der Benutzer noch nicht synchronisiert ist, sollte die nächste automatischen Synchronisierung innerhalb der nächsten drei Stunden stattfinden. Sie können auch eine Synchronisierung früher erzwingen. Weitere Informationen finden Sie unter [Verzeichnissynchronisierung erzwingen](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).

Zuweisen, indem Sie die Lizenz in Office 365 finden Sie unter [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migrieren von benutzereinstellungen zu Skype für Business Online

Vor dem Migrieren von Benutzern zu Skype für Business Online sollten Sie die Benutzerdaten zugeordnete Konten verschoben werden soll sichern. Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben. Informationen finden Sie unter [Sicherungs- und Wiederherstellungsanforderungen: Daten](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).

Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.

## <a name="move-pilot-users-to-skype-for-business-online"></a>Verschieben von Pilotbenutzer in Skype für Business Online

Bevor Sie Benutzer in Skype für Business Online verschieben, sollten Sie verschieben einige Pilotbenutzer zu bestätigen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist. Anschließend können Sie überprüfen, ob die Funktionen und Dienste erwartungsgemäß funktionieren, bevor Sie weitere Nutzer verschieben.

Um einen lokalen Benutzer in Ihrer Skype für Business Online-Mandanten zu verschieben, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell, verwenden die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Mandanten. Ersetzen Sie "username@contoso.com" durch die Informationen für den Benutzer, die Sie verschieben möchten.

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Verschieben von Benutzern nach Skype for Business Online

Verschieben mehrerer Benutzer können mit dem Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) mit dem Parameter Filter auswählen die Benutzer mit einer bestimmten Eigenschaft, die Benutzerkonten, beispielsweise RegistrarPool zugewiesen sind. Sie können dann die zurückgegebenen Benutzer an das Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) reichen Sie wie im folgenden Beispiel dargestellt:

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

Sie können auch den OU - Parameter verwenden zum Abrufen von allen Benutzern in der angegebenen Organisationseinheit, wie im folgenden Beispiel dargestellt:

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a>Überprüfen von Online-Benutzereinstellungen und -Funktionen

Mit folgenden Methoden können Sie überprüfen, ob ein Benutzer erfolgreich verschoben wurde:

- Zeigen Sie in der Systemsteuerung von Skype for Business Online den Status des Benutzers an. Für lokale und Onlinebenutzer werden unterschiedliche visuelle Indikatoren verwendet.

- Führen Sie das folgende Cmdlet aus:

  ```
  Get-CsUser -Identity
  ```


