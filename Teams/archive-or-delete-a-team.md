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
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e367fe85f1af35391fa00b4a416b6e796383d962
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826403"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivieren oder Löschen eines Teams in Microsoft Teams
===========================================

Im Laufe der Zeit kann ein Team, das in Microsoft Teams erstellt wurde, möglicherweise nicht mehr verwendet werden, oder Sie möchten ein Team am Ende eines Projekts archivieren oder löschen. Wenn Sie ein Microsoft Teams-Administrator sind, führen Sie die in diesem Artikel aufgeführten Schritte aus, um ein nicht mehr benötigtes Team zu archivieren oder zu löschen.

Wenn Sie ein Team archivieren, werden alle Aktivitäten für dieses Team eingestellt. Durch die Archivierung eines Teams werden auch private Kanäle im Team und die zugehörigen Websitesammlungen archiviert.  Sie können jedoch weiterhin Mitglieder hinzufügen oder entfernen sowie Rollen aktualisieren, und Sie können weiterhin alle Teamaktivitäten in Standard-und privaten Kanälen, Dateien und Chats anzeigen.

Wenn Sie ein Team löschen, werden auch die Teamaktivitäten in Standard-und privaten Kanälen (und zugehörigen Websitesammlungen), Dateien und Chats gelöscht.

> [!IMPORTANT]
> Archivierte Teams können erneut aktiviert werden, aber Sie können ein gelöschtes Team nicht direkt wiederherstellen. In diesem Fall sollten Sie das Team zunächst archivieren und den Löschvorgang verschieben, bis Sie sicher sind, dass Sie das Team nicht mehr benötigen.

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

Führen Sie die folgenden Schritte aus, um ein gelöschtes Team wiederherzustellen, indem Sie die Office 365-Gruppe wiederherstellen, die dem Team zugeordnet ist. Beim Wiederherstellen der Office 365-Gruppe für ein Team werden Team Inhalte, einschließlich Tabstopps, Standardkanälen und privaten Kanälen sowie deren zugehörigen Websitesammlungen, wiederhergestellt.

Standardmäßig wird eine gelöschte Office 365-Gruppe 30 Tage lang aufbewahrt. Dieser Zeitraum von 30 Tagen wird als "Soft-Delete" bezeichnet, da Sie die Gruppe wiederherstellen können. Weitere Informationen finden Sie unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installieren des AzureADPreview-Moduls

1. Öffnen Sie Windows PowerShell als Administrator.
2. Wenn Sie eine frühere Version des AzureADPreview-Moduls installiert oder das AzureAD-Modul installiert haben, deinstallieren Sie es, indem Sie eine der folgenden Aktionen ausführen:

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. Installieren Sie die neueste Version des AzureADPreview-Moduls, indem Sie Folgendes ausführen:

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>Wiederherstellen der gelöschten Office 365-Gruppe

1. Stellen Sie eine Verbindung mit Azure AD her, indem Sie Folgendes ausführen:
    ```PowerShell
    Connect-AzureAD
    ```
    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Administratorkonto und Kennwort an.  
2. Führen Sie die folgenden Schritte aus, um eine Liste aller Soft-Deleted Office 365-Gruppen anzuzeigen, die sich noch innerhalb des Aufbewahrungszeitraums von 30 Tagen befinden. Verwenden Sie den Parameter **-all $true** , wenn viele Gruppen vorhanden sind.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Suchen Sie die Gruppe, die Sie wiederherstellen möchten, und notieren Sie sich die ID.
4. Führen Sie die folgenden Schritte aus, um die Gruppe wiederherzustellen, wobei [ID] die Gruppen-ID ist.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Gruppe erfolgreich wiederhergestellt wurde, wobei [ID] die Gruppen-ID ist.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Es kann bis zu 24 Stunden dauern, bis der Wiederherstellungsvorgang abgeschlossen ist, nach dem das Team und die Inhalte, die dem Team zugeordnet sind, einschließlich Tabstopps und Kanäle, in Teams angezeigt werden.
