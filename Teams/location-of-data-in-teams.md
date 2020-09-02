---
title: Speicherort von Daten in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: In diesem Artikel erfahren Sie, wo sich die Daten in Microsoft Teams geografisch befinden.
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121685"
---
# <a name="location-of-data-in-microsoft-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Gegenwärtig unterstützt Teams die Regionen Australien, Kanada, Frankreich, Deutschland, Indien, Japan, Südafrika, Südkorea, die Schweiz (einschließlich Liechtenstein), die Vereinigten Arabischen Emirate, Großbritannien, Nord- und Südamerika, APAC und EMEA. 

> [!IMPORTANT]
> Teams bietet derzeit Data Residency in Australien, Kanada, Frankreich, Deutschland, Indien, Japan, den Vereinigten Arabischen Emiraten, Großbritannien, Südkorea, Südafrika und der Schweiz (einschließlich Liechtenstein) nur für neue Mandanten an.
> Ein neuer Mandant wird definiert als ein Mandant, über den sich noch kein einziger Benutzer bei Microsoft Teams angemeldet hat. Bei bestehenden Mandanten aus Australien, Indien, Japan und Südkorea werden die entsprechenden Teams weiterhin in der Region APAC gespeichert. Die Daten bestehender Mandanten in Kanada weiterhin in Amerika gespeichert. Bestehende Mandanten in Frankreich, Deutschland, Liechtenstein, den Vereinigten Arabischen Emiraten, Großbritannien, Südafrika und der Schweiz werden in der Region EMEA gespeichert.

## <a name="where-your-teams-data-is-stored"></a>Wo Ihre Teams-Daten gespeichert sind

Wenn Sie wissen möchten, in welcher Region sich die Daten für Ihren Mandanten befinden, wechseln Sie zu [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) > **Einstellungen** > **Organisationsprofil**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort).

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Speicherort ruhender Teams-Daten

Ihre Teams-Daten werden je nach Inhaltstyp anders gespeichert. 

![Diagramm, das die Teams-Inhaltstypen und deren Speicherort (im Ruhezustand) zeigt](media/location-of-data-storage-at-rest.png)

Sehen Sie sich die [Ignite-Breakout-Sitzung zur Microsoft Teams-Architektur](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) an, um ausführliche Informationen zu erhalten.

### <a name="core-teams-customer-data"></a>Zentrale Teams-Kundendaten

Wenn Ihr Mandant in Australien, Kanada, der Europäischen Union, Frankreich, Deutschland, Indien, Japan, Südafrika, Südkorea, der Schweiz (einschließlich Liechtenstein), den Vereinigten Arabischen Emiraten, dem Vereinigten Königreich oder den Vereinigten Staaten bereitgestellt wird, speichert Microsoft die folgenden ruhenden Kundendaten nur innerhalb dieses Standorts:

- Team-Chats, Team- und Kanalunterhaltungen, Bilder, Voicemail-Nachrichten und Kontakte
- Microsoft Office SharePoint Online-Websiteinhalte und die auf der Website gespeicherten Dateien
- Auf Microsoft OneDrive for Business hochgeladene Dateien

#### <a name="chat-channel-messages-team-structure"></a>Chats, Kanalmeldungen, Teamstruktur

Jedes Team in Teams verfügt über eine Microsoft 365-Gruppe und die zugehörige SharePoint-Website sowie einem Exchange-Postfach. Private Chats (einschließlich Gruppenchats), Nachrichten, die als Teil einer Unterhaltung in einem Kanal gesendet wurden, und die Struktur von Teams und Kanälen werden in einem Chatdienst gespeichert, der in Azure ausgeführt wird. Die Daten werden außerdem in einem verborgenen Ordner der Benutzer- und Gruppen-postfächer gespeichert, um die Azure Information Protection-Features zu aktivieren.

#### <a name="voicemail-and-contacts"></a>Voicemail und Kontakte

Voicemails werden in Exchange gespeichert. Kontakte werden in einem Exchange-basierten Clouddatenspeicher gespeichert. Exchange und der Exchange-basierte Cloudspeicher bieten bereits Data Residency in allen weltweiten Rechenzentrumsgeos. Für alle Teams werden für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, die Vereinigten Arabischen Emirate, das Vereinigte Königreich, Südafrika, Südkorea, die Schweiz (einschließlich Liechtenstein) und die Vereinigten Staaten Voicemail und Kontakte innerhalb des Landes gespeichert. Für alle anderen Länder werden Dateien je nach Mandantenaffinität n den USA, in Europa oder Asien-Pazifik gespeichert.

#### <a name="images-and-media"></a>Bilder und Medien

In Chats verwendete Medien (außer Giphy-GIFs, die nicht gespeichert werden, sondern auf die ursprüngliche URL des Giphy-Dienstes verweisen, da Giphy ein Nicht-Microsoft-Dienst ist), werden in einem Azure-basierten Mediendienst gespeichert, der an denselben Orten wie der Chatdienst bereitgestellt wird.

#### <a name="files"></a>Dateien

Dateien (einschließlich OneNote und Wiki), die jemand in einem Kanal teilt, werden auf der Microsoft Office SharePoint Online-Website des Teams gespeichert. In einem privaten Chat oder in einem Chat während einer Besprechung oder eines Anrufs geteilte Daten werden in das Microsoft OneDrive for Business-Benutzerkonto hochgeladen und gespeichert. Exchange, Microsoft Office SharePoint Online und Microsoft OneDrive bieten bereits Data Residency in allen weltweiten Rechenzentrumsgeos. Bei bestehenden Kunden sind also bereits alle Dateien, OneNote-Notebooks, Teams Wiki-Inhalte, Postfächer der Teams-Umgebung, am Standort gespeichert, je nach Mandantenaffinität. Dateien werden für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, Vereinigte Arabische Emirate, Großbritannien, Südafrika, Südkorea und die Schweiz (einschließlich Liechtenstein) innerhalb des Landes gespeichert. Für alle anderen Länder werden Dateien je nach Mandantenaffinität in den USA, Europa oder Asien-Pazifik gespeichert.

### <a name="datacenter-locations"></a>Standorte der Rechenzentren

Die in diesem Abschnitt beschriebenen Teams-Dienste legen die ruhenden Daten an den folgenden Speicherorten ab:

|Land oder Region  |Standort des Rechenzentrums |
|---------|---------|
|Australien   |New South Wales und Victoria         |
|Kanada    |Quebec und Toronto         |
|Frankreich    |Marseille und Paris         |
|Deutschland    |Berlin und Frankfurt      |
|Indien   |Chennai und Pune        |
|Japan    |Tokio (Saitama) und Osaka         |
|Liechtenstein   |Genf und Zürich       |
|Südafrika     |Johannesburg und Kapstadt         |
|Südkorea     |Seoul und Busan         |
|Schweiz    |Genf und Zürich       |
|Vereinigte Arabische Emirate     |Abu Dhabi und Dubai         |
|Vereinigtes Königreich     | Cardiff und London        |
|Nord- und Südamerika (AMER) |Bay, CA und Boydton, VA       |
|Asien-Pazifik (APAC)  |Singapur und Hongkong        |
|Europa, Naher Osten und Asien (EMEA)   |Dublin und Amsterdam        |

> [!NOTE]
> Für Liechtenstein werden die Daten in den Rechenzentren der Schweiz in Genf und Zürich gespeichert.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Bei einem externen Anbieter gespeicherte Daten

Organisationen, die Benutzern das Speichern von Dateien mit einem Drittanbieter gestatten, sind vom Speicherort dieser Dienste abhängig und sollten deshalb den Speicherort der ruhenden Daten für diese Dienste separat überprüfen.

- **Registerkarten**: Mithilfe von Registerkarten können Benutzer Informationen aus Apps und Diensten an einen Kanal anheften. Der Datenspeicherort variiert je nach Art der Registerkarte. Auf der Registerkarte selbst werden keine Daten abgelegt. Beispielsweise werden auf einer Microsoft Office SharePoint Online-Registerkarte Daten gespeichert, je nachdem, wo die Microsoft Office SharePoint Online-Websitesammlung bereitgestellt wurde. Eine Registerkarte, die Informationen von einem Partner enthält, speichert die Daten direkt in dem vom Partner verwendeten System und zeigt nur eine Ansicht der Daten an.
- **Weitere Partner-Apps**: Microsoft bietet keinen Data Residency-Support für Apps und Dienste von Partnern, die Sie möglicherweise im Rahmen der Teams-Umgebung nutzen. Prüfen Sie Informationen aus diesen Lösungen direkt, um zu erfahren, wo ihre Daten gespeichert werden.

## <a name="see-also"></a>Weitere Informationen

- [Microsoft Teams startet Data Residency in den Vereinigten Arabischen Emiraten](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams startet Data Residency in Südkorea](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams startet Data Residency in Südafrika](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams startet Data Residency in Frankreich](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams startet Data Residency in Indien, weitere Geos demnächst verfügbar](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams startet Data Residency in Australien und Japan](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams startet Data Residency in Kanada, Australien und Japan (in Kürze verfügbar)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
