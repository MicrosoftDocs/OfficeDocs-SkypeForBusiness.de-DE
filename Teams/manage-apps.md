---
title: Verwalten Ihrer Apps im Microsoft Teams Admin Center
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Erfahren Sie, wie Sie Ihre Teams-apps auf der Seite "Apps verwalten" im Microsoft Teams Admin Center verwalten.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: d4abedbd24f9f0211a66b0890fe9d3db2fc977cd
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868482"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Verwalten Ihrer Apps im Microsoft Teams Admin Center
======================================================

Als Administrator können Sie auf der Seite " **apps verwalten** " im Microsoft Teams Admin Center alle Teams-apps im App-Katalog Ihrer Organisation anzeigen und verwalten. Hier können Sie den Status und die Eigenschaften von apps auf Organisationsebene anzeigen, neue benutzerdefinierte apps in ihren Mandanten-App-Katalog hochladen, Apps auf org-Ebene blockieren oder zulassen sowie organisationsweite App-Einstellungen verwalten.

Auf der Seite " **apps verwalten** " erhalten Sie einen Überblick über alle verfügbaren apps in Ihrem Mandanten Katalog, in dem Sie die Informationen finden, die Sie benötigen, um zu entscheiden, welche apps in Ihrer Organisation zugelassen oder blockiert werden sollen. Sie können dann [App-Berechtigungsrichtlinien](teams-app-permission-policies.md), [App-Setup Richtlinien](teams-app-setup-policies.md)und [benutzerdefinierte App-Richtlinien und-Einstellungen](teams-custom-app-policies-and-settings.md) verwenden, um die APP-Umgebung für bestimmte Benutzer in Ihrer Organisation zu konfigurieren.

Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**. Sie müssen ein globaler Administrator oder Team Dienstadministrator sein, um auf die Seite zugreifen zu können.

## <a name="view-apps-in-your-tenant-app-catalog"></a>Anzeigen von apps in Ihrem Mandanten-App-Katalog

Sie können jede app in Ihrem Mandanten-App-Katalog anzeigen, einschließlich der folgenden Informationen zu den einzelnen apps.

![Screenshot der Seite "verwaltete Apps"](media/manage-apps.png)

- **Name**: der Name der app. Klicken Sie auf den Namen der APP, um weitere Informationen zur APP anzuzeigen. Dies umfasst eine Beschreibung der APP, ob Sie zulässig oder gesperrt ist, Version, Kategorien, die für die APP gelten, den Zertifizierungsstatus, die unterstützten Funktionen und die APP-ID. Nachfolgend ein Beispiel:<br> 
![Screenshot der Seite "Apps-Details" für eine APP](media/manage-apps-app-details.png)
- **Zertifizierung**: Wenn die APP die Zertifizierung durchlaufen hat, wird entweder **Microsoft 365 Certified** oder **Publisher-Bestätigung**angezeigt. Klicken Sie auf den Link, um die Zertifizierungsdetails für die APP anzuzeigen. Wenn "" angezeigt **--** wird, verfügen wir nicht über Zertifizierungsinformationen für die app. Wenn Sie mehr über zertifizierte apps in Microsoft Teams erfahren möchten, lesen Sie [Microsoft 365-App-Zertifizierungsprogramm](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Kategorien**: Kategorien, die für die APP gelten.
- **App-Status**: Status der APP auf org-Ebene, die eine der folgenden Optionen sein kann:
    - **Zulässig**: die APP steht allen Benutzern in Ihrer Organisation zur Verfügung.
    - **Blockiert**: die APP ist blockiert und steht nicht für Benutzer in Ihrer Organisation zur Verfügung.
    - **Organisationsweit blockiert**: die APP wird in den organisationsweiten App-Einstellungen blockiert. <br>
Es ist wichtig zu wissen, dass diese Spalte den zulässigen und blockierten Status von apps darstellt, die sich zuvor im Bereich " **organisationsweite Einstellungen** " befanden. Sie können jetzt apps auf der Seite " **apps verwalten** " auf der Organisationsebene anzeigen, blockieren und zulassen. 
- **Version**: App-Version.

Wenn Sie die gewünschten Informationen in der Tabelle anzeigen möchten, klicken Sie in der oberen rechten Ecke auf **Spalte bearbeiten** , um der Tabelle Spalten hinzuzufügen oder daraus zu entfernen.

## <a name="upload-a-new-app"></a>Hochladen einer neuen App

Sie können Ihren app-Katalog verwenden, um benutzerdefinierte Anwendungen zu testen und zu verteilen, die speziell für Ihre Organisation entwickelt wurden. Ein Team-App-Paket wird mithilfe von [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)erstellt. Wenn Sie über das App-Paket verfügen, können Sie es dem App-Katalog hinzufügen. Während alle Benutzer in Ihrer Organisation den App-Katalog anzeigen können, können Sie nur von globalen Administratoren und Teams-Dienstadministratoren veröffentlicht und verwaltet werden.

Wenn Sie eine neue benutzerdefinierte app in ihren Mandanten-App-Katalog hochladen möchten, klicken Sie auf **neue APP hochladen** , um das App-Paket im ZIP-Format hochzuladen. Nachdem die APP hochgeladen wurde, wird Sie nicht hervorgehoben, sodass Sie Ihren app-Katalog durchsuchen müssen, um ihn zu finden.

Wenn Sie eine APP nach dem Hochladen aktualisieren möchten, klicken Sie in der Liste der apps auf der Seite **apps verwalten** auf den Namen der APP, und klicken Sie dann auf **Aktualisieren**. Dadurch wird die vorhandene App im App-Katalog ersetzt, und alle App-Berechtigungsrichtlinien und App-Setup Richtlinien bleiben für die aktualisierte APP erzwungen.

Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten apps in Teams](manage-your-custom-apps.md).

## <a name="allow-and-block-apps"></a>Zulassen und Blockieren von apps

Auf der Seite " **apps verwalten** " können Sie einzelne apps auf Organisationsebene zulassen oder blockieren. Sie zeigt alle verfügbaren apps und den aktuellen App-Status auf Organisationsebene an. (Das Blockieren und zulassen von apps auf der Organisationsebene wurde vom Bereich " **organisationsweite App-Einstellungen** " hierhin verschoben.)

Wenn Sie eine App zulassen oder blockieren möchten, wählen Sie Sie aus, und klicken Sie dann auf **zulassen** oder **blockieren**. Wenn Sie eine APP blockieren, werden alle Interaktionen mit dieser APP deaktiviert, und die APP wird nicht in Teams für alle Benutzer in Ihrer Organisation angezeigt.

Wenn Sie eine APP auf der Seite " **apps verwalten** " blockieren oder zulassen, wird diese APP für alle Benutzer in Ihrer Organisation blockiert oder zugelassen.  Wenn Sie eine app in einer Berechtigungsrichtlinie für Teams-App blockieren oder zulassen, ist Sie für Benutzer, denen diese Richtlinie zugewiesen ist, blockiert oder zulässig. Damit ein Benutzer eine App installieren und mit ihnen interagieren kann, müssen Sie die APP auf der Organisationsebene auf der Seite " **apps verwalten** " und in der APP-Berechtigungsrichtlinie zulassen, die dem Benutzer zugewiesen ist.

 > [!NOTE]
 > Wenn Sie eine APP deinstallieren möchten, klicken Sie mit der rechten Maustaste auf die APP, und klicken Sie dann auf **deinstallieren** oder verwenden Sie das Menü **Weitere apps** auf der linken Seite. 

## <a name="manage-org-wide-app-settings"></a>Verwalten von organisationsweiten App-Einstellungen

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer apps von Drittanbietern installieren können und ob Benutzer benutzerdefinierte apps in Ihrer Organisation hochladen oder mit ihnen interagieren können. Organisationsweite App-Einstellungen Regeln das Verhalten für alle Benutzer und überschreiben alle anderen APP-Berechtigungsrichtlinien, die Benutzern zugewiesen sind. Sie können Sie verwenden, um schädliche oder problematische apps zu steuern.

1. Wählen Sie auf der Seite **apps verwalten** die Option **organisationsweite App-Einstellungen**aus. Anschließend können Sie die gewünschten Einstellungen im Panel konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen](media/manage-apps-org-wide-app-settings.png)
    
2. Deaktivieren oder aktivieren Sie unter **apps von Drittanbietern**diese Einstellungen, um den Zugriff auf Drittanbieter-apps zu steuern:

    - **Drittanbieter-apps zulassen**: Hiermit wird gesteuert, ob Benutzer apps von Drittanbietern verwenden können. Wenn Sie diese Einstellung deaktivieren, sind Ihre Benutzer nicht in der Lage, Apps von Drittanbietern zu installieren oder zu verwenden, und der APP-Status dieser Apps wird in der Tabelle als **blockiert org-weit** angezeigt.

        > [!NOTE]
        > In einer Microsoft 365 Government-gcc-Bereitstellung von Teams ist die Einstellung **Drittanbieter-apps in Teams zulassen** standardmäßig deaktiviert.

        Wenn **Drittanbieter-apps zulassen** deaktiviert ist, werden [ausgehende webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) deaktiviert, was bedeutet, dass Benutzer Sie nicht erstellen können. Wenn diese Einstellung aktiviert ist, werden ausgehende webhooks für alle Benutzer aktiviert, unabhängig davon, ob die Einstellung in der APP-Berechtigungsrichtlinie für Benutzer aktiviert oder deaktiviert ist.
    - **Alle neuen Drittanbieter-apps zulassen, die standardmäßig im Store veröffentlicht**werden: Hiermit wird gesteuert, ob neue Drittanbieter-apps, die im App Store für Teams veröffentlicht werden, automatisch in Teams verfügbar sind. Diese Option kann nur festgesetzt werden, wenn Sie Drittanbieter-apps zulassen.

3. Deaktivieren oder aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**. Mit dieser Einstellung wird gesteuert, ob Benutzer mit benutzerdefinierten apps interagieren können. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und-Einstellungen in Teams](teams-custom-app-policies-and-settings.md).
4. Klicken Sie auf **Speichern** , damit die App-Einstellungen für die gesamte Organisation wirksam werden.

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
