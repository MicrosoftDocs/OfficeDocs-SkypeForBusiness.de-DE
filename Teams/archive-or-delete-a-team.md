---
title: Archivieren oder Löschen eines Teams in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Hier erfahren Sie, wie Sie ein Team archivieren oder endgültig löschen.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdbc5a03698fc5aa8cd7d686ad0c3038132236f1
ms.sourcegitcommit: 21ef0846c8d9bc986550d34614bae1cb9eb2ded8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980575"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivieren oder Löschen eines Teams in Microsoft Teams
===========================================

Im Laufe der Zeit kann ein Team, das in Microsoft Teams erstellt wurde, möglicherweise nicht mehr verwendet werden, oder Sie möchten ein Team am Ende eines Projekts archivieren oder löschen. Wenn Sie ein Microsoft Teams-Administrator sind, führen Sie die in diesem Artikel aufgeführten Schritte aus, um ein nicht mehr benötigtes Team zu archivieren oder zu löschen. Wenn Sie ein Team archivieren, werden alle Aktivitäten für dieses Team beendet, aber Sie können weiterhin Mitglieder hinzufügen oder entfernen sowie Rollen aktualisieren, und Sie können weiterhin alle Teamaktivitäten in Kanälen, Dateien und Chats anzeigen. Wenn Sie ein Team löschen, werden die Teamaktivitäten in zugeordneten Kanälen, Dateien und Chats ebenfalls gelöscht.

> [!IMPORTANT]
> Archivierte Teams können wieder aktiviert werden, aber Sie können ein gelöschtes Team nicht direkt löschen. In diesem Fall sollten Sie das Team zunächst archivieren und den Löschvorgang verschieben, bis Sie sicher sind, dass Sie das Team nicht mehr benötigen.

## <a name="archive-a-team"></a>Archivieren eines Teams

Führen Sie die folgenden Schritte aus, um ein Team zu archivieren.

1. Wählen Sie im Microsoft Teams Admin Center **Teams**aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **archivieren**aus. Die folgende Meldung wird angezeigt.

    ![Screenshot der Meldung "Teams archivieren"](media/teams-archive-message.png)

4. Wenn Sie möchten, dass die SharePoint-Website für das Team schreibgeschützt ist, aktivieren Sie das Kontrollkästchen.
5. Wählen Sie **archivieren** aus, um das Team zu archivieren. Der Status des Teams wird in **archiviert**geändert.

## <a name="make-an-archived-team-active"></a>Aktivieren eines archivierten Teams

Führen Sie die folgenden Schritte aus, um ein archiviertes Team erneut zu aktivieren.

1. Wählen Sie im Microsoft Teams Admin Center **Teams**aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **archivieren**aus. Der Status des Teams wird in " **aktiv**" geändert.

## <a name="delete-a-team"></a>Löschen eines Teams

Wenn das Team in Zukunft nicht mehr benötigt wird, können Sie es löschen, anstatt es zu archivieren. Führen Sie die folgenden Schritte aus, um ein Team zu löschen.

1.  Wählen Sie im Microsoft Teams Admin Center **Teams**aus.
2.  Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3.  Wählen Sie **Löschen**aus. Eine Bestätigungsmeldung wird angezeigt.
4.  Wählen Sie **Löschen** aus, um das Team endgültig zu löschen.

## <a name="restore-a-deleted-team"></a>Wiederherstellen eines gelöschten Teams

Führen Sie die folgenden Schritte aus, um ein gelöschtes Team wiederherzustellen, indem Sie die Office 365-Gruppe wiederherstellen, die dem Team zugeordnet ist. Standardmäßig wird eine gelöschte Office 365-Gruppe 30 Tage lang aufbewahrt. Dieser Zeitraum von 30 Tagen wird als "Soft-Delete" bezeichnet, da Sie die Gruppe wiederherstellen können. Weitere Informationen finden Sie unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installieren des AzureADPreview-Moduls

1. Öffnen Sie Windows PowerShell als Administrator.
2. Wenn Sie eine frühere Version des AzureADPreview-Moduls installiert oder das AzureAD-Modul installiert haben, deinstallieren Sie es, indem Sie eine der folgenden Aktionen ausführen:

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. Installieren Sie die neueste Version des AzureADPreview-Moduls, indem Sie Folgendes ausführen:

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>Wiederherstellen der gelöschten Office 365-Gruppe

1. Stellen Sie eine Verbindung mit Azure AD her, indem Sie Folgendes ausführen:
    ```
    Connect-AzureAD
    ```
    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Administratorkonto und Kennwort an.  
2. Führen Sie die folgenden Schritte aus, um eine Liste aller Soft-Deleted Office 365-Gruppen anzuzeigen, die sich noch innerhalb des Aufbewahrungszeitraums von 30 Tagen befinden. Verwenden Sie den Parameter **-all $true** , wenn viele Gruppen vorhanden sind.
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. Suchen Sie die Gruppe, die Sie wiederherstellen möchten, und notieren Sie sich die ID.
4. Führen Sie die folgenden Schritte aus, um die Gruppe wiederherzustellen, wobei [ID] die Gruppen-ID ist.
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Gruppe erfolgreich wiederhergestellt wurde, wobei [ID] die Gruppen-ID ist.
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    Es kann bis zu 24 Stunden dauern, bis der Wiederherstellungsvorgang abgeschlossen ist, nach dem das Team und die Inhalte, die dem Team zugeordnet sind, einschließlich Tabstopps und Kanäle, in Teams angezeigt werden.
