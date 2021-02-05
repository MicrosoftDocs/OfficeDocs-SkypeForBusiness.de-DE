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
description: Erfahren Sie, wie Sie das Anrufqualitätsdashboard aktivieren und verwenden und Zusammenfassungsberichte zur Anrufqualität erhalten.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112840"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Einrichten des Anrufqualitätsdashboards (CQD)

Öffnen Sie das Microsoft-Anrufqualitätsdashboard (CQD) unter (melden Sie [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Teams Admin Center, und wählen Sie **"Anrufqualitätsdashboard" aus.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche für das Anrufqualitätsdashboard im Teams Admin Center":::

Klicken Sie auf der  seite, die nun geöffnet wird, auf "Anmelden", und geben Sie die Kontoinformationen Ihres globalen Administratorkontos oder Microsoft Teams Service Administrators ein. Nach der ersten Anmeldung beginnt das AQD mit dem Sammeln und Verarbeiten von Daten. Denken Sie daran, dass es eine oder mehrere Stunden dauern kann, bis genügend Daten für die Anzeige aussagekräftiger Ergebnisse in den Berichten zu verarbeiten sind.

Das CQD zeigt die Anruf- und Besprechungsqualität für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019 organisationsweit an. 

> [!IMPORTANT]
> Um das CQD mit Skype for Business Server 2019 verwenden zu können, müssen Sie den Connector für [Anrufdaten konfigurieren.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector) Informationen [finden Sie unter "Plananrufdatenconnector",](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) bevor Sie beginnen.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf das AQD

Weisen [Sie](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) den Personen, die das AQD verwenden müssen, Rollen für den Zugriff auf das AQD zu.

Wenn Benutzer ohne Administratorrechte (z. B. Supporttechniker und Helpdeskmitarbeiter) das Anrufqualitätsdashboard verwenden dürfen, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die dem Anrufqualitätsdashboard Zugriff gewährt. 


|  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Dienstadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Global Reader |Ja         |Ja         |Ja         |Nein         |
|Leser für Berichte<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Neben dem Lesen von AQD-Berichten kann [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) der Leser alle Aktivitätsberichte im Admin Center und alle Berichte aus dem Inhaltspaket zur Einführung von [Microsoft 365 anzeigen.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Wenn EUII (identifizierbare Informationen [für Endbenutzer)](CQD-data-and-reports.md#euii-data) nicht angezeigt wird und Sie über eine der Rollen verfügen, die diese Informationen sehen dürfen, denken Sie daran, dass das CQD EUII nur 28 Tage lang beibehalten kann. Alles, was älter als 28 Tage ist, wird gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter ["Informationen zu Administratorrollen von Office 365".](/office365/admin/add-users/about-admin-roles)


Nach der ersten Anmeldung beginnt das AQD mit dem Sammeln und Verarbeiten von Daten. Ab Dezember 2019 können Sie weiterhin auf die ältere Version des AQD (cqd.lync.com) zugreifen, obwohl ihnen das legacy-Portal einen Link zum neuesten CQD (cqd.teams.microsoft.com) bietet. Schließlich wird die ältere Version des AQD außer Betrieb gesetzt. Ab dem 1. Juli 2020 greifen die älteren Versionen des AQD auf Daten aus dem neuesten AQD zu.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrieren von Gebäudedaten und Berichten aus früheren Versionen des AQD

> [!IMPORTANT]
> Seit dem 1. Juli 2020 können Sie keine Gebäudedaten und Berichte mehr aus dem alten AQD migrieren ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von AQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Lesen [Sie Power BI zum Analysieren von AQD-Daten,](CQD-Power-BI-query-templates.md) um mehr zu erfahren.


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Daten und Berichte zum AQD](CQD-data-and-reports.md)

[Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)
