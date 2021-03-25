---
title: Fallstudie "Teams voice Contoso"
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Sprachfallstudie zu Teams für multinationale Unternehmen
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121303"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso-Fallstudie: Audiokonferenzen

Um ein Verständnis für Audiokonferenzen zu erhalten, was es ist, was es kostet, verfügbarkeit und wie es funktioniert Contoso überprüft &mdash; &mdash; [Audiokonferenzen in Office 365](deploy-audio-conferencing-teams-landing-page.md). 

## <a name="overview"></a>Übersicht 

Für Audiokonferenzen verwendete Contoso Telefonnummern, die innerhalb der Organisation sowie extern bekannt sind. Da Contoso diese Nummern nach Möglichkeit beibehalten wollte, überprüften sie die Informationen zum Zuweisen dedizierter und freigegebener Telefonnummern zur Audiokonferenzbrücke. 

Basierend auf ihren Recherchen hat Contoso die folgenden Entscheidungen getroffen: 

- Nur ein Teil der Bevölkerung, die regelmäßig Audiokonferenzanrufe hosten, erhält Lizenzen für Audiokonferenzen. 

- Contoso würde dedizierte Telefonnummern verwenden und ihre vorhandenen Nummern für die Verwendung mit Audiokonferenzen portieren.   

Da Contoso-Benutzer Skype for Business verwendeten und die Postfächer aller Benutzer online gespeichert sind, sind für viele Benutzer bereits Besprechungen geplant. Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are automatically updated for Contoso when they change the endbenutzer to TeamsOnly mode.  


## <a name="configuration"></a>Konfiguration

Telefonnummern, die Audiokonferenzen zugeordnet sind, werden innerhalb des Telefonsystems als Dienstnummern bezeichnet. 

- Für Standorte, die Anrufpläne verwenden, um ihre vorhandenen Telefonnummern von ihrem Telefonanbieter zu Office 365 zu portieren, hat Contoso die Schritte unter Abrufen von [Diensttelefonnummern befolgt.](getting-service-phone-numbers.md)

- Um dem Endbenutzer im technischen Pilotprojekt die Lizenz für Audiokonferenzen zuzuordnen, hat der Contoso-Administrator die Schritte unter Verwalten der Einstellungen für [Audiokonferenzen](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)für Ihre Organisation befolgt. 

- Für den Geschäftspilot und die Migration hat Contoso gruppenbasierte Lizenzierung verwendet, indem es die Schritte unter Zuweisen von Lizenzen zu Benutzern nach [Gruppenmitgliedschaft in Azure Active Directory ausführen.](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

