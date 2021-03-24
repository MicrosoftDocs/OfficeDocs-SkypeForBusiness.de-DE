---
title: Konfigurieren der Liste intelligenter Kontakte in Skype for Business-Clients
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095799"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren der Liste intelligenter Kontakte in Skype for Business-Clients

**Zusammenfassung:** Erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.

Das Feature Smart contacts list ermöglicht die automatische Aufgesamtheit von Kontaktlisten für Ihre Endbenutzer. Bei der ersten Verwendung von Skype for Business sehen Ihre Benutzer automatisch ihren Vorgesetzten und andere Personen in ihrem Team. Dieses Feature ist standardmäßig für Microsoft 365- und Office 365-Benutzer aktiviert, Sie müssen dieses Feature jedoch explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinieneinstellung konfigurieren.

Beachten Sie beim Konfigurieren dieses Features Folgendes:

- Benutzer mit bis zu 13 Werden automatisch in der folgenden Reihenfolge zur Liste der intelligenten Kontakte hinzugefügt:

  1. Manager

  2. Directs in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe namens Meine Gruppe erstellt. Die Gruppe wird basierend auf dem im Feld Manager aufgefüllten Benutzeralias automatisch mit Personen in der AD-Gruppenbeziehung des Benutzers gefüllt. Beachten Sie, dass Änderungen an der AD-Gruppenmitgliedschaft keine Aktualisierungen für Meine Gruppe nach dem anfänglichen Aufgefüllten verursachen. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe neu erstellt. 

- Wenn die automatische Kennzeichnung aktiviert ist, werden Kontakte in der Liste für Anwesenheitsänderungen markiert. Die automatische Kennzeichnung ist standardmäßig aktiviert, Sie können sie jedoch deaktivieren. 

- Alle neuen Benutzer in der Gruppe werden darüber informiert, dass sie der Kontaktliste hinzugefügt wurden. Benutzer können ihrer Meine Gruppe oder anderen Gruppen ihrer Wahl manuell neue Mitglieder hinzufügen.

- Dieses Feature funktioniert nur für Benutzer, die sich zum ersten Mal anmelden. Wenn sich ein Benutzer zuvor von einem Beliebigen Gerät angemeldet hat , z. B. einem mobilen Gerät oder einem Mac, ist das Feature für den Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Konfigurieren von intelligenten Kontaktlisten

Zum Aktivieren des Features für die Liste intelligenter Kontakte für Ihre Benutzer müssen Sie die folgenden Schritte ausführen: 

- Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Erstellen eines Richtlinieneintrags zum Aktivieren der Liste intelligenter Kontakte

Verwenden Sie das [Cmdlet New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) mit der Option EnableClientAutoPopulateWithTeam, um einen Richtlinieneintrag zu erstellen, um das Feature Smart contacts list zu aktivieren:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Verwenden Sie als Nächstes [das Cmdlet Set-CsClientPolicy,](/powershell/module/skype/set-csclientpolicy?view=skype-ps) um die Änderungen an der globalen Richtlinie wie folgt zu schreiben:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie können optional eine Richtlinie erstellen, um die automatische Kennzeichnung wie folgt zu deaktivieren:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie müssen auch den Parameter AddressBookAvailability für die entsprechende Richtlinie auf WebSearchOnly festlegen. Weitere Informationen finden Sie unter [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Troubleshooting

Wenn die Liste der intelligenten Kontakte nicht wie erwartet funktioniert, überprüfen Sie Folgendes:

- Überprüfen Sie die Konfiguration. 

- Vergewissern Sie sich, dass die AD-Organisationsinformationen aufgefüllt werden.

- Sammeln von Skype for Business-Clientprotokollen für einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass auf der Skype for Business-Clientbenutzeroberfläche keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann. Führen Sie eine Suche nach einem Benutzer in der Skype for Business-Clientsuchleiste aus, um die Adressbuchkonnektivität zu bestätigen.

- Ad DS-Replikationsprobleme können dazu führen, dass Kontakte nicht gelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business meldet.