---
title: Erstellen Eines Ressourcenkontos mithilfe der Microsoft 365 Admin Center
description: Wenn Sie lieber eine grafische Benutzeroberfläche verwenden möchten, können Sie mithilfe des Microsoft 365 Admin-Centers ein Ressourcenkonto für Ihre Microsoft Teams-Räume und zusammenarbeitsleisten für Microsoft Teams erstellen.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: Erstellen eines Gerätekontos, Microsoft 365 Benutzeroberfläche und Microsoft 365 Admin Center
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 5107521b6b3c3cb69ccb33df1a895edc5fe8b7d9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732014"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Erstellen Sie mithilfe Microsoft 365 Ressourcenkontos ein Microsoft 365 Admin Center

Microsoft 365 Ressourcenkonten sind Postfach- und Teams-Konten, die bestimmten Ressourcen zugeordnet sind, z. B. einem Raum, Projektor und so weiter. Diese Ressourcenkonten können automatisch mithilfe von Regeln, die Sie beim Erstellen definieren, auf Besprechungs-Einladungen antworten. Wenn Sie z. B. über eine allgemeine Ressource wie einen Konferenzraum verfügen, können Sie ein Ressourcenkonto für diesen Konferenzraum einrichten, mit dem Besprechungs-Einladungen je nach Verfügbarkeit des Kalenders automatisch akzeptiert oder ablehnen werden.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Lizenzierung

Bevor Sie ein Ressourcenkonto Microsoft 365, überprüfen Sie, welche Art von Lizenz erforderlich ist. Wenn Sie zum Buchen einer Ressource nur ein Ressourcenkonto verwenden (d. h. die Ressource zu Ihrer Besprechung einladen und die Einladung automatisch annehmen oder ablehnen lassen), müssen Sie einem Ressourcenkonto keine Lizenz zuweisen. In den folgenden Fällen müssen Sie dem Ressourcenkonto eine Lizenz zuweisen:

- **Teams Besprechung** Wenn die Ressource (z. B. eine Microsoft Teams-Räume-Konsole, eine Zusammenarbeitsleiste und so weiter) an einer Teams-Besprechung teilnehmen soll, damit die Teilnehmer sie zum Präsentieren von Video und Audio verwenden können, benötigen Sie eine Besprechungsraum-Lizenz. 
- **PSTN-Anrufe** Wenn Sie möchten, dass die Ressource Anrufe an oder von externen Telefonnummern (als "Telefon im öffentlichen Telefonnetz" oder "PSTN-Anruf" bezeichnet) anruft, benötigen Sie eine Microsoft 365 Telefonsystem- oder Microsoft 365 Business Voice-Lizenz.

Weitere Informationen zu Lizenzen für Besprechungsraum, Telefonsystem und Business Voice finden Sie unter [Microsoft Teams-Add-On-Lizenzen.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Erstellen eines Ressourcenkontos im Microsoft 365 Admin Center

1. Melden Sie sich bei ihrem Microsoft 365, indem Siehttps://admin.microsoft.com
2. Geben Sie die Administratoranmeldeinformationen für Ihren mandanten Microsoft 365 an. Dadurch werden Sie zu Ihrem Microsoft 365 Admin Center.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 Admin Center.":::
3. Navigieren Sie im Admin  Center im linken Bereich zu  Ressourcen (möglicherweise müssen Sie zuerst Alle anzeigen auswählen), und wählen Sie dann Räume & **aus.**

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 Admin Center - Ressourcen.":::
4. Wählen Sie **Ressourcenpostfach hinzufügen aus,** um ein neues Raumkonto zu erstellen. Geben Sie einen Anzeigenamen und eine E-Mail-Adresse für das Konto ein, wählen Sie **Hinzufügen** und dann Schließen **aus.** Es wird empfohlen, für alle Ressourcenkonten eine Standardisierung nach einer Benennungskonvention zu verwenden.

> [!NOTE]
> Standardmäßig werden Ressourcenkonten mit den folgenden Einstellungen eingerichtet. Wenn Sie diese ändern möchten, wählen Sie **Terminplanungsoptionen festlegen aus,** bevor Sie Schließen **auswählen.** Wenn Sie die Einstellungen später ändern möchten, navigieren Sie zu Ressourcenräume & , wählen Sie das Ressourcenkonto und dann unter Buchungsoptionen die Option  >   **Bearbeiten aus.** 
>
> - Wiederholen von Besprechungen zulassen
> - Automatisches Ablehnen von Besprechungen außerhalb der folgenden Grenzwerte
>   - Buchungsfenster (Tage): 180
>   - Maximale Dauer (Stunden): 24
> - Automatisches Annehmen von Besprechungsanfragen

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 Admin Center – Ressourcen hinzufügen.":::
5. Navigieren Sie **im Admin** Center zum  Abschnitt Benutzer, und in der Liste Aktive Benutzer wird der gerade erstellte Raum angezeigt.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 Admin Center – Aktive Benutzer sehen.":::
6. Wählen Sie den Namen des Raums aus, und auf der rechten Seite wird ein Bereich mit den Kontoeigenschaften angezeigt.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 Admin Center – Benutzereigenschaften.":::
7. Jetzt müssen Sie dem Ressourcenkonto ein Kennwort zuweisen. Im Bereich werden die Kontoeigenschaften und mehrere optionale Aktionen angezeigt. Wählen Sie unter **dem Benutzernamen das Symbol** Kennwortschlüssel zurücksetzen aus, um das Kennwort zu ändern. Deaktivieren Sie die **Option Diesen Benutzer muss sein Kennwort bei der ersten Anmeldung ändern.** Es ist nicht möglich, das Kennwort über den Anmeldevorgang des Geräts zu ändern. Wählen Sie **Zurücksetzen aus.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 Admin Center – Kennwort zurücksetzen.":::
8. Legen Sie **im Abschnitt Lizenzen** und Apps Standort auswählen auf das Land oder die Region, in dem bzw. der das Gerät installiert werden soll.  Scrollen Sie nach unten, aktivieren Sie das Kontrollkästchen neben der Lizenz, die zugewiesen werden soll (z. B. Besprechungsraum), und wählen Sie **dann Änderungen speichern aus.** Die Lizenz kann je nach Ihrer Organisation variieren.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 Admin Center – Lizenz zuweisen.":::
