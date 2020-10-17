---
title: Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Hier erfahren Sie, wie Sie das Feature "Gastzugriff" in Microsoft Teams als Office 365-Administrator aktivieren oder deaktivieren.
ms.openlocfilehash: 54d7461e9e03cd22900e07aca7ad2d12712faab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508062"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams

Der Gastzugriff ist standardmäßig deaktiviert. Sie müssen den Gastzugriff für Teams aktivieren, bevor Administratoren oder Teambesitzer Gäste hinzufügen können.

Nachdem Sie den Gastzugriff aktiviert haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden. Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder der Gastzugriff nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind.

> [!IMPORTANT]
> Das Aktivieren des Gastzugriffs hängt von den Einstellungen in Azure Active Directory, Microsoft 365, SharePoint und Teams ab. Weitere Informationen finden Sie unter [zusammenarbeiten mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Konfigurieren des Gastzugriffs im Team Admin Center

1. Anmelden beim [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/).

2. Wählen Sie **Organisationsweite Einstellungen** > **Gastzugriff** aus.

3. **Aktivieren Sie "** **Gastzugriff in Microsoft Teams zulassen** ".

    ![Schalter für „Gastzugriff in Teams ermöglichen“ ist auf „An“ eingestellt ](media/set-up-guests-image1.png)

4. Wählen Sie unter **anrufen**, **Besprechungen**und nach **richten**für jede Funktion **ein** oder **aus** , je nachdem, was Sie für Gastbenutzer zulassen möchten.

      - **Private Anrufe führen**: **Aktivieren** Sie diese Einstellung, um Gästen Peer-to-Peer-Anrufe zu ermöglichen.
      - **IP-Video zulassen**: **Aktivieren** Sie diese Einstellung, damit Gäste Video in ihren Anrufen und Besprechungen verwenden dürfen.
      - **Bildschirmübertragungsmodus**: Diese Einstellung steuert die Verfügbarkeit der Bildschirmübertragung für Gastbenutzer. 
          - Legen Sie diese Einstellung auf **Deaktiviert** fest, wenn Sie möchten, dass Gäste ihren Bildschirm in Teams nicht übertragen können. 
          - Legen Sie diese Einstellung auf **Einzelne Anwendung** fest, um die Übertragung einzelner Anwendungen zu gestatten. 
          - Legen Sie diese Einstellung auf **Vollbild** fest, um die vollständige Bildschirmübertragung zuzulassen.
      - **Sofortbesprechungen zulassen**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung des Features „Sofortbesprechung“ in Microsoft Teams zu ermöglichen.
      - **Gesendete Nachrichten bearbeiten**: **Aktivieren** Sie diese Einstellung, um Gästen die Bearbeitung von zuvor gesendeten Nachrichten zu ermöglichen.
      - **Gäste können gesendete Nachrichten löschen**: **Aktivieren** Sie diese Einstellung, um Gästen das Löschen von zuvor gesendeten Nachrichten zu ermöglichen.
      - **Chat**: **Aktivieren** Sie diese Einstellung, um Gästen den Zugriff auf den Chat in Teams zu ermöglichen.
      - **Giphys in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Giphys in Unterhaltungen zu ermöglichen. Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen. Jedem Giphy wird eine Inhaltsbewertung zugewiesen.
      - **Giphy-Inhaltsbewertung**: Wählen Sie eine Bewertung aus der Dropdown-Liste aus:
          - **Alle Inhalte zulassen**: Gäste können alle Giphys in Chats einfügen, unabhängig von der Inhaltsbewertung.
          - **Moderat**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber moderat eingeschränkt.
          - **Streng**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber eingeschränkt.
      - **Memes in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Memes in Unterhaltungen zu ermöglichen.
      - **Sticker in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Stickern in Unterhaltungen zu ermöglichen. 

    ![Einstellungen von Gastberechtigungen in Teams](media/manage-guest-access-image1.png)

5. Klicken Sie auf **Speichern**.

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Weitere Informationen

[Einrichten einer sicheren Zusammenarbeit mit Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Sperren von Gastbenutzern aus einem bestimmten Team](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Satz-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)