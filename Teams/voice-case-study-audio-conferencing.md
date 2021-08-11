---
title: 'Teams Contoso-Fallstudie: Audio conferencing (Audiokonferenz)'
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
description: 'Teams– Fallstudie für multinationale Unternehmen: Audiokonferenzen'
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25fa2e81244365d1c0c3dfcacf918f1b35a6fa71d2b619eaaa55c8aa219c310
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335795"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso-Fallstudie: Audiokonferenzen

Um ein Grundlegendes zu Audiokonferenzen zu erhalten, was dies ist, was es kostet, verfügbarkeit und wie Contoso es funktioniert, &mdash; &mdash; [überprüfte Audio conferencing (Audiokonferenz) in Office 365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Übersicht 

Für Audiokonferenzen hat Contoso Telefonnummern verwendet, die innerhalb der Organisation sowie extern bekannt sind. Da Contoso diese Nummern nach Möglichkeit pflegen wollte, überprüfte es die Informationen zum Zuweisen von dedizierten und freigegebenen Telefonnummern zur Audiokonferenzbrücke. 

Auf der Grundlage seiner Recherchen hat Contoso die folgenden Entscheidungen getroffen: 

- Nur ein Segment der Bevölkerung, das regelmäßig Audiokonferenzanrufe hosten würde, würde Lizenzen für Audiokonferenzen erhalten. 

- Contoso verwendet dedizierte Telefonnummern und portiert die vorhandenen Nummern zur Verwendung mit Audiokonferenzen.   

Da Contoso-Benutzer eine Skype for Business und die Postfächer aller Benutzer online gespeichert sind, sind für viele Benutzer bereits Besprechungen geplant. Contoso hat [unter Verwenden des Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) erfahren, dass vorhandene Besprechungen für Contoso automatisch aktualisiert werden, wenn der Endbenutzer in den TeamsOnly-Modus wechselt.  


## <a name="configuration"></a>Konfiguration

Telefon, die Audiokonferenzen zugeordnet sind, werden innerhalb einer Konferenz als Leistungsnummern Telefonsystem. 

- Um Standorte, die Anrufpläne verwenden, ihre vorhandenen Telefonnummern von ihrem Netzbetreiber zu Office 365 zu portieren, hat Contoso die Schritte unter Abrufen von [Servicetelefonnummern befolgt.](getting-service-phone-numbers.md)

- Um dem Endbenutzer im technischen Pilotprojekt die Lizenz für [Audiokonferenzen](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)zuzuordnen, hat der Contoso-Administrator die Schritte unter Verwalten der Audiokonferenzeinstellungen für Ihre Organisation befolgt. 

- Für das Pilotprojekt und die Migration von Unternehmen hat Contoso eine gruppenbasierte Lizenzierung verwendet. Dazu folgen Sie den Schritten unter Zuweisen von Lizenzen zu Benutzern durch [Gruppenmitgliedschaft in Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

