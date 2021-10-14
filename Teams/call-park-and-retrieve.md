---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie mithilfe der Anruf parken und einen Anruf in einem Anruf halten, Microsoft Teams.
ms.openlocfilehash: ad35f5bdfa6cb60a842705c150f0f511ba45cb63
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356503"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Das Parken und Abrufen von Anrufen ist ein Feature, mit dem benutzer einen Anruf in die Warteschleife setzen können. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code dann mit einer unterstützten App oder einem unterstützten Gerät verwenden, um den Anruf abzurufen. (Weitere Informationen [finden Sie unter](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) Parken eines Teams in der Telefonanlage.)

Häufige Szenarien für die Verwendung des Anruf parkens sind:

- Ein Empfangsist telefont mit einer Person, die in einer Fabrik arbeitet. Der Empfang sagt dann den Anruf und die Codenummer über das öffentliche Adresssystem an. Der Anrufbearbeiter kann dann ein Telefon Teams in der Werkshallen nehmen und den Code zum Abrufen des Anrufs eingeben.
- Ein Benutzer verdingt einen Anruf auf einem mobilen Gerät, weil der Geräteakku knapp wird. Der Benutzer kann dann den Code zum Abrufen des Anrufs von einem Telefon Teams eingeben.
- Ein Supportmitarbeiter leitet einen Kundenanruf ab und sendet eine Ankündigung auf einem Teams-Kanal für einen Experten, der den Anruf abruft und dem Kunden hilft. Ein Experte gibt den Code in das Programm ein, Teams, um den Anruf abzurufen.

Um Anrufe zu parken und abzurufen, muss ein Benutzer ein Enterprise-VoIP sein und in eine Anruf parkrichtlinien eingeschlossen sein.

> [!NOTE]
> Anruf parken und abrufen ist nur im Teams [Bereitstellungsmodus](teams-and-skypeforbusiness-coexistence-and-interoperability.md) verfügbar und wird auf IP-Telefonen Skype for Business unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anruf parkens und Abrufens

Sie müssen ein Teams sein, um das Parken und Abrufen von Anrufen zu konfigurieren. Sie ist standardmäßig deaktiviert. Sie können sie für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf parkrichtlinien erstellen. Wenn Sie dieselbe Richtlinie auf eine Gruppe von Benutzern anwenden, können diese Anrufe zwischen sich selbst parken und abrufen.

Der Bereich der Anrufabrufnummern liegt standardmäßig zwischen 10 und 99. Sie können auch einen eigenen benutzerdefinierten Bereich zwischen 10 und 9999 erstellen. Beim ersten geparkten Anruf wird ein Abholcode des Bereichsanfangs (z. B. 10) gerendert. Beim nächsten geparkten Anruf wird ein Abholcode gerendert, der um 1 erhöht wird. 11 und so weiter, bis das Ende des Bereichs als Abholcode gerendert wird. Danach beginnen die gerenderten Abholcodes erneut von Anfang an. 

Sie können ein Timeout als Anzahl von Sekunden angeben, die gewartet werden muss, bevor der geparkte Anruf abgeholt wurde. Der zulässige Bereich beträgt 120 bis 1800 Sekunden, und der Standardwert ist 300 Sekunden.

Verwenden Sie zum Festlegen des Benutzerdefinierten Parkbereichs und des Parktimeouts die New- und Set-CsTeamsCallParkPolicy-Cmdlets, die in Teams PowerShell Module 2.6.0 oder höher verfügbar sind. (Änderungen an der benutzerdefinierten Parkbereichs- und Parktimeout-Änderung lassen sich im Admin Center Teams verwalten. Beachten Sie, dass Teams Admin Center weiterhin die Standardwerte anzeigen.)

So aktivieren Sie eine Anruf parkrichtlinien:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für den **Park von**  >  **Sprachanrufen**.
2. Klicken Sie **auf der Registerkarte Richtlinien** verwalten auf **Hinzufügen**.
3. Geben Sie der Richtlinie einen Namen, und ändern Sie dann Anruf **parken zulassen** auf **Ein**. (Der Anrufabrufbereich und das Timeout können nicht angepasst werden.)

    ![Screenshot der Anruf parkrichtlinieneinstellungen](media/call-park-add-policy.png)

4. Klicken Sie auf **Speichern**.

Sie können die Richtlinie bearbeiten, indem Sie sie in der Liste auswählen und auf **Bearbeiten klicken.**

Damit die Richtlinie funktioniert, muss sie Benutzern zugewiesen werden. Sie können [die Richtlinie einzelnen Benutzern zuweisen](assign-policies.md) oder sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Anruf parkrichtlinie zu

1. Klicken Sie auf der Seite Anruf **parkrichtlinien** auf der **Registerkarte Gruppenrichtlinienzuweisung** auf **Gruppe hinzufügen**.
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann **auf Hinzufügen**.
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenzuordnungen aus.
4. Wählen **Sie unter Richtlinie auswählen** die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![Parkrichtlinien (Abbildung).](media/call-park-assign-policy-to-group.png)

5. Wählen Sie **Übernehmen aus.**

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
