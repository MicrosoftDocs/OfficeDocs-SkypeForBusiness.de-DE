---
title: Verwalten von Geräten in Microsoft-Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Erfahren Sie, wie mit Teams in Ihrer Organisation verwendeten Geräte verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97fd4b8d7f613c6d3f435f2d505bbd2cf99d4b10
ms.sourcegitcommit: 853760e8d926fed7176c23754197442ccd860e6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26285925"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Verwalten von Geräten in Microsoft-Teams

 Als Administrator verwalten Sie alle Geräte mit Teams in Ihrer Organisation aus dem Microsoft-Teams & Skype für Business-Verwaltungskonsole verwendet. Anzeigen und Verwalten der Geräteübersicht für Ihre Organisation, und führen Aufgaben wie das Update, neu und Monitordiagnose für Geräte. Sie können auch ein Gerät oder Gerätegruppen Konfigurationsprofile zuzuweisen. 

## <a name="what-devices-can-you-manage"></a>Welche Geräte können Sie verwalten?
Geräte müssen für Teams zertifiziert und Teams registriert werden. Ein Gerät wird automatisch beim ersten registriert, die ein Benutzer bei Teams auf dem Gerät anmeldet. 

> [!NOTE]
> Wenn Sie Microsoft Intune verfügen, werden automatisch Geräte Intune registriert. Nachdem ein Gerät registriert, Gerät Compliance bestätigt wurde, und bedingte Zugriffsrichtlinien auf das Gerät angewendet werden. 

## <a name="manage-devices-in-teams"></a>Verwalten von Geräten in Teams

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.
2. Wählen Sie **alle Geräte**aus.  

 Von hier aus können Sie anzeigen und verwalten alle Geräte in Ihrer Organisation in Teams registriert. Informationen, die Sie für jedes Gerät sehen enthält Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, letzten angezeigt und Verlauf. Sie können die Ansicht, um die Informationen anzeigen, die Ihren Anforderungen entspricht anpassen.

 Nachfolgend finden Sie einige Beispiele, wie Sie Teams Geräte in Ihrer Organisation verwalten können.  
    
|Hierzu...  |Aktion... |
|---------|---------|
|Geräteinformationen ändern   | Wählen Sie ein Gerät > **Bearbeiten**. Sie können Bearbeiten der Details wie Gerätename, Benutzerinformationen, Asset-Tags und Notizen hinzufügen.     |
|Verwalten von Softwareupdates   |Wählen Sie ein Gerät > **Update**. Sie können die Liste der Software- und Firmwareupdates Updates für das Gerät anzeigen, und wählen Sie zur Installation der Updates.    |
|Neustart eines Geräts   |Wählen Sie ein Gerät > **neu zu starten**.          |
|Gerät-Historie anzeigen  | Wählen Sie ein Gerät > **Verlauf**. Sie können den Updateverlauf für das Gerät anzeigen.     |
|Ansicht Diagnose  | Wählen Sie ein Gerät > **Diagnose**.        |

## <a name="use-configuration-profiles-in-teams"></a>Verwenden Sie Konfigurationsprofile in Teams

Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams Geräte in Ihrer Organisation zu verwalten. Sie können erstellen oder Hochladen Konfigurationsprofile zum Einschließen von Einstellungen und Features zu aktivieren oder deaktivieren, und weisen Sie einem Profil ein Gerät oder Gruppen von Geräten. 

### <a name="create-a-configuration-profile"></a>Erstellen Sie ein Konfigurationsprofil

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.
2. Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann auf **neues Konfigurationsprofil**.
3. Geben Sie einen Namen für das Profil, und wenn Sie möchten, fügen Sie eine benutzerfreundliche Beschreibung.
4. Geben Sie die Einstellungen, die Sie für das Profil verwenden möchten, und klicken Sie dann auf **Speichern**.

### <a name="assign-a-configuration-profile"></a>Zuweisen eines Konfigurationsprofils

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business Administrationscenter

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.
2. Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in das Profil, das Sie zuweisen möchten, klicken Sie auf den Link.  
3. Suchen Sie und wählen Sie die Geräte, die Sie zuweisen möchten, klicken Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** .
4. Klicken Sie auf **Speichern**.
