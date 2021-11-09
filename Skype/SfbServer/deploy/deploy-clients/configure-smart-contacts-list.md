---
title: Konfigurieren einer intelligenten Kontaktliste in Skype for Business Clients
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Erfahren Sie, wie Sie das Feature "Intelligente Kontaktliste" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: 422972f017a1604312f1e6b75bbe18bb4c5cbc87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860902"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren einer intelligenten Kontaktliste in Skype for Business Clients

**Zusammenfassung:** Erfahren Sie, wie Sie das Feature "Intelligente Kontaktliste" im Skype for Business-Client aktivieren.

Das Feature "Intelligente Kontaktliste" ermöglicht die automatische Auffüllung von Kontaktlisten für Ihre Endbenutzer. Bei der ersten Verwendung von Skype for Business sehen Ihre Benutzer automatisch ihren Vorgesetzten und andere Personen in ihrem Team. Dieses Feature ist standardmäßig für Microsoft 365 und Office 365 Benutzer aktiviert. Sie müssen dieses Feature jedoch explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinieneinstellung konfigurieren.

Beachten Sie beim Konfigurieren dieses Features Folgendes:

- Bis zu 13 Benutzer werden automatisch in der folgenden Reihenfolge zur Liste der intelligenten Kontakte hinzugefügt:

  1. Manager

  2. Leitet in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen "Meine Gruppe" erstellt. Die Gruppe wird automatisch mit Personen in der AD-Gruppenbeziehung des Benutzers aufgefüllt, basierend auf dem Benutzeralias, der im Feld "Manager" ausgefüllt ist. Beachten Sie, dass Änderungen an der AD-Gruppenmitgliedschaft nach dem anfänglichen Auffüllen keine Aktualisierungen an "Meine Gruppe" verursachen. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe neu erstellt. 

- Wenn die automatische Markierung aktiviert ist, werden Kontakte in der Liste für Anwesenheitsänderungen markiert. Die automatische Markierung ist standardmäßig aktiviert, Sie können sie jedoch deaktivieren. 

- Alle neuen Benutzer in der Gruppe werden darüber informiert, dass sie der Kontaktliste hinzugefügt wurden. Benutzer können ihrer "Meine Gruppe" oder anderen Gruppen ihrer Wahl manuell neue Mitglieder hinzufügen.

- Dieses Feature funktioniert nur für Benutzer, die sich zum ersten Mal anmelden. Wenn sich ein Benutzer zuvor von einem beliebigen Gerät angemeldet hat , z. B. einem mobilen Gerät oder einem Mac- ist das Feature für diesen Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Konfigurieren von intelligenten Kontaktlisten

Um das Feature "Intelligente Kontaktliste" für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte ausführen: 

- Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Erstellen eines Richtlinieneintrags zum Aktivieren der Intelligenten Kontaktliste

Verwenden Sie zum Erstellen eines Richtlinieneintrags zum Aktivieren des Smart Contacts List-Features das Cmdlet ["New-CsClientPolicyEntry"](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) mit der Option "EnableClientAutoPopulateWithTeam" wie folgt:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Verwenden Sie als Nächstes das Cmdlet ["Set-CsClientPolicy",](/powershell/module/skype/set-csclientpolicy?view=skype-ps) um die Änderungen wie folgt in die globale Richtlinie zu schreiben:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie können optional eine Richtlinie erstellen, um die automatische Kennzeichnung wie folgt zu deaktivieren:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie müssen auch den AddressBookAvailability-Parameter für die entsprechende Richtlinie auf WebSearchOnly festlegen. Weitere Informationen finden Sie unter ["Set-CsClientPolicy".](/powershell/module/skype/set-csclientpolicy?view=skype-ps) 

### <a name="troubleshoot"></a>Problembehandlung

Wenn die Intelligente Kontaktliste nicht wie erwartet funktioniert, überprüfen Sie Folgendes:

- Überprüfen Sie die Konfiguration. 

- Vergewissern Sie sich, dass die AD-Organisationsinformationen ausgefüllt sind.

- Sammeln sie Skype for Business Clientprotokolle für einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass die Skype for Business Clientbenutzeroberfläche keine Meldung anzeigt, dass keine Verbindung mit dem Adressbuch hergestellt werden kann. Um die Adressbuchkonnektivität zu bestätigen, führen Sie eine Suche nach einem Benutzer in der Skype for Business Clientsuchleiste durch.

- Ad DS-Replikationsprobleme können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet.