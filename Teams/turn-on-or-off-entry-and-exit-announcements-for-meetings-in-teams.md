---
title: Aktivieren oder Deaktivieren von Eingabe-und Beendigungs Ankündigungen für Besprechungen in Teams
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Der Administrator kann erfahren, wie Sie in einer Microsoft Teams-Besprechung ein-und Ausstiegs Ankündigungen aktivieren oder deaktivieren.
ms.openlocfilehash: 4e263328e0f38e1c058fd9036e22eefbfa50f6fd
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562050"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Aktivieren oder Deaktivieren von Ankündigungen bei Zu- oder Abgang für Besprechungen in Microsoft Teams

Beim Einrichten von Audiokonferenzen in Office 365 erhalten Sie eine Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die Teilnehmer zum Einwählen in eine Microsoft Teams-Besprechung verwenden. 
  
Die Konferenzbrücke nimmt einen Anruf eines Benutzers an, der sich über ein Telefon in eine Besprechung einwählt. Die Konferenzbrücke antwortet dem Anrufer mit Sprachansagen einer automatischen Telefonzentrale und kann dann, abhängig von Ihren Einstellungen, Benachrichtigungen abspielen, Anrufer auffordern, ihren Namen aufzuzeichnen und die PIN-Sicherheit einrichten. Microsoft Teams-Besprechungsorganisatoren erhalten eine PIN, mit der sie eine Besprechung starten können, falls dies über die Microsoft Teams-App nicht möglich ist. Sie können jedoch festlegen, dass zum Starten einer Besprechung keine PIN erforderlich ist.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Festlegen von Optionen für die Besprechungsteilnahme

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Administrator sein, um diese Änderungen vornehmen zu können.

1. Melden Sie sich beim Admin Center an  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

3. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

4. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen). Diese Option ist standardmäßig ausgewählt. Wenn Sie sie deaktivieren, werden Benutzer, die bereits an der Besprechung teilnehmen, nicht benachrichtigt, wenn ein Teilnehmer der Besprechung beitritt oder diese verlässt.
    
5. Unter **Einstieg/Ausstieg-Ansagetyp** wählen Sie **Namen oder Telefonnummern** oder **Töne**.

   > [!NOTE]
   > Standardmäßig können externe Teilnehmer die Telefonnummern von Einwahl Teilnehmern nicht sehen. Wenn Sie den Datenschutz dieser Telefonnummern beibehalten möchten, wählen Sie **Töne** für die **Eingabe/Exit-Ansage** aus (Dies verhindert, dass die Nummern von Teams ausgelesen werden).
    
6. Wenn Sie **Namen oder Telefonnummern** ausgewählt haben, aktivieren oder deaktivieren Sie **Anrufer zur Aufnahme ihres Namens auffordern, bevor sie an der Besprechung teilnehmen**.
    
7. Klicken Sie auf **Speichern**.

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
