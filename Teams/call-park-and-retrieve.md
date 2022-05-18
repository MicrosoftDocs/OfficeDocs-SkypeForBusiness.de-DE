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
description: Erfahren Sie, wie Sie das Parken und Abrufen von Anrufen verwenden, um einen Anruf in Microsoft Teams zu halten.
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465446"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Das Parken und Abrufen von Anrufen ist ein Feature, mit dem ein Benutzer einen Anruf in den Haltebereich setzen kann. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code zum Abrufen von Anrufen. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code dann mit einer unterstützten App oder einem unterstützten Gerät verwenden, um den Anruf abzurufen. (Weitere Informationen finden Sie [unter Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).)

Einige der gängigen Szenarien für die Verwendung des Parkens von Anrufen sind:

- Ein Rezeptionist parkt einen Anruf für jemanden, der in einer Fabrik arbeitet. Der Empfangsmitarbeiter gibt dann den Anruf und die Codenummer über das öffentliche Adresssystem an. Der Benutzer, für den sich der Anruf richtet, kann dann ein Teams Telefon in der Werkshalle entgegen nehmen und den Code eingeben, um den Anruf abzurufen.
- Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts aus dem Netz geht. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Teams Telefonapparat abzurufen.
- Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams Kanal für einen Experten, um den Anruf abzurufen und dem Kunden zu helfen. Ein Experte gibt den Code in Teams Clients ein, um den Anruf abzurufen.

Um Anrufe zu parken und abzurufen, muss ein Benutzer ein Enterprise-VoIP Benutzer sein und in eine Richtlinie zum Parken von Anrufen einbezogen werden.

> [!NOTE]
> Das Parken und Abrufen von Anrufen ist nur im [Bereitstellungsmodus Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) verfügbar und wird auf Skype for Business IP-Telefonen nicht unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Parkens und Abrufen von Anrufen

Sie müssen ein Teams Administrator sein, um das Parken und Abrufen von Anrufen konfigurieren zu können. Sie ist standardmäßig deaktiviert. Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Richtlinie zum Parken von Anrufen erstellen. Wenn Sie dieselbe Richtlinie auf eine Gruppe von Benutzern anwenden, können diese Anrufe zwischen sich selbst parken und abrufen.

Standardmäßig liegt der Bereich der Anrufannahmenummern zwischen 10 und 99. Sie können auch einen eigenen benutzerdefinierten Bereich zwischen 10 und 9999 erstellen. Der erste geparkte Aufruf wird als Pickupcode des Anfangsbereichs (z. B. 10) gerendert. Der nächste geparkte Anruf wird mit einem um 1 erhöhten Pickup-Code gerendert. d. h. 11 usw., bis das Ende des Bereichs als Pickup-Code gerendert wird. Danach beginnen die gerenderten Pickup-Codes erneut vom Anfang des Bereichs. 

Sie können ein Timeout als Die Anzahl der Sekunden angeben, die gewartet werden müssen, bevor sie wieder klingeln, wenn der geparkte Anruf nicht abgeholt wurde. Der zulässige Bereich beträgt 120-1800 Sekunden, und der Standardwert ist 300 Sekunden.

So aktivieren Sie eine Richtlinie zum Parken von Anrufen:

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **VoIPCall-Parkrichtlinien** > .
2. Klicken Sie auf der Registerkarte " **Richtlinien verwalten** " auf **"Hinzufügen"**.
3. Geben Sie der Richtlinie einen Namen, und aktivieren Sie dann "**Parken von Anrufen zulassen****".**
4. Ändern Sie den Bereich und das Parktimeout nach Bedarf.
5. Klicken Sie auf **Speichern**.

Sie können die Richtlinie bearbeiten, indem Sie sie in der Liste auswählen und auf **"Bearbeiten"** klicken.

Damit die Richtlinie funktioniert, muss sie Benutzern zugewiesen werden. Sie können [die Richtlinie einzelnen Benutzern zuweisen](assign-policies-users-and-groups.md) oder sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Richtlinie zum Parken von Anrufen zu

1. Klicken Sie auf der Seite "Richtlinien für das **Parken von Anrufen** " auf der Registerkarte " **Gruppenrichtlinienzuweisung** " auf **"Gruppe hinzufügen"**.
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann auf **"Hinzufügen"**.
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenzuweisungen aus.
4. **Wählen Sie unter "Richtlinie auswählen**" die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![Bild "Parkrichtlinien".](media/call-park-assign-policy-to-group.png)

5. Wählen Sie **"Übernehmen" aus**.

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
