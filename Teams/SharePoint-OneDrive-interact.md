---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden, sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232278"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.

Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. 

> [!NOTE]
> Die Integration in SharePoint lokal wird für Microsoft Teams zurzeit nicht unterstützt.

Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.

![Diagramm der Ordner "freigegebene Dokumente" in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen. Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung. In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.

> [!TIP]
> So fügen Sie Ihrem Team eine Registerkarte hinzu, die mit einer vorhandenen SharePoint-Website Seite oder mit Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft ist:
> 1. Wählen Sie das Pluszeichen neben den Registerkarten aus.
> 2. Wählen Sie entweder **SharePoint** für eine vorhandene SharePoint-Website Seite oder eine **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek aus.
> 3. Wählen Sie die entsprechende Seite oder Dokumentbibliothek aus.

Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![Diagramm des OneDrive-Ordners mit dem Namen Microsoft Teams-Chat Dateien](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Registerkarte "Kanaldateien"

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Die Registerkarte **Dateien** in Microsoft Teams ähnelt der Ansicht SharePoint-Dokumente. Auf der Registerkarte " **Dateien** " können Benutzer:

- Weitere Optionen finden Sie im Menü " **neue** Datei".
- Synchronisieren Sie Dateien auf dem lokalen Laufwerk.
- Wechseln Sie im Menü **alle Dokumente** von der **Listen** Ansicht zur **kompaktliste** in die **Kachel** Ansicht.
- Ermitteln Sie Dateien, die auf die Berücksichtung oder Malware abstellen.
- Sehen Sie sofort, ob eine Datei schreibgeschützt oder ausgecheckt ist.
- Auschecken und Einchecken von Dateien
- Anheften, unpin und Ändern der Sortierreihenfolge von Dateien
- Ermitteln, welche Dateien Metadaten benötigen
- Wählen Sie aus vielen weiteren Filteroptionen aus.
- Gruppieren Sie Dateien basierend auf Spaltenüberschriften.
- Ändern Sie die Spalteneinstellungen (nach links oder rechts, ausblenden) und Spaltenbreite.

## <a name="default-link-type-setting"></a>Standardeinstellung für den Verknüpfungstyp

SharePoint und OneDrive verfügen über eine Administratoreinstellung zum Angeben des Standardverknüpfungstyp für Links, die für eine Datei erstellt werden. Teams nimmt denselben Ansatz an, indem die Einstellungen wieder verwendet werden, die der Administrator für SharePoint und OneDrive festlegt. Weitere Informationen zu diesem Ansatz finden Sie unter [Ändern des Standard Link Typs, wenn Benutzer Links für die Freigabe erhalten](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zur Funktionsweise von SharePoint mit Teams finden Sie unter [SharePoint und Teams: besser zusammen](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Wenn Sie mehr über die Gastfreundlichkeit in Teams erfahren möchten, lesen Sie, [wie die Gast Erfahrung aussieht](guest-experience.md).

