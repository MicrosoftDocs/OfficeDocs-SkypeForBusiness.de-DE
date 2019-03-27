---
title: Konfigurieren von Smart Kontaktliste in Skype für die Business-clients
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Erfahren Sie, wie das Listenfeature Smart Kontakte in die Skype für Business-Client zu aktivieren.'
ms.openlocfilehash: 52de1eb889b1373dc6928c90a9e0e298f467d3fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896658"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren von Smart Kontaktliste in Skype für die Business-clients

**Zusammenfassung:** Erfahren Sie, wie das Listenfeature Smart Kontakte in die Skype für Business-Client zu aktivieren.

Das Listenfeature Smart Kontakte ermöglicht automatische Auffüllung von Kontaktlisten für die Endbenutzer. Bei der ersten Verwendung von Skype für Unternehmen, Ihre Benutzer werden automatisch finden Sie unter ihren Manager und andere Personen in ihrem Team. Dieses Feature ist standardmäßig für Office 365-Benutzer aktiviert, aber Sie müssen dieses Feature explizit durch Konfigurieren der Einstellung für die Richtlinie für Ihre lokalen Benutzer aktivieren.

Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:

- Benutzer, bis zu 13, werden automatisch der Liste Smart Kontakte in der folgenden Reihenfolge hinzugefügt:

  1. Manager

  2. Directors in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen „My Group“ erstellt. Mit Personen in der Beziehung des Benutzers AD Gruppe basierend auf den Alias des Benutzers im Feld Manager aufgefüllt wird automatisch die Gruppe aufgefüllt. Beachten Sie, dass Änderungen in Bezug auf die AD-Gruppenmitgliedschaft keine Aktualisierung der Gruppe „My Group“ zur Folge hat, nachdem diese einmal mit Benutzern gefüllt wurde. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe wiederhergestellt. 

- Falls die automatische Tag-Kennzeichnung aktiviert ist, werden Kontakte in der Liste markiert, sobald sich deren Anwesenheitsstatus ändert. Die automatische Kennzeichnung ist standardmäßig aktiviert, kann jedoch bei Bedarf deaktiviert werden. 

- Alle neuen Benutzer in der Gruppe erhalten eine Nachricht, dass sie zur Kontaktliste hinzugefügt wurden. Benutzer haben die Möglichkeit, neue Mitglieder manuell zur Gruppe „My Group“ oder zu anderen Gruppen ihrer Wahl hinzuzufügen.

- Diese Funktion steht Benutzern nur bei der erstmaligen Anmeldung zur Verfügung. Falls sich ein Benutzer zuvor bereits von einem anderen Gerät jeglicher Art aus angemeldet hat, z. B. von einem mobilen Gerät oder von einem Mac aus, ist die Funktion für diesen Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Intelligente Kontaktlisten konfigurieren

Um die Funktion „Intelligente Kontaktliste“ für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte durchführen: 

- Erstellen Sie einen neuen Eintrag CsClientPolicy und globale Clientrichtlinie hinzugefügt. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Einen Richtlinieneintrag zur Aktivierung der intelligenten Kontaktliste erstellen

So erstellen Sie einen Richtlinieneintrag, um das Listenfeature Smart Kontakte aktivieren, verwenden Sie das Cmdlet " [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) " mit der Option EnableClientAutoPopulateWithTeam wie folgt:

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Im nächsten Schritt verwenden Sie das Cmdlet " [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen an der globalen Richtlinie wie folgt schreiben:

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Optional können Sie eine Richtlinie erstellen, um die automatische Kennzeichnung zu deaktivieren, wie im Folgenden beschrieben:

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Außerdem müssen Sie den Parameter „AddressBookAvailability“ für die entsprechende Richtlinie auf „WebSearchOnly“ einstellen. Weitere Informationen finden Sie unter [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Problembehandlung

Sollte die intelligente Kontaktliste nicht wie erwartet funktionieren, nehmen Sie folgende Überprüfung vor:

- Überprüfen Sie die Konfiguration. 

- Stellen Sie sicher, dass die AD-Organisationsinformationen ausgefüllt sind.

- Sammeln von Skype für Clientprotokolle Business auf einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass die Skype für Business Clientbenutzeroberfläche keine Meldung anzeigt, die zum Adressbuch keine Verbindung herstellen können. Adressbuch-Konnektivität zu bestätigen, führen Sie eine Suche für einen Benutzer in der Skype für Business Client Suchleiste.

- AD DS-Replikationsprobleme verursachen Kontakte nicht aufgelöst werden, wenn ein Benutzer zuerst bei Skype für Unternehmen anmeldet.


