---
title: Teams Voice Contoso-Fallstudie
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
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786037"
---
# <a name="contoso-case-study-audio-conferencing"></a>Contoso-Fallstudie: Audiokonferenzen

Wenn Sie eine Vorstellung von Audiokonferenzen gewinnen möchten, was es &mdash; ist, was es kostet, die Verfügbarkeit und wie es funktioniert, hat &mdash; contoso [Audiokonferenzen in Office 365](deploy-audio-conferencing-teams-landing-page.md)bewertet. 

## <a name="overview"></a>Übersicht 

Für Audiokonferenzen verwendet Contoso Telefonnummern, die sowohl innerhalb der Organisation als auch extern bekannt sind. Da Contoso diese Nummern nach Möglichkeit beibehalten wollte, haben Sie die Informationen zum Zuweisen von dedizierten und freigegebenen Telefonnummern zur Audiokonferenz-Brücke überprüft. 

Basierend auf Ihren Recherchen hat Contoso die folgenden Entscheidungen getroffen: 

- Nur ein Bevölkerungssegment, das regelmäßig Audiokonferenz-Anrufe hostet, erhält Audiokonferenz-Lizenzen. 

- Contoso würde dedizierte Telefonnummern verwenden und Ihre vorhandenen Nummern für die Verwendung mit Audiokonferenzen portieren.   

Da Contoso-Benutzer Skype for Business verwenden und die Postfächer aller Benutzer online sind, haben viele Benutzer bereits Besprechungen geplant. Contoso liest [mithilfe des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , um zu erfahren, dass vorhandene Besprechungen automatisch für Contoso aktualisiert werden, wenn Sie den Endbenutzer in den TeamsOnly-Modus ändern.  


## <a name="configuration"></a>Konfiguration

Telefonnummern, die mit Audiokonferenzen verknüpft sind, werden im Telefon System als Dienstnummern bezeichnet. 

- Bei Speicherorten mit Anrufplänen, um Ihre vorhandenen Telefonnummern von Ihrem Telefonanbieter zu Office 365 zu portieren, folgte Contoso den Schritten unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md).

- Wenn Sie die Audiokonferenz-Lizenz dem Endbenutzer im technischen Pilotprojekt zuweisen möchten, folgte der Contoso-Administrator den Schritten unter [Verwalten der audiokonferenzeinstellungen für Ihre Organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). 

- Für den Geschäfts Pilot und die Migration verwendete Contoso die Gruppenbasierte Lizenzierung, indem Sie die Schritte unter [Zuweisen von Lizenzen zu Benutzern durch Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)befolgten.  

 

 