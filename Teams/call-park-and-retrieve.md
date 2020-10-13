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
description: Hier erfahren Sie, wie Sie in Microsoft Teams mithilfe von Parken und Abrufen einen Anruf in Wartestellung setzen.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424593"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parken und Fortsetzen von Anrufen in Microsoft Teams

Parken und Abrufen ist eine Funktion, mit der ein Nutzer einen Anruf in Wartestellung setzen kann. Wenn ein Anruf abgestellt wird, generiert der Dienst einen eindeutigen Code für den Abruf des Anrufs. Der Benutzer, der den Anruf abgestellt hat, oder eine andere Person können diesen Code dann mit einer unterstützten APP oder einem Gerät verwenden, um den Anruf abzurufen. (Weitere Informationen finden Sie unter [Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .)

Einige häufige Szenarien für die Verwendung von Call Park sind:

- Eine Empfangsdame parkt einen Anruf für jemanden, der in einer Fabrik arbeitet. Der Rezeptionist kündigt dann den Anruf und die Codenummer über das öffentliche adresssystem an. Der Benutzer, für den der Anruf ansteht, kann dann in der Factory-Etage ein Team Telefon aufnehmen und den Code zum Abrufen des Anrufs eingeben.
- Ein Benutzer parkt einen Anruf auf einem mobilen Gerät, da der Akku des Geräts knapp wird. Der Benutzer kann dann den Code eingeben, um den Anruf von einem Team-Tischtelefon abzurufen.
- Ein Supportmitarbeiter parkt einen Kundenanruf und sendet eine Ankündigung in einem Teams-Kanal, damit ein Experte den Anruf abruft und dem Kunden hilft. Ein Experte gibt den Code in Teams-Clients ein, um den Anruf abzurufen.

Zum Parken und Abrufen von Anrufen muss ein Benutzer ein Enterprise-VoIP-Benutzer sein und muss in eine Anruf Park Richtlinie aufgenommen werden.

> [!NOTE]
> Parken und Abrufen von Anrufen steht nur im [Bereitstellungsmodus für Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) zur Verfügung und wird von Skype for Business-IP-Telefonen nicht unterstützt.

## <a name="configure-call-park-and-retrieve"></a>Konfigurieren des Anruf Parks und Abrufen

Sie müssen ein Teamadministrator sein, um den Parken von Anrufen zu konfigurieren und abzurufen. Sie ist standardmäßig deaktiviert. Sie können es für Benutzer aktivieren und Benutzergruppen mithilfe der Anruf Park Richtlinie erstellen. Wenn Sie die gleiche Richtlinie auf eine Reihe von Benutzern anwenden, können Sie Anrufe unter sich selbst Parken und abrufen.

So aktivieren Sie eine Anruf Park Richtlinie

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den Richtlinien für den **VoIP**-  >  **Anruf Park**.
2. Klicken Sie auf der Registerkarte **Richtlinien verwalten** auf **Hinzufügen**.
3. Geben Sie der Richtlinie einen Namen, und wählen Sie dann "Parken **von** **anrufen zulassen** " auf ein.

    ![Screenshot der Richtlinieneinstellungen für das Parken von Anrufen](media/call-park-add-policy.png)

4. Wählen Sie **Speichern**aus.

Sie können die Richtlinie bearbeiten, indem Sie Sie in der Liste auswählen und dann auf **Bearbeiten**klicken.

Damit die Richtlinie funktioniert, muss Sie Benutzern zugewiesen werden. Sie können [die Richtlinie Benutzern einzeln zuweisen](assign-policies.md) oder Sie einer Gruppe zuweisen.

So weisen Sie einer Gruppe eine Anruf Teil Richtlinie zu

1. Klicken Sie auf der Seite **Anruf Park Richtlinien** auf der Registerkarte **Gruppenrichtlinien Zuweisung** auf **Gruppe hinzufügen**.
2. Suchen Sie nach der Gruppe, die Sie verwenden möchten, und klicken Sie dann auf **Hinzufügen**.
3. Wählen Sie einen Rang im Vergleich zu anderen Gruppenaufgaben aus.
4. Wählen Sie unter **Richtlinie auswählen**die Richtlinie aus, der Sie diese Gruppe zuweisen möchten.

    ![](media/call-park-assign-policy-to-group.png)

5. Klicken Sie auf **Anwenden**.

## <a name="related-topics"></a>Verwandte Themen

[Parken eines Anrufs in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

[Neu – CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Satz-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)