---
title: Verwalten Ihrer Geräte in Microsoft Teams
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
ms.openlocfilehash: f1cf2dcc1d300490d1b3049c9513d0c4e16c3f83
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760591"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Verwalten Ihrer Geräte in Microsoft Teams

::: zone target="docs"
Als Administrator verwalten Sie alle Geräte mit Teams in Ihrer Organisation aus der Microsoft-Teams & Skype für Business-Verwaltungskonsole verwendet. Anzeigen und Verwalten der Geräteübersicht für Ihre Organisation, und führen Aufgaben wie das Update, neu und Monitordiagnose für Geräte. Sie können auch ein Gerät oder Gerätegruppen Konfigurationsprofile zuzuweisen. 

## <a name="what-devices-can-you-manage"></a>Welche Geräte können Sie verwalten?
Geräte müssen für Teams zertifiziert und Teams registriert werden. Ein Gerät wird automatisch beim ersten registriert, die ein Benutzer bei Teams auf dem Gerät anmeldet. Eine Liste mit zertifizierten Geräte, die verwaltet werden können, finden Sie unter [Konferenz Mobiltelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) und [herkömmliche Telefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).

> [!NOTE]
> Wenn Sie Microsoft Intune verfügen, werden automatisch Geräte Intune registriert. Nachdem ein Gerät registriert, Gerät Compliance bestätigt wurde, und bedingte Zugriffsrichtlinien auf das Gerät angewendet werden. 

## <a name="manage-devices-in-teams"></a>Verwalten von Geräten in Teams

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.
2. Wählen Sie **alle Geräte**aus.  

::: zone-end

 Von hier aus können Sie anzeigen und verwalten alle Geräte in Ihrer Organisation in Teams registriert. Informationen, die Sie für jedes Gerät sehen enthält Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, letzten angezeigt und Verlauf. Sie können die Ansicht, um die Informationen anzeigen, die Ihren Anforderungen entspricht anpassen.

 Nachfolgend finden Sie einige Beispiele, wie Sie Teams Geräte in Ihrer Organisation verwalten können.  
    
|Hierzu...  |Aktion... |
|---------|---------|
|Geräteinformationen ändern   | Wählen Sie ein Gerät > **Bearbeiten**aus. Sie können Bearbeiten der Details wie Gerätename, Benutzerinformationen, Asset-Tags und Notizen hinzufügen.     |
|Verwalten von Softwareupdates   |Wählen Sie ein Gerät > **Update**aus. Sie können die Liste der Software- und Firmwareupdates Updates für das Gerät anzeigen, und wählen Sie zur Installation der Updates.    |
|Neustart eines Geräts   |Wählen Sie ein Gerät > **neu zu starten**.          |
|Gerät-Historie anzeigen  | Wählen Sie ein Gerät > **Verlauf**aus. Sie können den Updateverlauf für das Gerät anzeigen.     |
|Ansicht Diagnose  | Wählen Sie ein Gerät > **Diagnose**aus.        |

## <a name="use-configuration-profiles-in-teams"></a>Verwenden Sie Konfigurationsprofile in Teams

Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams Geräte in Ihrer Organisation zu verwalten. Sie können erstellen oder Hochladen Konfigurationsprofile zum Einschließen von Einstellungen und Features zu aktivieren oder deaktivieren, und weisen Sie einem Profil ein Gerät oder Gruppen von Geräten. 

### <a name="create-a-configuration-profile"></a>Erstellen Sie ein Konfigurationsprofil

::: zone target="docs"

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business-Verwaltungskonsole

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.

::: zone-end

2. Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann auf **neues Konfigurationsprofil**.
3. Geben Sie einen Namen für das Profil, und wenn Sie möchten, fügen Sie eine benutzerfreundliche Beschreibung.
4. Geben Sie die Einstellungen, die Sie für das Profil verwenden möchten, und klicken Sie dann auf **Speichern**.

### <a name="assign-a-configuration-profile"></a>Zuweisen eines Konfigurationsprofils

::: zone target="docs"

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden die Microsoft-Teams & Skype für Business-Verwaltungskonsole

1. Wechseln Sie im linken Navigationsbereich auf **Geräte** > **Geräte verwalten**.

::: zone-end

2. Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in das Profil, das Sie zuweisen möchten, klicken Sie auf den Link.  
3. Suchen Sie und wählen Sie die Geräte, die Sie zuweisen möchten, klicken Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** .
4. Klicken Sie auf **Speichern**.
