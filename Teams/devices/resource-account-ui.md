---
title: Erstellen eines Ressourcenkontos mit dem Microsoft 365 Admin Center
description: Wenn Sie eine grafische Benutzeroberfläche verwenden möchten, können Sie ein Ressourcenkonto für Ihre Microsoft Teams-Chatrooms und-Zusammenarbeits leisten für Microsoft Teams mit dem Microsoft 365 Admin Center erstellen.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: Erstellen eines Geräte Kontos, Microsoft 365 UI, Microsoft 365 Admin Center
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268022"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Erstellen eines Microsoft 365-Ressourcenkontos mit dem Microsoft 365 Admin Center

Microsoft 365-Ressourcenkonten sind Postfach-und Teams-Konten, die für bestimmte Ressourcen dediziert sind, beispielsweise einen Raum, einen Projektor usw. Diese Ressourcenkonten können mithilfe von Regeln, die Sie bei der Erstellung definieren, automatisch auf Besprechungseinladungen Antworten. Wenn Sie beispielsweise über eine gemeinsame Ressource wie einen Konferenzraum verfügen, können Sie ein Ressourcenkonto für diesen Konferenzraum einrichten, in dem die Besprechungseinladungen je nach Verfügbarkeit des Kalenders automatisch akzeptiert oder abgelehnt werden.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Lizenzierung

Bevor Sie ein Microsoft 365-Ressourcenkonto erstellen, überprüfen Sie, welche Art von Lizenz erforderlich ist. Wenn Sie nur ein Ressourcenkonto verwenden, um eine Ressource zu buchen (das heißt, die Ressource zu Ihrer Besprechung einladen und die Einladung automatisch annehmen oder ablehnen), müssen Sie einem Ressourcenkonto keine Lizenz zuweisen. Sie müssen dem Ressourcenkonto in den folgenden Situationen eine Lizenz zuweisen:

- **Teams-Besprechung** Wenn Sie möchten, dass die Ressource (beispielsweise eine Microsoft Teams rooms-Konsole, eine Zusammenarbeits Leiste usw.) an einer Teambesprechung teilnimmt, damit Sie von Teilnehmern Video-und Audiofunktionen bereitstellen können, benötigen Sie eine Lizenz für einen Besprechungsraum. 
- **PSTN-Anrufe** Wenn Sie möchten, dass die Ressource Anrufe an oder von externen Telefonnummern (so genannte Public Switched Telephone Network oder PSTN-Anruf) tätigen oder empfangen kann, benötigen Sie ein Microsoft 365-Telefon System oder eine Microsoft 365 Business Voice-Lizenz.

Weitere Informationen zu Besprechungsräumen, Telefon System und Business-VoIP-Lizenzen finden Sie unter [Add-on-Lizenzen für Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Erstellen eines Ressourcenkontos im Microsoft 365 Admin Center

1. Wenn Sie sich bei Microsoft 365 anmelden, besuchen Siehttps://admin.microsoft.com
2. Geben Sie die Administratoranmeldeinformationen für Ihren Microsoft 365-Mandanten an. Damit gelangen Sie zu Ihrem Microsoft 365 Admin Center.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 Admin Center":::
3. Navigieren Sie im Admin Center zu **Ressourcen** im linken Bereich (möglicherweise müssen Sie alle zuerst **anzeigen** auswählen), und wählen Sie dann **Räume & Equipment**aus.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 Admin Center – Ressourcen":::
4. Wählen Sie **Ressourcenpostfach hinzufügen** aus, um ein neues Raum Konto zu erstellen. Geben Sie einen Anzeigenamen und eine e-Mail-Adresse für das Konto ein, wählen Sie **Hinzufügen**und dann **Schließen**aus. Wir empfehlen, dass Sie für alle Ressourcenkonten eine Benennungskonvention standardisieren.

> [!NOTE]
> Standardmäßig sind Ressourcenkonten mit den folgenden Einstellungen eingerichtet. Wenn Sie Sie ändern möchten, wählen Sie **Planungsoptionen festlegen** aus, bevor Sie **Schließen**auswählen. Wenn Sie Sie später ändern möchten, navigieren Sie zu **Ressourcen**  >  **Räumen & Geräten**, wählen Sie das Ressourcenkonto aus, und wählen Sie dann unter **Buchungsoptionen**die Option **Bearbeiten** aus.
>
> - Wiederholen von Besprechungen zulassen
> - Automatisches ablehnen von Besprechungen außerhalb der folgenden Grenzwerte
>   - Buchungsfenster (Tage): 180
>   - Maximale Dauer (Stunden): 24
> - Automatische Annahme von Besprechungsanfragen

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 Admin Center – Ressourcen hinzufügen":::
5. Navigieren Sie im Admin Center zum Abschnitt **Benutzer** , und in der Liste **aktive Benutzer** wird der soeben erstellte Raum angezeigt.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 Admin Center – aktive Benutzer anzeigen":::
6. Wählen Sie den Namen des Chatrooms aus, und auf der rechten Seite wird ein Bereich mit den Kontoeigenschaften angezeigt.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 Admin Center – Benutzereigenschaften":::
7. Nun müssen Sie dem Ressourcenkonto ein Kennwort zuweisen. Im Panel werden die Kontoeigenschaften und verschiedene optionale Aktionen angezeigt. Wählen Sie unter dem Benutzernamen das Symbol **Kennwort zurücksetzen** aus, um das Kennwort zu ändern. Heben Sie die Auswahl **auf, dass dieser Benutzer sein Kennwort bei der ersten Anmeldung ändern muss**. Es ist nicht möglich, das Kennwort über das Anmeldeverfahren für Geräte zu ändern. Wählen Sie **Zurücksetzen**aus.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 Admin Center – Kennwort zurücksetzen":::
8. Legen Sie im Abschnitt **Lizenzen und apps** den **Eintrag Standort** auf das Land oder die Region, in dem das Gerät installiert wird, ein. Scrollen Sie nach unten, und aktivieren Sie das Kontrollkästchen neben der Lizenz, die zugewiesen werden soll, beispielsweise Besprechungsraum, und wählen Sie dann **Änderungen speichern**aus. Die Lizenz kann je nach Organisation unterschiedlich sein.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 Admin Center – Lizenz zuweisen":::
