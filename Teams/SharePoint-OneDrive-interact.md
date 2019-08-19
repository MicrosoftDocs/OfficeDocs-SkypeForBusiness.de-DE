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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232278"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams

> [!Tip]
> Erfahren Sie in der folgenden Sitzung, wie Teams mit Azure Active Directory (AAD), Office 365-Gruppen, Exchange, SharePoint und OneDrive for Business interagiert: [Microsoft Teams – Grundlagen](https://aka.ms/teams-foundations)

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.

Wenn Benutzer nicht mit SharePoint Online-Lizenzen ausgestattet und diese aktiviert sind, verfügen sie nicht über einen OneDrive for Business-Speicher in Office 365. Die Dateifreigabe ist in Kanälen weiterhin möglich, ohne OneDrive for Business-Speicher in Office 365 können die Benutzer jedoch keine Dateien in Chats freigeben.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. 

> [!NOTE]
> Die Integration in lokale SharePoint-Umgebungen wird für Microsoft Teams zurzeit nicht unterstützt.

Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.

![Diagramm der Ordner "Freigegebene Dokumente" in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen. Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung. In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.

> [!TIP]
> So fügen Sie Ihrem Team eine Registerkarte mit einer Verknüpfung zu einer bestehenden SharePoint-Website oder zu Ihrer bestehenden SharePoint-Dokumentbibliothek hinzu:
> 1. Wählen Sie das Pluszeichen neben den Registerkarten aus.
> 2. Wählen Sie entweder **SharePoint** für eine bestehende SharePoint-Website oder **Dokumentbibliothek** für eine bestehende Dokumentbibliothek aus.
> 3. Wählen Sie die entsprechende Seite oder Dokumentbibliothek aus.

Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![Diagramm des OneDrive-Ordners "Microsoft Teams-Chatdateien"](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Registerkarte "Kanaldateien"

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Die Registerkarte **Dateien** in Teams ähnelt der SharePoint-Dokumentansicht. Auf der Registerkarte **Dateien** haben Benutzer folgende Möglichkeiten:

- Weitere Optionen im Datei-Menü **Neu** anzeigen
- Dateien mit dem lokalen Laufwerk synchronisieren
- Im Menü **Alle Dokumente** von der **Listen**-Ansicht zu **Kompaktliste** und **Kacheln** wechseln
- Dateien ermitteln, die Aufmerksamkeit erfordern oder Schadsoftware aufweisen
- Sofort sehen, ob eine Datei schreibgeschützt oder ausgecheckt ist
- Dateien einchecken und auschecken
- Die Sortierreihenfolge von Dateien anheften, ablösen und ändern
- Bestimmen, welche Dateien Metadaten benötigen
- Aus vielen weiteren Filteroptionen auswählen
- Dateien basierend auf Spaltenüberschriften gruppieren
- Spalteneinstellungen (nach links oder rechts, ausblenden) und Spaltenbreite ändern

## <a name="default-link-type-setting"></a>Einstellungen für Standardlinktyp

SharePoint und OneDrive verfügen über eine Administratoreinstellung zum Angeben des Standardlinktyps für Links, die für eine Datei erstellt werden. Der selbe Ansatz wird in Teams angewendet durch die Übernahme der Einstellungen, die ein Administrator für SharePoint und OneDrive festlegt. Weitere Details zu diesem Ansatz finden Sie unter [Ändern des Standardlinktyps, wenn Benutzer Links für die Freigabe erhalten](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen dazu, wie SharePoint mit Teams funktioniert, finden Sie unter [SharePoint und Teams: zusammen noch besser](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Näheres über den Gastzugriff in Teams erfahren Sie in dem Artikel zur [Gastfunktionalität](guest-experience.md)

