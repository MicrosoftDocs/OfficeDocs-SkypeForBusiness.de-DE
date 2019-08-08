---
title: Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.'
ms.openlocfilehash: 17981e13c239241f050704b7c98593f95a29ab27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234237"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Konfigurieren der intelligenten Kontaktliste in Skype for Business-Clients

**Zusammenfassung:** Hier erfahren Sie, wie Sie das Feature "Smart Contacts List" im Skype for Business-Client aktivieren.

Das Feature "Smart Contacts List" ermöglicht die automatische Auffüllung von Kontaktlisten für Ihre Endbenutzer. Bei der ersten Verwendung von Skype for Business werden Ihre Benutzer automatisch Ihren Manager und andere Personen in Ihrem Team sehen. Dieses Feature ist standardmäßig für Office 365-Benutzer aktiviert, Sie müssen dieses Feature aber explizit für Ihre lokalen Benutzer aktivieren, indem Sie die Clientrichtlinien Einstellung konfigurieren.

Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:

- Benutzer, bis zu 13, werden der Liste der intelligenten Kontakte automatisch in der folgenden Reihenfolge hinzugefügt:

  1. Manager

  2. Directors in alphabetischer Reihenfolge

  3. Peers in alphabetischer Reihenfolge

- Wenn sich ein Benutzer zum ersten Mal anmeldet, wird eine neue Gruppe mit dem Namen „My Group“ erstellt. Die Gruppe wird automatisch mit Personen in der Anzeigengruppen Beziehung des Benutzers ausgefüllt, basierend auf dem im Feld Manager aufgefüllten Benutzer-Alias. Beachten Sie, dass Änderungen in Bezug auf die AD-Gruppenmitgliedschaft keine Aktualisierung der Gruppe „My Group“ zur Folge hat, nachdem diese einmal mit Benutzern gefüllt wurde. Wenn ein Benutzer einen Kontakt oder die Gruppe löscht, werden weder der Kontakt noch die Gruppe wiederhergestellt. 

- Falls die automatische Tag-Kennzeichnung aktiviert ist, werden Kontakte in der Liste markiert, sobald sich deren Anwesenheitsstatus ändert. Die automatische Kennzeichnung ist standardmäßig aktiviert, kann jedoch bei Bedarf deaktiviert werden. 

- Alle neuen Benutzer in der Gruppe erhalten eine Nachricht, dass sie zur Kontaktliste hinzugefügt wurden. Benutzer haben die Möglichkeit, neue Mitglieder manuell zur Gruppe „My Group“ oder zu anderen Gruppen ihrer Wahl hinzuzufügen.

- Diese Funktion steht Benutzern nur bei der erstmaligen Anmeldung zur Verfügung. Falls sich ein Benutzer zuvor bereits von einem anderen Gerät jeglicher Art aus angemeldet hat, z. B. von einem mobilen Gerät oder von einem Mac aus, ist die Funktion für diesen Benutzer nicht aktiviert.

## <a name="configure-smart-contacts-list"></a>Intelligente Kontaktlisten konfigurieren

Um die Funktion „Intelligente Kontaktliste“ für Ihre Benutzer zu aktivieren, müssen Sie die folgenden Schritte durchführen: 

- Erstellen Sie einen neuen CsClientPolicy-Eintrag, und fügen Sie ihn der globalen Clientrichtlinie hinzu. 

- Stellen Sie sicher, dass die Adressbuchsuche nur für die Websuche konfiguriert ist.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Einen Richtlinieneintrag zur Aktivierung der intelligenten Kontaktliste erstellen

Verwenden Sie zum Erstellen eines Richtlinien Eintrags zum Aktivieren des Features "Smart Contacts List" das Cmdlet " [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) " mit der Option "EnableClientAutoPopulateWithTeam" wie folgt:

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Verwenden Sie als nächstes das Cmdlet " [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) ", um die Änderungen an der globalen Richtlinie wie folgt zu schreiben:

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Optional können Sie eine Richtlinie erstellen, um die automatische Kennzeichnung zu deaktivieren, wie im Folgenden beschrieben:

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Außerdem müssen Sie den Parameter „AddressBookAvailability“ für die entsprechende Richtlinie auf „WebSearchOnly“ einstellen. Weitere Informationen finden Sie unter [Satz-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Problembehandlung

Sollte die intelligente Kontaktliste nicht wie erwartet funktionieren, nehmen Sie folgende Überprüfung vor:

- Überprüfen Sie die Konfiguration. 

- Stellen Sie sicher, dass die AD-Organisationsinformationen ausgefüllt sind.

- Sammeln Sie Skype for Business-Client-Logs für einen neuen Benutzer zur weiteren Analyse.

- Vergewissern Sie sich, dass auf der Skype for Business-Client-Benutzeroberfläche keine Meldung angezeigt wird, dass keine Verbindung mit dem Adressbuch hergestellt werden kann. Um die Adressbuch Konnektivität zu bestätigen, führen Sie in der Skype for Business-Client Suchleiste eine Suche nach einem Benutzer durch.

- Probleme mit der AD DS-Replikation können dazu führen, dass Kontakte nicht aufgelöst werden, wenn sich ein Benutzer zum ersten Mal bei Skype for Business anmeldet.


