---
title: Grenzwerte und Spezifikationen für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Erfahren Sie mehr über die Grenzwerte, Spezifikationen und anderen Anforderungen für Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407881"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Grenzwerte und Spezifikationen für Microsoft Teams

In diesem Artikel werden einige der Grenzwerte, Spezifikationen und anderen Anforderungen für Teams beschrieben.

## <a name="teams-and-channels"></a>Teams und Kanäle 

|Feature    | Obergrenze |
|-----------|---------------|
|Anzahl der Teams, die ein Benutzer erstellen kann | Grenzwert von 250 Objekten&sup1;         |
|Anzahl der Mitglieder in einem Team | 5.000       |
|Anzahl der in einem Mandanten zulässigen organisationsweiten Teams | 5     |
|Anzahl der Mitglieder in einem [organisationsweiten Team](create-an-org-wide-team.md) | 5.000       |
|Anzahl der Teams, die ein globaler Administrator erstellen kann        |  500.000   |
|Anzahl der Teams in einem Office 365-Mandanten    | 500.000&sup2;     |
|Anzahl der Kanäle pro Team    | 200 (enthält gelöschte Kanäle) &sup3;         |

&sup1;Jedes Verzeichnisobjekt in Azure Active Directory zählt. Globale Administratoren und Apps, die Microsoft Graph mit [Anwendungsberechtigungen](https://docs.microsoft.com/graph/permissions-reference) aufrufen, sind von diesem Grenzwert ausgeschlossen.

&sup2; Dieser Grenzwert umfasst Archivierte Teams.

&sup3; gelöschte Kanäle können innerhalb von 30 Tagen wiederhergestellt werden. Während dieser 30 Tage wird ein gelöschter Kanal weiterhin für den 200-Kanal pro Team Grenze gezählt. Nach 30 Tagen werden ein gelöschter Kanal und dessen Inhalt endgültig gelöscht, und der Kanal zählt nicht mehr zu den 200-Kanälen pro Team Grenze.

## <a name="channel-names"></a>Kanalnamen

Kanalnamen dürfen die folgenden Zeichen oder Wörter nicht enthalten.

|||
|---------|---------|
|Zeichen     | ~ #% & * {} +/\: #a3? &#124; ""..        |
|Zeichen in diesen Bereichen    | 0 bis 1F<br>80 bis 9F        |
|Wörter     | Formulare, con, konische $, CONOUT $, PRN, AUX, NUL, COM1 zu COM9, LPT1 zu LPT9, Desktop. ini, &#95;VTI&#95;|

Kanalnamen können auch nicht mit einem Unterstrich (_) oder Punkt (.) beginnen oder mit einem Punkt (.) enden.

## <a name="meetings-and-calls"></a>Besprechungen und Anrufe

|Feature     | Obergrenze |
|------------|---------------|
|Anzahl der Personen in einer Besprechung  | 250    |

## <a name="teams-live-events"></a>Live-Events für Teams

|Feature     | Obergrenze |
|------------|---------------|
|Zielgruppengröße | 10.000-Teilnehmer |
|Dauer des Ereignisses | 4 Stunden |
|Spalte1  |Spalte2  |
|---------|---------|
|Row1     |         |
|Row2     |         |

| Gleichzeitige Live Ereignisse in einem Office 365-Mandanten | 15 |

Weitere Informationen zu Live Ereignissen und einem Vergleich der Live-Events von Teams mit Skype-Live Konferenz finden Sie unter [Teams Live-Events und Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)-Live Konferenz.

## <a name="storage"></a>Speicher

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Wenn Sie SharePoint Online nicht in Ihrem Mandanten aktiviert haben, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer im privaten Chat können Dateien auch nicht freigeben, weil OneDrive for Business (mit der SharePoint-Lizenz verknüpft) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. (Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).)

Da Teams in einem SharePoint Online-Backend für die Dateifreigabe ausgeführt wird, gelten die SharePoint-Einschränkungen für den Bereich „Dateien“ innerhalb eines Teams. Hier die entsprechenden Speichergrenzwerte für SharePoint Online:

|Feature                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Speicher                 |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz   |1 TB pro Organisation plus 10 GB pro erworbener Lizenz |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation           |
|Speicher für Teams-Dateien |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |
|Beschränkung des Dateiuploads (pro Datei)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Kanäle werden durch Ordner in der für das Team erstellten SharePoint Online-Websitesammlung gesichert, sodass Dateiregisterkarten in Kanälen die Speichergrenzwerte des Teams teilen, dem Sie angehören.

Weitere Informationen finden Sie unter [SharePoint Online-Grenzwerte](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="messaging"></a>Messaging

Benutzer, die an Gesprächen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind, müssen ein Exchange Online-Postfach (cloudbasiert) für einen Administrator haben, um Unterhaltungen im Chat zu suchen. Der Grund hierfür ist, dass Unterhaltungen, die Teil der Chat-Liste sind, in den cloudbasierten Postfächern der Chat-Teilnehmer gespeichert werden. Wenn ein Chat-Teilnehmer nicht über ein Exchange Online-Postfach verfügt, kann der Administrator Chat-Unterhaltungen nicht durchsuchen oder sperren. Beispielsweise können Benutzer mit lokalen Postfächern in einer Exchange-Hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind. Der Inhalt dieser Unterhaltungen ist in diesem Fall jedoch nicht durchsuchbar und kann nicht gesperrt werden, da die Benutzer keine cloudbasierten Postfächer haben. (Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md).)

Die Chat-Funktion von Microsoft Teams funktioniert in einem Microsoft Exchange-Backend, damit Sie die Grenzwerte für das Exchange-Messaging auf die Chat-Funktion in Microsoft Teams anwenden können. Wenn Benutzer eine E-Mail an einen Kanal in Teams senden möchten, verwenden sie die E-Mail-Adresse des Kanals. Wenn eine E-Mail Teil eines Kanals ist, kann jeder antworten, um eine Unterhaltung zu beginnen. Hier einige geltende Grenzwerte zum Senden von E-Mails an einen Kanal: 

|Feature  | Obergrenze  |
|---------|---------|
|Anzahl der Personen in einem privaten Chat  | 100    |
|Nachrichtengröße&dagger;  |25 KB   |
|Anzahl der Dateianlagen&Dagger;  |10     |
|Anzahl der Inline Bilder&Dagger; |50   |

&dagger; Wenn die Nachricht diesen Grenzwert überschreitet, wird eine Vorschaunachricht generiert und der Benutzer wird gebeten, die Original-E-Mail aus dem bereitgestellten Link anzuzeigen/herunterzuladen.

&Dagger;Wenn die Anzahl der Anlagen oder Bilder diesen Grenzwert überschreitet, wird die Nachricht nicht verarbeitet, und eine NDR-e-Mail wird an den Absender zurückgesendet, der Sie über den Fehler benachrichtigt.

> [!NOTE]
> Die Grenzwerte für Nachrichtengröße, Dateianlagen und Inline Bilder sind für alle Office 365-Lizenzen identisch.

Weitere Informationen finden Sie unter [Exchange Online-Grenzwerte](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Betriebssysteme

Informationen zu den Betriebssystemanforderungen finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).
