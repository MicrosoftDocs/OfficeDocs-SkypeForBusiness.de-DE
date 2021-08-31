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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Sie den Gastzugriff in Microsoft Teams als Office 365-Administrator aktivieren bzw. deaktivieren.
ms.openlocfilehash: 433d0f3b73da465cdfd11382889b9cd13a1e7b06
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725524"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams

> [!Note]

> Bis **Februar 2021** ist der Gastzugriff ist standardmäßig deaktiviert. Sie müssen den Gastzugriff für Teams aktivieren, bevor Administratoren oder Teambesitzer Gäste hinzufügen können. Nach dem Aktivieren des Gastzugriffs dauert es möglicherweise ein paar Stunden, bis die Änderungen wirksam werden. Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung **Wenden Sie sich an Ihren Administrator** sehen, ist wahrscheinlich der Gastzugriff nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.

> Ab **Februar 2021** wird der Gastzugriff in Microsoft Teams für Neukunden & Bestandskunden, die diese Einstellung nicht konfiguriert haben, standardmäßig aktiviert. Wenn diese Änderung implementiert ist, wird die Gastzugriffsfunktion auf Ihrem Mandanten aktiviert, sofern Sie diese nicht bereits in Microsoft Teams konfiguriert haben. Wenn Sie möchten, dass der Gastzugriff für Ihre Organisation deaktiviert bleibt, müssen Sie sich vergewissern, dass die Einstellung für den Gastzugriff auf **Aus** und nicht auf **Dienststandard** festgelegt ist.

> [!IMPORTANT]
> Das Aktivieren des Gastzugriffs hängt von den Einstellungen in Azure Active Directory, Microsoft 365, SharePoint und Teams ab. Weitere Informationen finden Sie unter [Zusammenarbeit mit Gästen in einem Team](/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Konfigurieren des Gastzugriffs im Admin Center für Teams

1. Melden Sie sich beim [Admin Center für Microsoft Teams](https://admin.teams.microsoft.com/) an.

2. Wählen Sie **Organisationsweite Einstellungen** > **Gastzugriff** aus.

3. Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **Ein** fest.

    ![Schalter "Gastzugriff zulassen" ist auf Ein festgelegt.](media/guest-access-setting.png)

4. Wählen Sie unter **Anruf**, **Besprechung** und **Messaging** je nach den Funktionen, die Sie Gastbenutzern bereitstellen möchten, **An** oder **Aus** aus.

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

    ![Einstellungen für Gastberechtigungen in Teams.](media/manage-guest-access-image1.png)

5. Klicken Sie auf **Speichern**.

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Siehe auch

[Sichere Zusammenarbeit mit Microsoft 365 einrichten](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Blockieren von Gastbenutzern aus einem bestimmten Team](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)