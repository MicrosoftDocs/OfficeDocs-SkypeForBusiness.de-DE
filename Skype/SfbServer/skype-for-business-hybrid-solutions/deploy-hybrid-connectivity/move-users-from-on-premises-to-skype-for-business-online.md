---
title: Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.'
ms.openlocfilehash: 0731a5307523e875d2f58ca33ecfcfbd62b0c768
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250539"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online

**Zusammenfassung:** Informationen Sie zum Migrieren von benutzereinstellungen und Verschieben von Benutzern in Skype für Business Online.

Bevor Sie Nutzer tatsächlich nach Office 365 migrieren, müssen Sie zunächst sicherstellen, dass sie mit der Cloud synchronisiert sind, und Sie müssen ihnen eine Lizenz zuweisen. Dazu verwenden Sie die Office 365-Verwaltungskonsole.

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Wie Sie sicherstellen, dass ein lokales Benutzerkonto mit Office 365 synchronisiert worden ist

1. Öffnen Sie [Office 365 Administrationscenter](https://portal.office.com/) mit einem Mandanten-Admin-Konto, für Ihre Mandanten.  Mandanten Administratorkonten sollten beide den Skype für Business-Administratorrolle und der Verwaltungsrolle Benutzer (oder der globalen Administratorrolle) zum Ausführen dieser Funktion in Office 365 gewährt werden

2. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und anschließend auf **Aktive Benutzer**.

3. Klicken Sie auf **Suche nach Benutzer** und geben Sie den Namen des Benutzers ein.

4. Vergewissern Sie sich, dass der Benutzer angezeigt wird und dass sein Status **Synchronisiert mit Active Directory** ist.

    Sofern der Benutzer noch nicht synchronisiert ist, sollte die nächste automatischen Synchronisierung innerhalb der nächsten drei Stunden stattfinden. Sie können auch eine Synchronisierung früher erzwingen. Weitere Informationen finden Sie unter [Verzeichnissynchronisierung erzwingen](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).

Zuweisen, indem Sie die Lizenz in Office 365 finden Sie unter [Zuweisen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migrieren von benutzereinstellungen zu Skype für Business Online

Bevor Sie die Migration von Benutzern zum Skype für Business Online beginnen, sollten Sie die Benutzerdaten zugeordnete Konten verschoben werden soll sichern. Nicht alle Benutzerdaten werden mit dem Benutzerkonto verschoben. Informationen finden Sie unter [Sicherungs- und Wiederherstellungsanforderungen: Daten](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).

Benutzereinstellungen werden zusammen mit dem Benutzerkonto verschoben. Einige lokale Einstellungen werden jedoch nicht mit dem Benutzerkonto verschoben.

## <a name="move-pilot-users-to-skype-for-business-online"></a>Verschieben von Pilotbenutzer in Skype für Business Online

Bevor Sie beginnen, um Benutzer nach Skype für Business Online verschieben, sollten Sie verschieben einige Pilotbenutzer zu bestätigen, dass Ihre Umgebung ordnungsgemäß konfiguriert ist. Anschließend können Sie überprüfen, ob die Funktionen und Dienste erwartungsgemäß funktionieren, bevor Sie weitere Nutzer verschieben.

Um einen lokalen Benutzer in Ihrer Skype für Business Online-Mandanten zu verschieben, führen Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell, verwenden die Administratoranmeldeinformationen für Ihre Microsoft Office 365-Mandanten. Ersetzen Sie „benutzername@contoso.com“ mit den Informationen des zu verschiebenden Benutzers.

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Verschieben von Benutzern nach Skype for Business Online

Verschieben mehrerer Benutzer können mit dem Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) mit dem Parameter Filter auswählen die Benutzer mit einer bestimmten Eigenschaft, die Benutzerkonten, beispielsweise RegistrarPool zugewiesen sind. Sie können dann die zurückgegebenen Benutzer an das Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) reichen Sie wie im folgenden Beispiel dargestellt.

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

Sie können auch den OU - Parameter verwenden zum Abrufen von allen Benutzern in der angegebenen Organisationseinheit, wie im folgenden Beispiel dargestellt.

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