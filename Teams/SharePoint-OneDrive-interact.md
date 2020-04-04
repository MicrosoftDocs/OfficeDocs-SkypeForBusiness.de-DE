---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & OneDrive for Business-Interaktion mit Teams; Speicherung privater Chat-Dateien & Interaktion zwischen Team, Standardkanal & Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fd34bf368667fcfa5776de40cad0d1444440805a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137255"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Jedes Team in Microsoft Teams hat eine Teamwebsite in SharePoint Online, und jeder Standardkanal in einem Team erhält einen Ordner in der standardmäßigen Teamwebsite-Dokumentbibliothek. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und die in SharePoint gesetzten Berechtigungen und Datei Sicherheitsoptionen werden in Teams automatisch wiedergegeben. Wenn Sie sehen möchten, welche Auswirkungen das Ändern einer Websiteadresse in SharePoint hat, lesen Sie [Ändern einer Websiteadresse](https://docs.microsoft.com/sharepoint/change-site-address).

> [!NOTE]
> Dieser Artikel bezieht sich nur auf Standardkanäle. Die Architektur für private Kanäle unterscheidet sich von Standardkanälen. Jeder private Kanal verfügt über eine eigene SharePoint-Websitesammlung, die von der übergeordneten Teamwebsite getrennt ist. Weitere Informationen finden Sie unter [private Kanäle in Microsoft Teams](private-channels.md).

Private Chat-Dateien werden im OneDrive for Business-Ordner des Absenders gespeichert, und Berechtigungen werden allen Teilnehmern im Rahmen des Dateifreigabe Prozesses automatisch gewährt.

Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Standardkanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. 

> [!NOTE]
> Die Integration in SharePoint lokal wird für Microsoft Teams zurzeit nicht unterstützt.

Im folgenden finden Sie ein Beispiel für Beziehungen zwischen Team, Standardkanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Website erstellt, und der Ordner " **freigegebene Dokumente** " ist der Standardordner, der für das Team erstellt wurde. Jeder Standardkanal, einschließlich des **allgemeinen** Kanals (der Standardkanal für jedes Team), verfügt über einen Ordner in **freigegebenen Dokumenten**.

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

