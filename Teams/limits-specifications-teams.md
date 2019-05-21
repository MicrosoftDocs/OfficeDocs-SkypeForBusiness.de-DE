---
title: Grenzwerte und Spezifikationen für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/07/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: Erfahren Sie mehr über die Grenzwerte, Spezifikationen und anderen Anforderungen für Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c71b789684d6d40ab9eb67e0464f8dc46ae0e96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299681"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Grenzwerte und Spezifikationen für Microsoft Teams

In diesem Artikel werden einige der Grenzwerte, Spezifikationen und anderen Anforderungen für Teams beschrieben.

## <a name="teams-and-channels"></a>Teams und Kanäle 

|Feature    | Obergrenze |
|-----------|---------------|
|Anzahl der Teams, die ein Benutzer erstellen kann | Grenzwert von 250 Objekten&sup1;         |
|Anzahl der Mitglieder in einem Team | 5.000       |
|Anzahl der Mitglieder in einem [organisationsweiten Team](create-an-org-wide-team.md) | 5.000       |
|Anzahl der Teams, die ein globaler Administrator erstellen kann        |  500.000   |
|Anzahl der Teams in einem Office 365-Mandanten    | 500, 000&sup2;     |
|Anzahl der Kanäle pro Team    | 200 (einschließlich gelöschter Kanäle) &sup3;         |

&sup1;Jedes Verzeichnisobjekt in Azure Active Directory zählt. Globale Administratoren und Apps, die Microsoft Graph mit [Anwendungsberechtigungen](https://docs.microsoft.com/graph/permissions-reference) aufrufen, sind von diesem Grenzwert ausgeschlossen.

&sup2; Dieser Grenzwert umfasst Archivierte Teams.

&sup3; gelöschte Kanäle können innerhalb von 30 Tagen wiederhergestellt werden. Während dieser 30 Tage wird ein gelöschter Kanal weiterhin für den 200-Kanal pro Team Grenze gezählt. Nach 30 Tagen werden ein gelöschter Kanal und dessen Inhalt endgültig gelöscht, und der Kanal zählt nicht mehr zu den 200-Kanälen pro Team Grenze.

## <a name="meetings-and-calls"></a>Besprechungen und Anrufe 

|Feature     | Obergrenze |
|------------|---------------|
|Anzahl der Personen in einer Besprechung  | 250    |
|Anzahl der Personen in einem privaten Chat  | 50    |

## <a name="storage"></a>Speicher

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Wenn Sie SharePoint Online nicht in Ihrem Mandanten aktiviert haben, können Microsoft Teams-Benutzer nicht immer Dateien in Teams freigeben. Benutzer im privaten Chat können Dateien auch nicht freigeben, weil OneDrive for Business (mit der SharePoint-Lizenz verknüpft) für diese Funktionalität erforderlich ist.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. (Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).)

Da Teams in einem SharePoint Online-Backend für die Dateifreigabe ausgeführt wird, gelten die SharePoint-Einschränkungen für den Bereich „Dateien“ innerhalb eines Teams. Hier die entsprechenden Speichergrenzwerte für SharePoint Online:

|Feature                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Speicher                 |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation plus 10 GB pro erworbener Lizenz   |1 TB pro Organisation plus 10 GB pro erworbener Lizenz |1 TB pro Organisation plus 10 GB pro erworbener Lizenz  |1 TB pro Organisation           |
|Speicher für Teams-Dateien |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |Bis zu 25 TB pro Websitesammlung oder Gruppe |
|Grenzwert bei Dateiuploads       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Jede Dateienregisterkarte in Teams wird in einem SharePoint Online-Backend ausgeführt. Die Speichergrenzwerte oben gelten also für jeden Kanal in einem Team.

Weitere Informationen finden Sie unter [SharePoint Online-Grenzwerte](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="messaging"></a>Messaging

Benutzer, die an Gesprächen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind, müssen ein Exchange Online-Postfach (cloudbasiert) für einen Administrator haben, um Unterhaltungen im Chat zu suchen. Der Grund hierfür ist, dass Unterhaltungen, die Teil der Chat-Liste sind, in den cloudbasierten Postfächern der Chat-Teilnehmer gespeichert werden. Wenn ein Chat-Teilnehmer nicht über ein Exchange Online-Postfach verfügt, kann der Administrator Chat-Unterhaltungen nicht durchsuchen oder sperren. Beispielsweise können Benutzer mit lokalen Postfächern in einer Exchange-Hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind. Der Inhalt dieser Unterhaltungen ist in diesem Fall jedoch nicht durchsuchbar und kann nicht gesperrt werden, da die Benutzer keine cloudbasierten Postfächer haben. (Weitere Informationen finden Sie unter [Interaktion von Exchange und Microsoft Teams](exchange-teams-interact.md).)

Die Chat-Funktion von Microsoft Teams funktioniert in einem Microsoft Exchange-Backend, damit Sie die Grenzwerte für das Exchange-Messaging auf die Chat-Funktion in Microsoft Teams anwenden können. Wenn Benutzer eine E-Mail an einen Kanal in Teams senden möchten, verwenden sie die E-Mail-Adresse des Kanals. Wenn eine E-Mail Teil eines Kanals ist, kann jeder antworten, um eine Unterhaltung zu beginnen. Hier einige geltende Grenzwerte zum Senden von E-Mails an einen Kanal: 

|Feature  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|Grenzwert für Nachrichtengröße &dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|Grenzwert für Dateianlagen &Dagger;  |10     |10     |10     |10    |
|Grenzwert für Inlinegrafiken &Dagger; |50   |50   |50   |50   |

&dagger; Wenn die Nachricht diesen Grenzwert überschreitet, wird eine Vorschaunachricht generiert und der Benutzer wird gebeten, die Original-E-Mail aus dem bereitgestellten Link anzuzeigen/herunterzuladen.

&Dagger; Wenn die Anzahl der Anlagen oder Bilder diesen Grenzwert überschreitet, wird die Nachricht nicht verarbeitet und eine NDR-E-Mail mit einer Benachrichtigung über den Fehler zurück an den Absender gesendet.

> [!NOTE]
> Die Grenzwerte für Nachrichtengröße, Dateianlagen und Inline Bilder sind für alle Office 365-Lizenzen identisch.

Weitere Informationen finden Sie unter [Exchange Online-Grenzwerte](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Betriebssysteme

Informationen zu den Betriebssystemanforderungen finden Sie unter [Beziehen von Clients für Microsoft Teams](get-clients.md).
