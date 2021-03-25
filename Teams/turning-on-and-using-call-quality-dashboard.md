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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Anrufqualitätsdashboard aktivieren und verwenden, und erhalten Sie Zusammenfassende Berichte zur Anrufqualität.
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162703"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Einrichten des Anrufqualitätsdashboards (CQD)

Öffnen Sie das Microsoft Call Quality Dashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Teams Admin Center, und wählen Sie **Anrufqualitätsdashboard aus.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche "Anrufqualitätsdashboard" im Teams Admin Center":::

Klicken Sie auf der nun geöffneten Seite auf **Anmelden,** und geben Sie Informationen zu Ihrem globalen Administratorkonto oder Ihrem Microsoft Teams Service Administrator-Konto ein. Nach der ersten Anmeldung beginnt CQD mit dem Sammeln und Verarbeiten von Daten. Denken Sie daran, dass es eine oder mehrere Stunden dauern kann, bis genügend Daten für die Anzeige aussagekräftiger Ergebnisse in den Berichten verwendet werden.

CQD zeigt die Anruf- und Besprechungsqualität für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 auf Organisationsebene an. 

> [!IMPORTANT]
> Wenn Sie CQD mit Skype for Business Server 2019 verwenden möchten, müssen Sie [Den Anrufdatenconnector konfigurieren.](/skypeforbusiness/hybrid/configure-call-data-connector) Weitere [Informationen finden Sie unter Planen des Anrufdatenverbinders,](/skypeforbusiness/hybrid/plan-call-data-connector) bevor Sie beginnen.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf CQD

Weisen [Sie den](/microsoft-365/admin/add-users/about-admin-roles) Personen, die es verwenden müssen, Rollen für den Zugriff auf CQD zu.

Wenn Sie möchten, dass Benutzer ohne Administratorrechte (z. B. Supporttechniker und Helpdeskmitarbeiter) das Anrufqualitätsdashboard verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, wodurch Zugriff auf CQD gewährt wird. 


|  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Dienstadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Globaler Reader |Ja         |Ja         |Ja         |Nein         |
|Berichte Reader<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) der Berichtsleser alle Aktivitätsberichte im Admin Center und alle Berichte aus dem [Microsoft 365 Adoption Content Pack anzeigen.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Wenn EUII (identifizierbare Informationen [für Endbenutzer)](CQD-data-and-reports.md#euii-data) nicht angezeigt wird und Sie über eine der Rollen verfügen, die diese Informationen sehen dürfen, denken Sie daran, dass CQD EUII nur für 28 Tage speichert. Alles, was älter als 28 Tage ist, wird gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen.](/office365/admin/add-users/about-admin-roles)


Nach der ersten Anmeldung beginnt CQD mit dem Sammeln und Verarbeiten von Daten. Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (cqd.lync.com) zugreifen, obwohl ihnen das Ältere Portal einen Link zum neuesten CQD (cqd.teams.microsoft.com) bietet. Schließlich wird die ältere Version von CQD außer Betrieb gesetzt. Ab dem 1. Juli 2020 zugrifft die ältere Version von CQD auf Daten aus dem neuesten CQD.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrieren von Gebäudedaten und Berichten aus früheren CQD-Versionen

> [!IMPORTANT]
> Ab dem 1. Juli 2020 können Sie keine Gebäudedaten und Berichte mehr aus dem alten CQD ( https://CQD.lync.com) migrieren. 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Weitere Informationen finden Sie unter Verwenden von Power BI zum Analysieren von [CQD-Daten.](CQD-Power-BI-query-templates.md)


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)