---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & OneDrive for Business-Interaktion mit Teams; Private Chatdateispeicherung & Interaktion zwischen Team, Standardkanal, & Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948623"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams

> [!Tip]
> Erfahren Sie in der folgenden Sitzung, wie Teams mit Azure Active Directory (AAD), Microsoft 365-Gruppen, Exchange, SharePoint und OneDrive for Business interagiert: [Microsoft Teams – Grundlagen](https://aka.ms/teams-foundations)

Jedes Team in Microsoft Teams verfügt über eine Teamwebsite in SharePoint Online, und jeder Standardkanal in einem Team erhält einen Ordner in der Standarddokumentbibliothek der Teamwebsite. In einer Unterhaltung freigegebene Dateien werden der Dokumentbibliothek automatisch hinzugefügt, und die in SharePoint festgelegten Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams widerspiegelt. Informationen zu den Auswirkungen des Änderns einer Websiteadresse in SharePoint finden Sie unter [Ändern einer Websiteadresse.](/sharepoint/change-site-address)

> [!NOTE]
> Dieser Artikel gilt nur für Standardkanäle. Die Architektur für private Kanäle ist von Standardkanälen verschieden. Jeder private Kanal verfügt über eine eigene SharePoint-Websitesammlung, die von der übergeordneten Teamwebsite getrennt ist. Weitere Informationen finden Sie unter [Private Kanäle in Microsoft Teams.](private-channels.md)

Private Chatdateien werden im OneDrive for Business-Ordner des Absenders gespeichert, und berechtigungen werden automatisch allen Teilnehmern im Rahmen des Dateifreigabevorgangs gewährt.

Wenn Benutzer nicht mit SharePoint Online-Lizenzen ausgestattet und diese aktiviert sind, verfügen sie nicht über einen OneDrive for Business-Speicher in Microsoft 365 oder Office 365. Die Dateifreigabe funktioniert weiterhin in Standardkanälen, aber Benutzer können Dateien in Chats ohne OneDrive for #A0 in Microsoft 365 oder Office 365 nicht freigeben.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. 

> [!NOTE]
> Die Lokale Integration von SharePoint wird für Microsoft Teams derzeit nicht unterstützt.

Im Folgenden sehen Sie das Beispiel für Beziehungen zwischen Team, Standardkanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Website erstellt, und der Ordner "Freigegebene Dokumente" ist der Standardordner, der für das Team erstellt wurde.  Jeder Standardkanal, einschließlich des **Kanals Allgemein** (der Standardkanal für jedes Team), verfügt über einen Ordner in **Freigegebene Dokumente.**

![Diagramm der Ordner "Freigegebene Dokumente" in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen. Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung. In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> So fügen Sie Ihrem Team eine Registerkarte hinzu, die mit einer vorhandenen SharePoint-Websiteseite oder ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft ist:
> 1. Wählen Sie das Pluszeichen neben den Registerkarten aus.
> 2. Wählen Sie **entweder SharePoint für** eine vorhandene SharePoint-Websiteseite oder **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek aus.
> 3. Wählen Sie die entsprechende Seite oder Dokumentbibliothek aus.

Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![Diagramm des OneDrive-Ordners "Microsoft Teams-Chatdateien"](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Beachten Sie, dass für öffentliche Teams die SharePoint-Teamwebsite mit dem Zugriff "Jeder außer externen Benutzern" bereitgestellt wird. Das öffentliche Team wird in Teams nicht für Personen angezeigt, die nicht Mitglied dieses Teams sind. Sie können jedoch über die URL der SharePoint-Teamwebsite auf Inhalte auf der SharePoint-Teamwebsite zugreifen. 

## <a name="channel-files-tab"></a>Registerkarte 'Kanaldateien'

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Die **Registerkarte Dateien** in Teams ähnelt der Ansicht "SharePoint-Dokumente". Auf der **Registerkarte** Dateien können Benutzer:

- Weitere Optionen finden Sie im **Menü Neue** Datei.
- Synchronisieren Sie Dateien mit ihrem lokalen Laufwerk.
- Wechseln Sie **im Menü** Alle Dokumente von der **Listenansicht** zur Liste **Komprimieren zur** **Kachelansicht.**
- Identifizieren Sie Dateien, die Aufmerksamkeit benötigen oder Schadsoftware enthalten.
- Sehen Sie sofort, ob eine Datei schreibgeschützt oder ausgecheckt ist.
- Auschecken und Einchecken von Dateien.
- Anheften, Losheften und Ändern der Sortierreihenfolge von Dateien
- Ermitteln, welche Dateien Metadaten benötigen
- Wählen Sie aus vielen weiteren Filteroptionen aus.
- Gruppieren sie Dateien basierend auf Spaltenüberschriften.
- Ändern Sie die Spalteneinstellungen (nach links oder rechts verschieben, ausblenden) und die Spaltenbreite.

## <a name="default-link-type-setting"></a>Standardeinstellung für den Linktyp

SharePoint und OneDrive verfügen über eine Administratoreinstellung zum Angeben des Standardlinktyps für Links, die für eine Datei erstellt werden. Teams verwendet denselben Ansatz, indem die Vom Administrator für SharePoint und OneDrive festgelegten Einstellungen erneut verwendet werden. Weitere Details zu diesem Ansatz finden Sie unter Ändern des [Standardlinktyps,](/sharepoint/change-default-sharing-link)wenn Benutzer Links für die Freigabe erhalten. 

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen zur Zusammenarbeit von SharePoint mit Teams finden Sie unter [SharePoint und Teams: Bessere Zusammenarbeit.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Weitere Informationen zur Gasterfahrung in Teams finden Sie unter [So sieht die Gasterfahrung aus.](guest-experience.md)