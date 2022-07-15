---
title: Einrichten des Anrufqualitäts-Dashboards (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Anrufqualitäts-Dashboard aktivieren und verwenden und zusammenfassende Berichte über die Qualität von Anrufen erhalten.
ms.openlocfilehash: 052b38634d17aa6d0086c80ed2a638a7818a729f
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66797380"
---
# <a name="set-up-call-quality-dashboard"></a>Einrichten des Anrufqualitätsdashboards

Öffnen Sie das Microsoft Call Quality Dashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Teams Admin Center, und wählen Sie **"Analyse& Berichte** > **über das Anrufqualitätsdashboard** aus.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Dashboardschaltfläche &quot;Anrufqualität&quot; im Teams Admin Center.":::

Klicken Sie auf der daraufhin geöffneten Seite auf **"Anmelden** ", und geben Sie Ihr globales Administratorkonto oder Microsoft Teams-Administratorkonto ein. Nach der ersten Anmeldung beginnt CQD mit dem Sammeln und Verarbeiten von Daten. Denken Sie daran, dass es ein oder mehrere Stunden dauern kann, bis genügend Daten verarbeitet wurden, um aussagekräftige Ergebnisse in den Berichten anzuzeigen.

CQD zeigt die Anruf- und Besprechungsqualität auf organisationsweiter Ebene für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 an. 

> [!IMPORTANT]
> Um CQD mit Skype for Business Server 2019 zu verwenden, müssen Sie den [Anrufdatenconnector konfigurieren](/skypeforbusiness/hybrid/configure-call-data-connector). Siehe ["Anrufdatenkonnektor planen](/skypeforbusiness/hybrid/plan-call-data-connector) ", bevor Sie beginnen.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf CQD

Weisen Sie den Personen, die es verwenden müssen, [Rollen](/microsoft-365/admin/add-users/about-admin-roles) für den Zugriff auf CQD zu.

Wenn Sie möchten, dass Nicht-Administratorbenutzer (z. B. Supporttechniker und Helpdesk-Agents) das Anrufqualitätsdashboard verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die Zugriff auf CQD bietet. 


|&nbsp;  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Globaler Reader |Ja         |Ja         |Ja         |Nein         |
|Berichtsleser<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann der Berichtsleser alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center und alle Berichte aus dem [Inhaltspaket zur Einführung von Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) anzeigen.

> [!NOTE]
> Wenn [EUII (Endbenutzer-identifizierbare Informationen)](CQD-data-and-reports.md#euii-data) nicht angezeigt wird und Sie über eine der Rollen verfügen, für die diese Informationen angezeigt werden dürfen, denken Sie daran, dass CQD EUII nur 28 Tage lang beibehält. Alles, was älter als 28 Tage ist, wird gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter ["Informationen Office 365 Administratorrollen](/office365/admin/add-users/about-admin-roles)".


Nach der ersten Anmeldung beginnt CQD mit dem Sammeln und Verarbeiten von Daten.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Lesen [Verwenden Sie Power BI, um CQD-Daten zu analysieren](CQD-Power-BI-query-templates.md) , um mehr zu erfahren.

## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
