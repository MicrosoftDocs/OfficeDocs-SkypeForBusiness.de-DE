---
title: Freigabe von Dateien in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Dateifreigabe in Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138353"
---
# <a name="sharing-files-in-microsoft-teams"></a>Freigabe von Dateien in Microsoft Teams

In Microsoft Teams können Benutzer Inhalte für andere Team Benutzer innerhalb und außerhalb Ihrer Organisation freigeben. Die Freigabe in Teams basiert auf den in SharePoint und OneDrive konfigurierten Einstellungen, sodass die für SharePoint und OneDrive eingerichteten Einstellungen auch die Freigabe in Teams steuern.

## <a name="overview"></a>Übersicht

Benutzer können Dateien aus OneDrive, aus Teams und Websites, auf die Sie Zugriff haben, und von Ihrem Computer aus freigeben. Zum Freigeben einer Datei können Benutzer die folgenden Aktionen ausführen:

- Klicken Sie in einem Kanal auf **Anfügen** (das Büroklammersymbol), wählen Sie **zuletzt**verwendet, **Teams und Kanäle durchsuchen**, **OneDrive**oder **vom Arbeitsplatz Hochladen aus**, und wählen Sie dann die Datei aus, die Sie freigeben möchten. <br> 
    ![Screenshot, der zeigt, wie eine Datei über einen Kanal freigegeben wird](media/share-files-channel.png)
- Klicken Sie in einem Chat auf **Anfügen** (das Büroklammersymbol), wählen oder **OneDrive** oder auf **vom Arbeitsplatz Hochladen aus**, und wählen Sie dann die Datei aus, die Sie freigeben möchten. <br>
    ![Screenshot, der zeigt, wie eine Datei über einen Chat freigegeben wird](media/share-files-chat.png)
- Kopieren Sie den Link Freigabe, und fügen Sie ihn in das Feld zum Verfassen ein.<br>
    ![Screenshot mit Dateivorschau im Feld zum Verfassen](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Was Sie über die gemeinsame Nutzung von Dateien wissen müssen

### <a name="permissions-of-shared-files-and-sharing-links"></a>Berechtigungen für freigegebene Dateien und Freigabelinks

Wenn Benutzer eine Datei freigeben, indem Sie Sie in OneDrive oder in Teams und Kanälen durchsuchen, werden allen Empfängern Zugriff zusammen mit der [Standardberechtigung gewährt, die auf Organisationsebene festgesetzt ist](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Wenn ein Benutzer einen Freigabe Link kopiert und einfügt, werden die für diesen Freigabe Link festgelegten Berechtigungen berücksichtigt, und die SharePoint-URL wird auf den Dateinamen verkürzt. Mit anderen Worten: Teams verwendet nur den Dateinamen, um eine Verknüpfung mit einer Datei zu erstellen.

Wenn Benutzer eine Datei in Microsoft Teams freigeben, können Sie die Personen, die auf die Datei zugreifen können, genau wie in Microsoft 365 einstellen. Sie können jedem Personen, Personen in Ihrer Organisation, Personen mit vorhandenem Zugriff oder bestimmten Personen (die Personen in einem 1:1-Chat, Gruppen-Chat oder Kanal einbeziehen können) Zugriff gewähren.  Wenn eine Datei freigegeben ist, ist die Dateivorschau in der Nachricht zusammen mit allen Dateiaktionen wie " **Online öffnen**", " **herunterladen**" und " **Link kopieren**" verfügbar. Standardmäßig wird die Datei in Teams geöffnet. Manchmal wurde der Freigabe Link möglicherweise nicht in eine Dateivorschau konvertiert, wenn ein Benutzer die Nachricht sendet. Die Dateivorschau wird vom System generiert, in diesem Szenario wird der Freigabe Link jedoch nicht auf den Dateinamen verkürzt.

Wenn Benutzer eine Datei in einem Chat oder Kanal freigeben, werden Sie benachrichtigt, ob einige oder alle Empfänger nicht über die Berechtigung zum Anzeigen der Datei verfügen. Sie können die Berechtigungen für die Datei ändern, bevor Sie Sie freigeben, indem Sie auf den Pfeil neben der Dateivorschau klicken, die nun in der Nachricht angezeigt wird.

![Screenshot der Benachrichtigung, wenn Empfänger keine Berechtigungen besitzen](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Kopieren eines Freigabelinks in Teams

Benutzer können einen SharePoint-Freigabe Link kopieren und Freigabeberechtigungen genauso wie in Microsoft 365 ändern. Sie können jedem Personen, Personen in Ihrer Organisation, Personen mit vorhandenem Zugriff oder bestimmten Personen Zugriff gewähren. Die Standardberechtigung für den Link entspricht dem Standardberechtigungssatz auf Organisationsebene, es sei denn, die Berechtigungen für die SharePoint-Websiteebene überschreiben ihn.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Konfigurieren der Freigabe in OneDrive und SharePoint

Weitere Informationen zum Freigeben von Dateien in OneDrive und SharePoint, einschließlich der Konfiguration der Freigabe und der Aktivierung und Deaktivierung von Freigaben, finden Sie unter:

- [Übersicht über externe Freigabe](https://docs.microsoft.com/sharepoint/external-sharing-overview) – beschreibt, was geschieht, wenn Benutzer die Freigabe durchgeführt haben, je nachdem, was Sie teilen und mit wem.

- [Verwalten von Freigabeeinstellungen](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – beschreibt, wie globale und SharePoint-Administratoren ihre Freigabeeinstellungen auf Organisationsebene für SharePoint und OneDrive ändern können.

- [Aktivieren oder Deaktivieren der externen Freigabe für eine Website](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – beschreibt, wie globale und SharePoint-Administratoren die externe Freigabe für eine Website aktivieren oder deaktivieren können.

- [Ändern des Standard Verknüpfungstyps für eine Website](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – beschreibt, wie Sie den Standardverknüpfungstyp so festlegen, dass er restriktiver ist.

## <a name="more-information"></a>Weitere Informationen

- [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint und Teams: besser zusammen](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Freigeben von SharePoint-Dateien oder-Ordnern](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
