---
title: Konfigurieren der intelligenten Kontaktliste in Skype for Business Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Feature "intelligente Kontaktliste" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776690"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren der intelligenten Kontaktliste in Skype for Business Clients

**Zusammenfassung:** Hier erfahren Sie, wie Sie das Feature "intelligente Kontaktliste" im Skype for Business-Client aktivieren.

Das Feature "intelligente Kontaktliste" ermöglicht die automatische Auffüllung von Kontaktlisten für die Endbenutzer. Bei der ersten Verwendung von Skype for Business werden Ihre Benutzer automatisch Ihren Vorgesetzten und andere Personen in Ihrem Team sehen. Dieses Feature ist für Microsoft 365 und Office 365 Benutzer standardmäßig aktiviert, Sie müssen dieses Feature jedoch explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinien Einstellung konfigurieren.

Beachten Sie beim Konfigurieren dieses Features Folgendes:

- Benutzer, bis zu 13, werden automatisch der Liste der intelligenten Kontakte in der folgenden Reihenfolge hinzugefügt:

  1. Manager

  2. Leitet in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen "meine Gruppe" erstellt. Die Gruppe wird automatisch mit Personen in der AD-Gruppenbeziehung des Benutzers basierend auf dem im Feld Manager aufgefüllten Benutzer Alias aufgefüllt. Beachten Sie, dass Änderungen an der AD-Gruppenmitgliedschaft nicht dazu führen, dass meine Gruppe aktualisiert wird, nachdem Sie ursprünglich aufgefüllt wurde. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe neu erstellt. 

- Wenn die automatische Kennzeichnung aktiviert ist, werden Kontakte in der Liste für Anwesenheitsänderungen markiert. Die automatische Kennzeichnung ist standardmäßig aktiviert, Sie können Sie jedoch deaktivieren. 

- Alle neuen Benutzer in der Gruppe werden darüber informiert, dass Sie der Kontaktliste hinzugefügt wurden. Benutzer können manuell neue Mitglieder zu Ihrer Gruppe meine oder zu anderen Gruppen Ihrer Wahl hinzufügen.

- Dieses Feature funktioniert nur für Benutzer, die sich zum ersten Mal anmelden. Wenn ein Benutzer sich zuvor von einem beliebigen Gerät aus angemeldet hat, beispielsweise auf einem mobilen Gerät oder einem Mac, ist das Feature für diesen Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Konfigurieren der intelligenten Kontaktliste

Sie müssen die folgenden Schritte ausführen, um die Funktion "intelligente Kontaktliste" für Ihre Benutzer zu aktivieren: 

- Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Erstellen eines Richtlinien Eintrags zum Aktivieren der Smart Contacts-Liste

Verwenden Sie das [New-CsClientPolicyEntry-](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet mit der Option EnableClientAutoPopulateWithTeam wie folgt, um einen Richtlinieneintrag zum Aktivieren des Features für die intelligente Kontaktliste zu erstellen:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Verwenden Sie als nächstes das Cmdlet " [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen wie folgt in die globale Richtlinie zu schreiben:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie können optional eine Richtlinie erstellen, um die automatische Kennzeichnung wie folgt zu deaktivieren:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Sie müssen auch den AddressBookAvailability-Parameter für die entsprechende Richtlinie auf WebSearchOnly festlegen. Weitere Informationen finden Sie unter [Sets-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Problembehandlung

Wenn die Liste der intelligenten Kontakte nicht wie erwartet funktioniert, überprüfen Sie Folgendes:

- Überprüfen Sie die Konfiguration. 

- Stellen Sie sicher, dass die Informationen zur AD-Organisation aufgefüllt werden.

- Sammeln Sie Skype for Business Clientprotokolle für einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass auf der Benutzeroberfläche des Skype for Business Clients keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann. Um die Adressbuch Konnektivität zu bestätigen, führen Sie in der Skype for Business-Client Suchleiste eine Suche nach einem Benutzer durch.

- AD DS Replikationsprobleme können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet.


