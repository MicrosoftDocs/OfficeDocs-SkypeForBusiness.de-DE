---
title: Speicherort von Daten in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: In diesem Artikel erfahren Sie, wo die Daten geografisch in Microsoft Teams gespeichert sind.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121685"
---
# <a name="location-of-data-in-microsoft-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365-oder Office 365-Organisation zugeordnet ist. Derzeit unterstützt Microsoft Teams Australien, Kanada, Frankreich, Deutschland, Indien, Japan, Südafrika, Südkorea, die Schweiz (einschließlich Liechtenstein), die Regionen Vereinigten Arabische Emirate, Großbritannien, Amerika, APAC und EMEA. 

> [!IMPORTANT]
> Teams bietet derzeit Daten in Australien, Kanada, Frankreich, Deutschland, Indien, Japan, den Vereinigten Arabischen Emiraten, Großbritannien, Südkorea, Südafrika und der Schweiz (einschließlich Liechtenstein) für neue Mandanten an.
> Ein neuer Mandant wird definiert als ein Mandant, über den sich noch kein einziger Benutzer bei Microsoft Teams angemeldet hat. Bei bestehenden Mandanten aus Australien, Indien, Japan und Südkorea werden die entsprechenden Teams weiterhin in der Region APAC gespeichert. Die Daten bestehender Mandanten in Kanada weiterhin in Amerika gespeichert. Bestehende Mandanten in Frankreich, Deutschland, Liechtenstein, den Vereinigten Arabischen Emiraten, Großbritannien, Südafrika und der Schweiz werden Ihre Daten in der EMEA-Region speichern.

## <a name="where-your-teams-data-is-stored"></a>Wo Ihre Teams-Daten gespeichert sind

Wenn Sie wissen möchten, in welcher Region sich die Daten für Ihren Mandanten befinden, wechseln Sie zu [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)  > **Einstellungen** > **Organisationsprofil**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort).

![Screenshot der Tabelle "Datenspeicherort" mit Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Speicherort der Teamdaten im Ruhezustand

Ihre Teams-Daten werden je nach Inhaltstyp unterschiedlich gespeichert. 

![Diagramm mit Teams-Inhaltstypen und dem Speicherort, an dem Sie im Ruhezustand gespeichert sind](media/location-of-data-storage-at-rest.png)

Schauen Sie sich die [Ignite-Breakout-Sitzung auf der Microsoft Teams-Architektur](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) an, um eine ausführliche Diskussion zu führen.

### <a name="core-teams-customer-data"></a>Kundendaten des Core Teams

Wenn Ihr Mandant in Australien, Kanada, der Europäischen Union, Frankreich, Deutschland, Indien, Japan, Südafrika, Südkorea, der Schweiz (einschließlich Liechtenstein), den Vereinigten Arabischen Emiraten, dem Vereinigten Königreich oder den Vereinigten Staaten bereitgestellt wird, speichert Microsoft die folgenden Kundendaten nur innerhalb dieses Speicherorts:

- Teams-Chats, Team-und Kanal Unterhaltungen, Bilder, Voicemail-Nachrichten und Kontakte
- SharePoint Online-Websiteinhalte und die auf dieser Website gespeicherten Dateien
- Dateien, die auf OneDrive for Business hochgeladen wurden

#### <a name="chat-channel-messages-team-structure"></a>Chat, Kanal Nachrichten, Teamstruktur

Jedes Team in Teams wird durch eine Microsoft 365-Gruppe und die zugehörige SharePoint-Website und das Exchange-Postfach gesichert. Private Chats (einschließlich Gruppen-Chats), Nachrichten, die als Teil einer Unterhaltung in einem Kanal gesendet wurden, und die Struktur von Teams und Kanälen werden in einem in Azure ausgeführten Chatdienst gespeichert. Die Daten werden auch in einem ausgeblendeten Ordner in den Benutzer-und Gruppen Postfächern gespeichert, um Informationsschutz Features zu ermöglichen.

#### <a name="voicemail-and-contacts"></a>Voicemail und Kontakte

Sprachnachrichten werden in Exchange gespeichert. Kontakte werden im Exchange-basierten Cloud-Datenspeicher gespeichert. Exchange und der Exchange-basierte Cloud Store bieten bereits Daten in jedem der weltweiten Rechenzentren GEOSS. Für alle Teams werden Voicemail und Kontakte in Deutschland für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, die Vereinigten Arabischen Emirate, das Vereinigte Königreich, Südafrika, Südkorea, die Schweiz (einschließlich Liechtenstein) und die Vereinigten Staaten gespeichert. Für alle anderen Länder werden Dateien auf der Grundlage der Mandanten Affinität in den USA, Europa oder dem asiatisch-pazifischen Standort gespeichert.

#### <a name="images-and-media"></a>Bilder und Medien

Medien, die in Chats verwendet werden (mit Ausnahme von Giphy-GIFs, die nicht gespeichert sind, aber ein Verweis Link zur ursprünglichen Giphy-Dienst-URL sind, Giphy ein nicht-Microsoft-Dienst ist), wird in einem Azure-basierten Mediendienst gespeichert, der an denselben Speicherorten wie der Chatdienst bereitgestellt wird.

#### <a name="files"></a>Dateien

Dateien (einschließlich OneNote und wiki), die jemand in einem Kanal freigibt, werden auf der SharePoint-Website des Teams gespeichert. In einem privaten Chat oder einem Chat während einer Besprechung oder eines Anrufs freigegebene Dateien werden im OneDrive für das Unternehmenskonto des Benutzers, der die Datei freigibt, hochgeladen und gespeichert. Exchange, SharePoint und OneDrive bieten bereits in jedem weltweiten Rechenzentrum GEOS Daten an. Daher sind für vorhandene Kunden alle Dateien, OneNote-Notizbücher, wiki-Inhalte von Teams und Postfächer, die Teil der Teams sind, auf Grundlage Ihrer Mandanten Affinität bereits an dem Speicherort gespeichert. Dateien werden in-Country für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, die Vereinigten Arabischen Emirate, das Vereinigte Königreich, Südafrika, Südkorea und die Schweiz (einschließlich Liechtenstein) gespeichert. Für alle anderen Länder werden Dateien auf der Grundlage der Mandanten Affinität in den USA, in Europa oder im asiatisch-pazifischen Standort gespeichert.

### <a name="datacenter-locations"></a>Datencenter Speicherorte

Die in diesem Abschnitt beschriebenen Team Dienste speichern Daten an den folgenden Speicherorten:

|Land oder Region  |Speicherort des Datencenters |
|---------|---------|
|Australien   |New South Wales und Victoria         |
|Kanada    |Quebec City und Toronto         |
|Frankreich    |Marseille und Paris         |
|Deutschland    |Berlin und Frankfurt      |
|Indien   |Chennai und Pune        |
|Japan    |Tokyo (Saitama) und Osaka         |
|Liechtenstein   |Genf und Zürich       |
|Südafrika     |Johannesburg und Kapstadt         |
|Südkorea     |Seoul und Busan         |
|Schweiz    |Genf und Zürich       |
|Vereinigte Arabische Emirate     |Abu Dhabi und Dubai         |
|Vereinigtes Königreich     | Cardiff und London        |
|Nord-und Südamerika (Amer) |Bay, ca und Boydton, VA       |
|Asien/Pazifik (APAC)  |Singapur und Hongkong        |
|Europa, Mittlerer Osten und Asien (EMEA)   |Dublin und Amsterdam        |

> [!NOTE]
> Für Liechtenstein werden die Daten in der Schweiz in den Rechenzentren in Genf und Zürich gespeichert.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Daten, die mit einem Speicheranbieter von Drittanbietern gespeichert sind

Organisationen, die es Benutzern ermöglichen, Dateien mit einem Drittanbieter-Speicheranbieter zu speichern, sind vom Speicherort dieser Dienste abhängig und sollten daher den Speicherort der Daten, die sich im Ruhezustand befinden, für diese Dienste separat überprüfen.

- **Registerkarten**: mit Tabstopps können Benutzerinformationen aus apps und Diensten an einen Kanal anheften. Daher variiert Sie je nach Typ der Registerkarte, auf der die Daten gespeichert sind. Die Registerkarte selbst speichert keine Daten. Auf der Registerkarte "SharePoint" werden beispielsweise Daten basierend darauf gespeichert, wo die SharePoint-Websitesammlung bereitgestellt wurde. Eine Registerkarte, die Informationen von einem Partner enthält, speichert die Daten direkt in dem vom Partner verwendeten System und zeigt nur eine Ansicht davon an.
- **Andere Partner-apps**: Microsoft bietet keine Daten Residency-Unterstützung für apps und Dienste von Partnern, die Sie möglicherweise in der Team Erfahrung verwenden. Überprüfen Sie die Informationen aus diesen Lösungen direkt, um zu erfahren, wo Ihre Daten gespeichert werden.

## <a name="see-also"></a>Siehe auch

- [Microsoft Teams startet den United Arab Emirates Data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams startet südkoreanischen Daten Wohnsitz](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams startet südafrikanische Daten Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams startet France Data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams startet India Data Residency, weitere GEOSS in Kürze verfügbar](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams startet Daten Residency in Australien und Japan](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams startet Kanada Data Residency, Australien und Japan in Kürze](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
