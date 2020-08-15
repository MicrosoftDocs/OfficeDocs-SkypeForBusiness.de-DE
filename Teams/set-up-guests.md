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
ms.reviewer: sbhatta
search.appverid: MET150
description: Hier erfahren Sie, wie Sie das Feature "Gastzugriff" in Microsoft Teams als Office 365-Administrator aktivieren oder deaktivieren.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9e91f51bb809b9917036dce1d074ec694cb113f
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761151"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams
===================================================

Der Gastzugriff ist standardmäßig deaktiviert. Als Microsoft 365-oder Office 365-Administrator müssen Sie den Gastzugriff für Teams aktivieren, bevor die Administratoren oder Teambesitzer Gäste hinzufügen können. Um den Gastzugriff zu aktivieren, [arbeiten Sie mit Gästen in einem Team zusammen](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Nachdem Sie den Gastzugriff aktiviert haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden. Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder der Gastzugriff nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind.

> [!IMPORTANT]
> Das Aktivieren des Gastzugriffs hängt von den Einstellungen in Azure Active Directory, Microsoft 365 oder Office 365, SharePoint Online und Teams ab. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Teams](Teams-dependencies.md).



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Konfigurieren des Gastzugriffs im Team Admin Center

1. Melden Sie sich beim Admin Center für Microsoft Teams an.

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

5. Klicken Sie auf **Speichern**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Verwenden Sie PowerShell zum Aktivieren oder Deaktivieren von Gastzugriff.

Lesen [verwenden Sie PowerShell, um den Gastzugriff zu aktivieren oder zu deaktivieren](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off).

## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
