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
description: Erfahren Sie, wie Sie den Anruf parken und abrufen, um einen Anruf in Microsoft Teams zu halten.
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278715"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Das Parken und Abrufen von Anrufen ist ein Feature, mit dem der Benutzer einen Anruf halten kann. Wenn ein Anruf geparkt ist, generiert der Dienst einen eindeutigen Code für den Anrufabruf. Der Benutzer, der den Anruf geparkt hat, oder eine andere Person kann diesen Code dann mit einer unterstützten App oder einem unterstützten Gerät verwenden, um den Anruf abzurufen. (Details finden [Sie unter "Parken eines Anrufs in](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) Teams".)

Einige der gängigen Szenarien für die Nutzung des Anrufparks sind:

- Ein Empfangsist gibt einen Anruf für jemanden ab, der in einer Fabrik arbeitet. Der Empfangsist sagt dann den Anruf und die Codenummer über das öffentliche Adresssystem an. Der Benutzer, für den der Anruf verwendet wird, kann dann in der Werkshallen ein Telefon in Teams abholen und den Code eingeben, um den Anruf abzurufen.
- Ein Benutzer macht einen Anruf auf einem mobilen Gerät, weil der Geräteakku knapp wird. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Teams Desk Phone abzurufen.
- Ein Supportmitarbeiter leitet einen Kundenanruf ab und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft. Ein Experte gibt den Code in die Teams-Clients ein, um den Anruf abzurufen.

Zum Parken und Abrufen von Anrufen muss ein Benutzer Enterprise-VoIP sein und in eine Anruf parkrichtlinie eingeschlossen sein.

> [!NOTE]
> Das Parken und Abrufen von Anrufen ist nur im [Bereitstellungsmodus](teams-and-skypeforbusiness-coexistence-and-interoperability.md) von Teams verfügbar und wird auf Skype for Business-IP-Telefonen nicht unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anruf parkens und abrufen

Sie müssen ein Teamadministrator sein, um das Parken und Abrufen von Anrufen zu konfigurieren. Sie ist standardmäßig deaktiviert. Sie können sie für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf parken-Richtlinie erstellen. Wenn Sie dieselbe Richtlinie auf eine Gruppe von Benutzern anwenden, können diese die Anrufe zwischen sich selbst parken und abrufen.

So aktivieren Sie eine Anruf parken-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den **Richtlinien zum**  >  **Parken von Sprachanrufen.**
2. Klicken Sie auf **der Registerkarte "Richtlinien verwalten"** auf **"Hinzufügen".**
3. Geben Sie der Richtlinie einen Namen, und ändern Sie dann "Anruf **parken zulassen" auf** **"Ein".**

    ![Screenshot der Richtlinieneinstellungen für das Parken von Anrufen](media/call-park-add-policy.png)

4. Klicken Sie auf **Speichern**.

Sie können die Richtlinie bearbeiten, indem Sie sie in der Liste auswählen und auf **"Bearbeiten" klicken.**

Damit die Richtlinie funktioniert, muss sie Benutzern zugewiesen werden. Sie können [die Richtlinie einzelnen Benutzern zuweisen](assign-policies.md) oder sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Anrufteilrichtlinie zu

1. Klicken Sie **auf der Seite "Anruf parkrichtlinien"** auf der Registerkarte **"Gruppenrichtlinienzuweisung"** auf **"Gruppe hinzufügen".**
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann auf **"Hinzufügen".**
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenzuordnungen aus.
4. Wählen **Sie unter "Richtlinie auswählen"** die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![Parkrichtlinien (Abbildung)](media/call-park-assign-policy-to-group.png)

5. Wählen Sie **"Übernehmen"** aus.

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
