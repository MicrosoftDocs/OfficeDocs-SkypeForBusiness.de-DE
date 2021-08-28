---
title: Parken und Fortsetzen von Anrufen in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 44884c98f3e98c15106b3d1a341eaa75b2176b0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628417"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Das Parken und Abrufen von Anrufen ist ein Feature, mit dem der Benutzer einen Anruf in die Warteschleife setzen kann. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code dann mit einer unterstützten App oder einem unterstützten Gerät verwenden, um den Anruf abzurufen. (Details [finden Sie unter Parken eines anrufs in Teams.)](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

Häufige Szenarien für die Verwendung des Anruf parkens sind:

- Ein Empfangsist telefont mit einer Person, die in einer Fabrik arbeitet. Der Empfang sagt dann den Anruf und die Codenummer über das öffentliche Adresssystem an. Der Anrufbearbeiter kann dann ein Telefon Teams in der Werkshallen nehmen und den Code zum Abrufen des Anrufs eingeben.
- Ein Benutzer verdingt einen Anruf auf einem mobilen Gerät, weil der Geräteakku knapp wird. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Telefon Teams abrufen.
- Ein Supportmitarbeiter stellt einen Kundenanruf ab und sendet eine Ankündigung auf einem Teams-Kanal an einen Experten, der den Anruf abruft und dem Kunden hilft. Ein Experte gibt den Code in das Programm ein, Teams, um den Anruf abzurufen.

Um Anrufe zu parken und abzurufen, muss ein Benutzer ein Enterprise-VoIP sein und in eine Anruf parkrichtlinien eingeschlossen sein.

> [!NOTE]
> Anruf parken und abrufen ist nur im Teams [Bereitstellungsmodus](teams-and-skypeforbusiness-coexistence-and-interoperability.md) verfügbar und wird auf IP-Telefonen Skype for Business unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anruf parkens und Abrufens

Sie müssen ein Teams sein, um das Parken und Abrufen von Anrufen zu konfigurieren. Sie ist standardmäßig deaktiviert. Sie können sie für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf parkrichtlinien erstellen. Wenn Sie dieselbe Richtlinie auf eine Gruppe von Benutzern anwenden, können diese Anrufe zwischen sich selbst parken und abrufen.

Der Bereich der Anrufabrufnummern ist vordefiniert und kann nicht geändert werden. Beim ersten geparkten Anruf wird der Abholcode 10, beim nächsten geparkten Anruf der Abholcode 11 usw. gerendert. bis 99 als Abholcode gerendert wird. Danach beginnen die gerenderten Abholcodes wieder von 10.  Wenn mehr als 89 aktive geparkte Anrufe aktiv sind, werden die gerenderten Abholcodes weiterhin über 99 hinaus erhöht, damit der 90. aktive geparkte Anruf 100 für einen Abholcode gerendert wird, der 91. aktive geparkte Anruf würde den Abholcode 101 gerendert.

So aktivieren Sie eine Anruf parkrichtlinien

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für den **Park von**  >  **Sprachanrufen**.
2. Klicken Sie **auf der Registerkarte Richtlinien** verwalten auf **Hinzufügen**.
3. Geben Sie der Richtlinie einen Namen, und ändern Sie dann Anruf **parken zulassen** auf **Ein**. (Der Anrufabrufbereich und das Timeout können nicht angepasst werden.)

    ![Screenshot der Richtlinieneinstellungen für den Anruf parken](media/call-park-add-policy.png)

4. Klicken Sie auf **Speichern**.

Sie können die Richtlinie bearbeiten, indem Sie sie in der Liste auswählen und auf **Bearbeiten klicken.**

Damit die Richtlinie funktioniert, muss sie Benutzern zugewiesen werden. Sie können [die Richtlinie einzelnen Benutzern zuweisen](assign-policies.md) oder sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Anruf parkrichtlinie zu

1. Klicken Sie auf der Seite Anruf **parkrichtlinien** auf der **Registerkarte Gruppenrichtlinienzuweisung** auf **Gruppe hinzufügen**.
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann **auf Hinzufügen**.
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenzuordnungen aus.
4. Wählen **Sie unter Richtlinie auswählen** die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![Parkrichtlinien (Abbildung)](media/call-park-assign-policy-to-group.png)

5. Wählen Sie **Übernehmen aus.**

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
