---
title: Einrichten des Anrufqualitätsdashboards (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Anrufqualitätsdashboard aktivieren und verwenden und Zusammenfassungsberichte zur Anrufqualität erhalten.
ms.openlocfilehash: 292fa240b9298bd60715d812ec95d8e53403c489
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58750043"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Einrichten des Anrufqualitätsdashboards

Öffnen Sie das Microsoft-Anrufqualitätsdashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Teams Admin Center, und wählen Sie **Anrufqualitätsdashboard aus.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche "Anrufqualitäts-Dashboard" im Teams Admin Center.":::

Klicken Sie auf der nun geöffneten Seite **auf** Anmelden, und geben Sie Ihr globales Administratorkonto oder Microsoft Teams Administratorkontoinformationen ein. Nach der ersten Anmeldung beginnt das AQD mit dem Sammeln und Verarbeiten von Daten. Denken Sie daran, dass es eine oder mehrere Stunden dauern kann, bis genügend Daten für die Anzeige aussagekräftiger Ergebnisse in den Berichten verarbeiten können.

Das CQD zeigt die Anruf- und Besprechungsqualität auf Organisationsebene für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 an. 

> [!IMPORTANT]
> Wenn Sie das Anrufdaten-Skype for Business Server 2019 verwenden möchten, müssen Sie [den Verbindungsdatenconnector konfigurieren.](/skypeforbusiness/hybrid/configure-call-data-connector) Informationen [finden Sie unter Planen des Anrufdatenconnector,](/skypeforbusiness/hybrid/plan-call-data-connector) bevor Sie beginnen.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf das AQD

Weisen [Sie den](/microsoft-365/admin/add-users/about-admin-roles) Personen, die das AQD verwenden müssen, Rollen für den Zugriff auf das AQD zu.

Wenn Sie möchten, dass Benutzer ohne Administratorrechte (z. B. Supporttechniker und Helpdesk-Agents) das Anrufqualitätsdashboard verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die dem Anrufqualitätsdashboard Zugriff gewährt. 


|&nbsp;  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Global Reader |Ja         |Ja         |Ja         |Nein         |
|Leser für Berichte<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von AQD-Berichten kann [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) der Leser für Berichte alle Aktivitätsberichte im Admin Center und alle Berichte aus dem Inhaltspaket Microsoft 365 Zur Einführung [anzeigen.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Wenn EUII (identifizierbare Informationen für [Endbenutzer)](CQD-data-and-reports.md#euii-data) nicht angezeigt wird und Sie über eine der Rollen verfügen, die diese Informationen sehen dürfen, denken Sie daran, dass das CQD EUII nur für 28 Tage beibehalten kann. Alles, was älter als 28 Tage ist, wird gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter Informationen [zu Office 365 Administratorrollen.](/office365/admin/add-users/about-admin-roles)


Nach der ersten Anmeldung beginnt das AQD mit dem Sammeln und Verarbeiten von Daten.




## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden Power BI zum Analysieren von AQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Weitere Informationen Power BI Sie unter Verwenden von Power BI zum Analysieren von [AQD-Daten.](CQD-Power-BI-query-templates.md)


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen mandanten- und gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwalten der Anruf- und Besprechungsqualität mithilfe des Anrufqualitäts-AQD](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
