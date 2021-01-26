---
title: Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Funktion "Intelligente Kontaktliste" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805775"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients

**Zusammenfassung:** Erfahren Sie, wie Sie die Funktion "Intelligente Kontaktliste" im Skype for Business-Client aktivieren.

Das Feature "Intelligente Kontaktliste" ermöglicht die automatische Aufgesamtheit von Kontaktlisten für Ihre Endbenutzer. Bei der ersten Verwendung von Skype for Business sehen Ihre Benutzer automatisch ihren Vorgesetzten und andere Personen in ihrem Team. Dieses Feature ist für Microsoft 365- und Office 365-Benutzer standardmäßig aktiviert, Sie müssen dieses Feature jedoch explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinieneinstellung konfigurieren.

Beachten Sie beim Konfigurieren dieses Features Folgendes:

- Bis zu 13 Benutzer werden automatisch in der folgenden Reihenfolge zur Liste der intelligenten Kontakte hinzugefügt:

  1. Manager

  2. Directs in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe namens "Meine Gruppe" erstellt. Die Gruppe wird basierend auf dem im Feld "Manager" aufgefüllten Benutzeralias automatisch mit Personen in der Ad-Gruppenbeziehung des Benutzers aufgefüllt. Beachten Sie, dass Änderungen an der Ad-Gruppenmitgliedschaft keine Aktualisierungen für "Meine Gruppe" nach dem anfänglichen Aufgefüllten verursachen. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe neu erstellt. 

- Wenn die automatische Markierung aktiviert ist, werden Kontakte in der Liste für Anwesenheitsänderungen markiert. Die automatische Markierung ist standardmäßig aktiviert, Sie können sie jedoch deaktivieren. 

- Alle neuen Benutzer in der Gruppe werden darüber informiert, dass sie der Kontaktliste hinzugefügt wurden. Benutzer können ihrer Gruppe "Meine Gruppe" oder anderen Gruppen Ihrer Wahl manuell neue Mitglieder hinzufügen.

- Dieses Feature funktioniert nur für Benutzer, die sich zum ersten Mal anmelden. Wenn sich ein Benutzer zuvor von einem Beliebigen Gerät (z. B. einem mobilen Gerät oder einem Mac) angemeldet hat, ist das Feature für den Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Konfigurieren von intelligenten Kontaktlisten

Um die Funktion "Intelligente Kontaktliste" für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte ausführen: 

- Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Erstellen eines Richtlinieneintrags zum Aktivieren einer intelligenten Kontaktliste

Verwenden Sie zum Erstellen eines Richtlinieneintrags zum Aktivieren des Features "Intelligente Kontaktliste" das [Cmdlet "New-CsClientPolicyEntry"](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) mit der Option "EnableClientAutoPopulateWithTeam" wie folgt:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Verwenden Sie als Nächstes [das Cmdlet "Set-CsClientPolicy",](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) um die Änderungen wie folgt in die globale Richtlinie zu schreiben:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie können optional eine Richtlinie erstellen, um die automatische Markierung wie folgt zu deaktivieren:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie müssen auch den Parameter "AddressBookAvailability" für die entsprechende Richtlinie auf "WebSearchOnly" festlegen. Weitere Informationen finden Sie unter [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Troubleshooting

Wenn die intelligente Kontaktliste nicht wie erwartet funktioniert, überprüfen Sie Folgendes:

- Überprüfen Sie die Konfiguration. 

- Vergewissern Sie sich, dass die Informationen zur AD-Organisation ausgefüllt sind.

- Erfassen Sie Skype for Business-Clientprotokolle für einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass auf der Skype for Business-Clientbenutzeroberfläche keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann. Um die Adressbuchkonnektivität zu bestätigen, führen Sie in der Skype for Business-Clientsuchleiste eine Suche nach einem Benutzer aus.

- Probleme mit der AD DS-Replikation können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business meldet.


