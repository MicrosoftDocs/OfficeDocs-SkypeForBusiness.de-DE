---
title: Interaktion SharePoint und OneDrive mit Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive Interaktion mit Teams; Private Chatdateispeicherung & Interaktion zwischen Team, Standardkanal, & Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855954"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Interaktion SharePoint und OneDrive mit Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Microsoft 365-Gruppen, Exchange,SharePoint [](https://aka.ms/teams-foundations) und OneDrive interagiert: Grundlagen Microsoft Teams

Jedes Team in Microsoft Teams verfügt über eine Teamwebsite in SharePoint, und jeder Standardkanal in einem Team erhält einen Ordner innerhalb der standardmäßigen Teamwebsite-Dokumentbibliothek. Jeder [private Kanal erhält](private-channels.md) eine eigene, separate SharePoint Website.

In einer Unterhaltung freigegebene Dateien werden der Dokumentbibliothek automatisch hinzugefügt, und die in den Dateien SharePoint festgelegten Berechtigungen und Sicherheitsoptionen werden Teams. Informationen zu den Auswirkungen des Änderns einer Websiteadresse in SharePoint Sie unter [Ändern einer Websiteadresse.](/sharepoint/change-site-address)

Private Chatdateien werden im Ordner OneDrive des Absenders gespeichert, und im Rahmen des Dateifreigabeprozesses werden allen Teilnehmern automatisch Berechtigungen erteilt.

Wenn Benutzern keine Lizenzen zugewiesen SharePoint, verfügen sie nicht über OneDrive in Microsoft 365. Die Dateifreigabe funktioniert in Standardkanälen, aber Benutzer können Dateien in Chats nur freigeben, wenn OneDrive in Microsoft 365.

Durch das Speichern der Dateien in SharePoint Dokumentbibliothek und OneDrive werden alle auf Organisationsebene konfigurierten Complianceregeln befolgt. 

> [!NOTE]
> Die Integration SharePoint Server wird für Teams.

Im Folgenden finden Sie ein Beispiel für Beziehungen zwischen Team, Standardkanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint erstellt,  und der Ordner "Freigegebene Dokumente" ist der Standardordner, der für das Team erstellt wird. Jeder Standardkanal, einschließlich des **Kanals Allgemein** (der Standardkanal für jedes Team), verfügt über einen Ordner unter **Freigegebene Dokumente.**

![Diagramm der Ordner "Freigegebene Dokumente" in SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Die Standardwebsite SharePoint Dokumentbibliothek kann nicht durch eine andere ersetzt werden.

Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![Diagram of the OneDrive folder named Microsoft Teams Chat Files](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Beachten Sie, dass für öffentliche Teams SharePoint Teamwebsite der Zugriff "Jeder, außer externen Benutzern" bereitgestellt wird. Das öffentliche Team wird nicht in einer Teams für Personen angezeigt, die keine Mitglieder dieses Teams sind. Sie können jedoch über die URL der SharePoint Teamwebsite auf SharePoint Website zugreifen. 

## <a name="channel-files-tab"></a>Registerkarte "Kanaldateien"

Die **Registerkarte** "Dateien" in Teams der Ansicht "SharePoint Dokumente" sehr ähnlich. Auf der **Registerkarte** Dateien können Benutzer:

- Weitere Optionen finden Sie im **Menü Neue** Datei.
- Synchronisieren Sie Dateien mit ihrem lokalen Laufwerk.
- Wechseln Sie **im Menü Alle** Dokumente von der **Listenansicht** zur Liste **Kompakt in** die **Ansicht Kacheln.**
- Identifizieren Sie Dateien, die Aufmerksamkeit benötigen oder Schadsoftware enthalten.
- Prüfen Sie sofort, ob eine Datei schreibgeschützt oder ausgecheckt ist.
- Auschecken und Einchecken von Dateien.
- Anheften, Losheften und Ändern der Sortierreihenfolge von Dateien
- Identifizieren der Dateien, die Metadaten benötigen
- Wählen Sie aus vielen weiteren Filteroptionen aus.
- Gruppieren sie Dateien anhand von Spaltenüberschriften.
- Ändern Sie die Spalteneinstellungen (nach links oder rechts verschieben, ausblenden) und die Spaltenbreite.

## <a name="default-link-type-setting"></a>Einstellung für Standardlinktyp

Der standardmäßig angezeigte Freigabelinktyp, wenn ein Benutzer eine Datei freigegeben hat, wird im SharePoint Admin Center festgelegt. Weitere [Informationen finden Sie unter Ändern des Standardlinktyps,](/sharepoint/change-default-sharing-link) wenn Benutzer Links für die Freigabe erhalten.

## <a name="related-topics"></a>Verwandte Themen

[SharePoint und Teams: zusammen besser.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

[Gastfunktionalität](guest-experience.md)