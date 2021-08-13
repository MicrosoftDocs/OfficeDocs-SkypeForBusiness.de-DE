---
title: Einrichten des Anrufqualitätsdashboards (Call Quality Dashboard, CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Anrufqualitäts-Dashboard aktivieren und verwenden und zusammenfassende Berichte über die Qualität von Anrufen erhalten.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300451"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Einrichten des Anrufqualitätsdashboards

Öffnen Sie das Microsoft Call Quality Dashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Teams Admin Center, und wählen Sie **"Anrufqualitäts-Dashboard"** aus. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche "Anrufqualitäts-Dashboard" im Teams Admin Center":::

Klicken Sie auf der daraufhin geöffneten Seite auf **"Anmelden",** und geben Sie Ihr globales Administratorkonto oder Microsoft Teams Administratorkontoinformationen ein. Nach der ersten Anmeldung beginnt das CQD mit der Erfassung und Verarbeitung von Daten. Denken Sie daran, dass es eine oder mehrere Stunden dauern kann, bis genügend Daten verarbeitet werden, um aussagekräftige Ergebnisse in den Berichten anzuzeigen.

CQD zeigt die Anruf- und Besprechungsqualität auf organisationsweiter Ebene für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 an. 

> [!IMPORTANT]
> Um CQD mit Skype for Business Server 2019 zu verwenden, müssen Sie [den Anrufdatenkonnektor konfigurieren.](/skypeforbusiness/hybrid/configure-call-data-connector) Sehen Sie sich den [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) an, bevor Sie beginnen.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf CQD

Weisen Sie [den Personen,](/microsoft-365/admin/add-users/about-admin-roles) die es verwenden müssen, Rollen für den Zugriff auf CQD zu.

Wenn Benutzer ohne Administratorrechte (z. B. Supporttechniker und Helpdesk-Agents) das Anrufqualitätsdashboard verwenden sollen, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die Zugriff auf CQD bietet. 


|&nbsp;  |Berichte anzeigen  |Anzeigen von EUII-Feldern  |Erstellen von Berichten  |Hochladen Gebäudedaten  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Supporttechniker für die Teams-Kommunikation     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Globaler Leser |Ja         |Ja         |Ja         |Nein         |
|Berichtsleseberechtigter<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann der Leser der Berichte alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center und alle Berichte aus dem [Inhaltspaket Microsoft 365 Einführung](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)anzeigen.

> [!NOTE]
> Wenn [EuII (Endbenutzer-Informationen)](CQD-data-and-reports.md#euii-data) nicht angezeigt wird und Sie über eine der Rollen verfügen, die diese Informationen anzeigen dürfen, denken Sie daran, dass CQD EUII nur 28 Tage lang beibehält. Alle älteren Elemente als 28 Tage werden gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365 Administratorrollen.](/office365/admin/add-users/about-admin-roles)


Nach der ersten Anmeldung beginnt das CQD mit der Erfassung und Verarbeitung von Daten. Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (cqd.lync.com) zugreifen, obwohl das Legacyportal einen Link zum neuesten CQD (cqd.teams.microsoft.com) bietet. Schließlich wird die ältere Version von CQD außer Betrieb genommen. Ab dem 1. Juli 2020 greift die ältere Version von CQD auf Daten aus dem neuesten CQD zu.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrieren von Gebäudedaten und Berichten aus der vorherigen Version von CQD

> [!IMPORTANT]
> Ab dem 1. Juli 2020 können Sie keine Gebäudedaten und Berichte mehr aus dem alten CQD migrieren https://CQD.lync.com) ( . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von AQD-Daten

Neu im Januar 2020: [Laden Sie Power BI Abfragevorlagen für CQD herunter.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Anpassbare Power BI Vorlagen, mit denen Sie Ihre CQD-Daten analysieren und melden können.

Lesen [Sie "Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more".


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream-Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
