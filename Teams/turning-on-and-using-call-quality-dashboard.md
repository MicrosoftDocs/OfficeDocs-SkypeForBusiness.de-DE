---
title: Einrichten des Dashboards für die Anrufqualität (CQD)
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
description: Hier erfahren Sie, wie Sie das Dashboard für die Anrufqualität aktivieren und verwenden und zusammenfassende Berichte über die Qualität von Anrufen erhalten.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918650"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Einrichten des Dashboards für die Anrufqualität (CQD)

Öffnen Sie das Microsoft Call Quality-Dashboard (CQD) unter [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (melden Sie sich mit Ihren Administratoranmeldeinformationen an). Oder wechseln Sie zum Team Admin Center, und wählen Sie **Anruf Qualitäts Dashboard** aus. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot der Schaltfläche "Anrufqualität" im Team Admin Center":::

Klicken Sie auf der Seite, die geöffnet wird, auf **Anmelden** , und geben Sie Ihr globales Administrator Konto oder Microsoft Teams-Dienstadministratorkonto Informationen ein. Nachdem Sie sich das erste Mal angemeldet haben, wird CQD mit dem sammeln und Verarbeiten von Daten beginnen. Beachten Sie, dass es möglicherweise eine oder mehrere Stunden dauert, bis genügend Daten verarbeitet werden, um aussagekräftige Ergebnisse in den Berichten anzuzeigen.

CQD zeigt Anruf-und Besprechungs Qualität auf organisationsweiter Ebene für Microsoft Teams, Skype for Business Online und Skype for Business Server 2019. 

> [!IMPORTANT]
> Wenn Sie CQD mit Skype for Business Server 2019 verwenden möchten, müssen Sie den [Anrufdaten-Konnektor konfigurieren](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Weitere Informationen finden Sie unter [Planen von Anrufdaten-Konnektoren](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) vor dem Start.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Zuweisen von Administratorrollen für den Zugriff auf CQD

Zuweisen von [Rollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) für den Zugriff auf CQD für Personen, die Sie verwenden müssen.

Wenn Sie möchten, dass Benutzer, die keine Administratoren sind (beispielsweise Support Engineers und Helpdesk-Agents), das Dashboard für die Anrufqualität verwenden, können Sie diesen Benutzern eine der folgenden Rollen zuweisen, die Zugriff auf CQD gewährt. 


|  |Berichte anzeigen  |EUII-Felder anzeigen  |Berichte erstellen  |Gebäudedaten hochladen  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Globaler Office 365-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Dienstadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationsadministrator     |Ja         |Ja         |Ja         |Ja         |
|Teams-Kommunikationssupporttechniker     |Ja         |Ja         |Ja         |Nein         |
|Supportfachmann für die Teams-Kommunikation     |Ja         |Nein         |Ja         |Nein         |
|Skype for Business-Administrator     |Ja         |Ja         |Ja         |Ja         |
|Azure AD globaler Leseberechtigter |Ja         |Ja         |Ja         |Nein         |
|Office 365-Berichtleseberechtigter<sup>1</sup>     |Ja         |Nein         |Ja         |Nein         |

<sup>1</sup> Zusätzlich zum Lesen von CQD-Berichten kann der Office 365-Berichtleseberechtigter alle [Aktivitätsberichte](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) im Admin Center sowie alle Berichte aus dem [Inhaltspaket zur Microsoft 365-Einführung](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) anzeigen.

> [!NOTE]
> Wenn Sie [EUII (Endbenutzer-identifizierbare Informationen)](CQD-data-and-reports.md#euii-data) nicht sehen und über eine der Rollen verfügen, die diese Informationen anzeigen dürfen, denken Sie daran, dass CQD nur 28 Tage lang EUII. Alles, was älter als 28 Tage ist, wird gelöscht.

Weitere Informationen zu diesen Rollen finden Sie unter [Informationen zu Office 365-Administratorrollen](/office365/admin/add-users/about-admin-roles).


Nachdem Sie sich das erste Mal angemeldet haben, wird CQD mit dem sammeln und Verarbeiten von Daten beginnen. Ab Dezember 2019 können Sie weiterhin auf die ältere Version von CQD (CQD.lync.com) zugreifen, obwohl das Legacy Portal Ihnen einen Link zu dem neuesten CQD (CQD.Teams.Microsoft.com) bietet. Schließlich wird die ältere Version von CQD außer Betrieb genommen. Ab dem 1. Juli 2020 greift die ältere Version von CQD auf Daten aus dem neuesten CQD zu.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrieren von Gebäudedaten und Berichten aus einer früheren Version von CQD

> [!IMPORTANT]
> Ab dem 1. Juli 2020 können Sie keine Gebäudedaten und Berichte mehr aus dem alten CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Verwenden von Power BI zum Analysieren von CQD-Daten

Neu im Januar 2020: [Power BI-Abfragevorlagen für CQD herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Anpassbare Power BI-Vorlagen, mit deren Hilfe Sie Ihre CQD-Daten analysieren und berichten können.

Lesen [verwenden Sie Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md) , um weitere Informationen zu erhalten.


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und-Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstrom Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)
