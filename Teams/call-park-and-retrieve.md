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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie den Anrufpark verwenden und abrufen, um einen Anruf in Microsoft Teams in den Halteraum zu setzen.
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197580"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Das Parken und Abrufen von Anrufen ist ein Feature, mit dem ein Benutzer einen Anruf in den Halteraum setzen kann. Wenn ein Anruf geparkt wird, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code dann mit einer unterstützten App oder einem unterstützten Gerät verwenden, um den Anruf abzurufen. (Details finden Sie unter [Parken eines Anrufs in Teams.)](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

Einige der gängigen Szenarien für die Verwendung des Anrufparks sind:

- Ein Empfangsist parkt einen Anruf für jemanden, der in einer Fabrik arbeitet. Der Empfanger sagt dann den Anruf und die Codenummer über das öffentliche Adresssystem an. Der Benutzer, für den der Anruf verwendet wird, kann dann ein Teams-Telefon auf der Werksfläche abholen und den Code eingeben, um den Anruf abzurufen.
- Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, weil der Geräteakku nicht mehr läuft. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Teams Desk Phone abzurufen.
- Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal für einen Experten, um den Anruf abzurufen und dem Kunden zu helfen. Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.

Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP benutzer sein und in eine Anrufparkrichtlinie einbezogen werden.

> [!NOTE]
> Anrufparken und -abrufen ist nur im [Bereitstellungsmodus von Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) verfügbar und wird auf Skype for Business-IP-Telefonen nicht unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anrufparks und Abrufens

Sie müssen ein Teams-Administrator sein, um den Anrufpark zu konfigurieren und abzurufen. Sie ist standardmäßig deaktiviert. Sie können sie für Benutzer aktivieren und Benutzergruppen mithilfe der Anrufparkrichtlinie erstellen. Wenn Sie dieselbe Richtlinie auf eine Gruppe von Benutzern anwenden, können sie Anrufe untereinander parken und abrufen.

So aktivieren Sie eine Anrufparkrichtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu Richtlinien für **den**  >  **Voiceanrufpark.**
2. Klicken Sie **auf der Registerkarte** Richtlinien verwalten auf **Hinzufügen.**
3. Geben Sie der Richtlinie einen Namen, und wechseln Sie dann **anrufparken zulassen** zu **Ein.**

    ![Screenshot der Richtlinieneinstellungen für den Anrufpark](media/call-park-add-policy.png)

4. Klicken Sie auf **Speichern**.

Sie können die Richtlinie bearbeiten, indem Sie sie in der Liste auswählen und auf **Bearbeiten klicken.**

Damit die Richtlinie funktioniert, muss sie Benutzern zugewiesen werden. Sie können [die Richtlinie benutzern einzeln zuweisen](assign-policies.md) oder sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Anrufparkrichtlinie zu

1. Klicken Sie **auf der Seite Anrufparkrichtlinien** auf der Registerkarte **Gruppenrichtlinienzuordnung** auf **Gruppe hinzufügen.**
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann auf **Hinzufügen.**
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenzuordnungen aus.
4. Wählen **Sie unter Richtlinie auswählen** die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![Abbildung "Parkrichtlinien"](media/call-park-assign-policy-to-group.png)

5. Wählen Sie **Übernehmen aus.**

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)