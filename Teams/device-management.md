---
title: Verwalten Ihrer Geräte in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: Hier erfahren Sie, wie Sie Geräte verwalten, die mit Teams in Ihrer Organisation verwendet werden.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b259b893f443a068b8156f2298613b0feb6d028
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237503"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Verwalten Ihrer Geräte in Microsoft Teams

::: zone target="docs"
Als Administrator verwalten Sie alle Geräte, die mit Teams in Ihrer Organisation verwendet werden, im Microsoft Teams #a0 Skype for Business Admin Center. Sie können die Geräte Inventur für Ihre Organisation anzeigen und verwalten sowie Aufgaben wie aktualisieren, Neustarten und Überwachen der Diagnose für Geräte ausführen. Sie können auch einem Gerät oder einer Gruppe von Geräten Konfigurationsprofile erstellen und zuweisen. 

## <a name="what-devices-can-you-manage"></a>Welche Geräte können verwaltet werden?
Geräte müssen für Teams zertifiziert und in Teams registriert sein. Ein Gerät wird automatisch registriert, wenn sich ein Benutzer zum ersten Mal bei Teams auf dem Gerät anmeldet. Eine Liste der zertifizierten Geräte, die verwaltet werden können, finden Sie unter [Konferenztelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) und [Tischtelefone](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).

> [!NOTE]
> Wenn Sie über Microsoft InTune verfügen, werden Geräte automatisch in InTune registriert. Nachdem ein Gerät registriert wurde, wird die Gerätekompatibilität bestätigt, und auf das Gerät werden Richtlinien für den bedingten Zugriff angewendet. 

## <a name="manage-devices-in-teams"></a>Verwalten von Geräten in Teams

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.
2. Wählen Sie **alle Geräte**aus.  

::: zone-end

 Hier können Sie alle Geräte anzeigen und verwalten, die für Teams in Ihrer Organisation registriert sind. Zu den Informationen, die Sie für jedes Gerät sehen, gehören Gerätename, Hersteller, Modell, Benutzer, Status, Aktion, zuletzt gesehen und Verlauf. Sie können die Ansicht anpassen, um die Informationen anzuzeigen, die Ihren Anforderungen entsprechen.

 Nachfolgend finden Sie einige Beispiele für die Verwaltung von Teams-Geräten in Ihrer Organisation.  
    
|Zu diesem Zweck...  |Tun Sie dies |
|---------|---------|
|Ändern von Geräteinformationen   | Wählen Sie ein Gerät #a0 **Bearbeiten**aus. Sie können Details wie Gerätename, Benutzerinformationen, Inventar Kategorien und Notizen bearbeiten.     |
|Verwalten von Softwareupdates   |Wählen Sie ein Gerät #a0 **Update**aus. Sie können die Liste der für das Gerät verfügbaren Software-und Firmware-Updates anzeigen und die zu installierenden Updates auswählen.    |
|Starten eines Geräts   |Wählen Sie ein Gerät #a0 **Neustart**aus.          |
|Geräte Verlauf anzeigen  | Wählen Sie ein Gerät #a0 **Verlauf**aus. Sie können den Updateverlauf für das Gerät anzeigen.     |
|Anzeigen von Diagnosen  | Wählen Sie ein Gerät #a0 **Diagnose**aus.        |

## <a name="use-configuration-profiles-in-teams"></a>Verwenden von Konfigurationsprofilen in Teams

Verwenden Sie Konfigurationsprofile, um Einstellungen und Features für Teams-Geräte in Ihrer Organisation zu verwalten. Sie können Konfigurationsprofile erstellen oder hochladen, um Einstellungen und Features einzubeziehen, die Sie aktivieren oder deaktivieren möchten, und dann einem Gerät oder einer Gruppe von Geräten ein Profil zuweisen. 

### <a name="create-a-configuration-profile"></a>Erstellen eines Konfigurationsprofils

::: zone target="docs"

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) Verwenden des Microsoft Teams #a0 Skype for Business Admin Center

1. Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.

::: zone-end

2. Wählen Sie **Konfigurationsprofile**aus, und wählen Sie dann **Neues Konfigurationsprofil**aus.
3. Geben Sie einen Namen für das Profil ein, und fügen Sie bei Bedarf eine Beschreibung hinzu.
4. Geben Sie die gewünschten Einstellungen für das Profil ein, und klicken Sie auf **Speichern**.

### <a name="assign-a-configuration-profile"></a>Zuweisen eines Konfigurationsprofils

::: zone target="docs"

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) Verwenden des Microsoft Teams #a0 Skype for Business Admin Center

1. Navigieren Sie in der linken Navigationsleiste zu **Devices** > **Manage Devices**.

::: zone-end

2. Wählen Sie **Konfigurationsprofil**aus, und klicken Sie dann unter **zugewiesen an** in dem Profil, das Sie zuweisen möchten, auf den Link.  
3. Suchen Sie im Bereich **Geräte zu einem Konfigurationsprofil zuweisen** nach den Geräten, die Sie zuweisen möchten, und wählen Sie Sie aus.
4. Klicken Sie auf **Speichern**.
