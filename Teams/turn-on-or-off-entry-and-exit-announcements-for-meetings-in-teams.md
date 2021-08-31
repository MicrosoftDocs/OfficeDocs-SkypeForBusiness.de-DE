---
title: Aktivieren oder Deaktivieren der Ankündigung von Zu- und Abgängen für Besprechungen in Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Administratoren können in einer Besprechung erfahren, wie Sie Ankündigungen bei Zu- und Abgang aktivieren Microsoft Teams können.
ms.openlocfilehash: 6a939495c3fe537873b464064656fc529719457f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728864"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams

Wenn Sie Audiokonferenzen in Microsoft 365 oder Office 365 einrichten, erhalten Sie eine Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die Teilnehmer zum Einwählen in eine Microsoft Teams-Besprechung verwenden.
  
Die Konferenzbrücke nimmt einen Anruf eines Benutzers an, der sich über ein Telefon in eine Besprechung einwählt. Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten. Microsoft Teams-Besprechungsorganisatoren erhalten eine PIN, mit der sie eine Besprechung starten können, falls dies über die Microsoft Teams-App nicht möglich ist. Sie können jedoch festlegen, dass zum Starten einer Besprechung keine PIN erforderlich ist.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Festlegen von Optionen für die Besprechungsteilnahme

![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Melden Sie sich beim Admin Center an.

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

3. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen).

4. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen). Diese Option ist standardmäßig ausgewählt. Wenn Sie sie deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.

5. Unter **Einstieg/Ausstieg-Ansagetyp** wählen Sie **Namen oder Telefonnummern** oder **Töne**.

   > [!NOTE]
   > Standardmäßig können externe Teilnehmer die Telefonnummern der einwählten Teilnehmer nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).

6. Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, aktivieren oder deaktivieren Sie **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**.

7. Klicken Sie auf **Speichern**.

## <a name="want-to-know-more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)