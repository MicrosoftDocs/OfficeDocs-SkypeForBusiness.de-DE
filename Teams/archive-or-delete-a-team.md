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
description: Hier erhalten Sie Informationen zum Archivieren oder endgültigen Löschen eines Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e065ddccd9781143b9c3522aa795f85ef0e118bb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780714"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivieren oder Löschen eines Teams in Microsoft Teams
===========================================

Im Laufe der Zeit wird ein in Microsoft Teams erstelltes Team möglicherweise nicht mehr verwendet, oder Sie möchten ein Team am Ende eines Projekts archivieren oder löschen. Als Administrator von Microsoft Teams führen Sie die in diesem Artikel beschriebenen Schritte aus, um ein Team, das nicht mehr benötigt wird, zu archivieren oder zu löschen.

Wenn Sie ein Team archivieren, werden alle Aktivitäten für dieses Team eingestellt. Durch Archivierung eines Teams werden auch die privaten Kanäle im Team und die zugehörigen Websitesammlungen archiviert.  Sie können aber weiterhin Mitglieder hinzufügen oder entfernen und Rollen aktualisieren, und Sie können weiterhin alle Teamaktivitäten in standardmäßigen und privaten Kanälen, Dateien und Chats anzeigen.

Wenn Sie ein Team löschen, werden auch Teamaktivitäten in standardmäßigen und privaten Kanälen (einschließlich zugeordneter Websitesammlungen), Dateien und Chats gelöscht.

> [!IMPORTANT]
> Archivierte Teams können reaktiviert werden, aber Sie können ein gelöschtes Team nicht unmittelbar wiederherstellen. Erwägen Sie zuerst die Archivierung des Teams, und verschieben Sie den Löschvorgang, bis Sie sicher sind, dass Sie das Team nicht mehr benötigen.

## <a name="archive-a-team"></a>Archivieren eines Teams

Gehen folgendermaßen Sie vor, um ein Team zu archivieren.

1. Wählen Sie im Microsoft Teams Admin Center die Option **Teams** aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **Archivieren** aus. Die folgende Warnmeldung wird angezeigt.

    ![Screenshot der Teams-Archivierungsmeldung](media/teams-archive-message.png)

4. Wenn die SharePoint-Website für das Team schreibgeschützt sein soll, aktivieren Sie das Kontrollkästchen.
5. Wählen Sie **Archivieren** aus, um das Team zu archivieren. Der Status des Teams wird in **Archiviert** geändert.

## <a name="make-an-archived-team-active"></a>Aktivieren eines archivierten Teams

Führen Sie die folgenden Schritte aus, um ein archiviertes Team wieder zu aktivieren.

1. Wählen Sie im Microsoft Teams Admin Center die Option **Teams** aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **Archivierung aufheben** aus. Der Status des Teams wird in **Aktiv** geändert.

## <a name="delete-a-team"></a>Löschen eines Teams

Wenn das Team in Zukunft nicht mehr benötigt wird, dann können Sie es löschen, anstatt es zu archivieren. Führen Sie folgende Schritte aus, um ein Team zu löschen.

1.  Wählen Sie im Microsoft Teams Admin Center die Option **Teams** aus.
2.  Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3.  Wählen Sie **Löschen** aus. Eine Bestätigungsmeldung wird angezeigt.
4.  Wählen Sie **Löschen** aus, um das Team endgültig zu löschen.

## <a name="restore-a-deleted-team"></a>Wiederherstellen eines gelöschten Teams

Befolgen Sie diese Schritte, um ein gelöschtes Team wiederherzustellen, indem Sie die mit dem Team verknüpfte Office 365-Gruppe wiederherstellen. Durch Wiederherstellung der Office 365-Gruppe für ein Team wird der Inhalt des Teams wieder hergestellt, einschließlich der Registerkarten, Standardkanäle und privaten Kanäle sowie der damit verbundenen Websitesammlungen.

Standardmäßig wird eine gelöschte Office 365-Gruppe 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe wiederherstellen können. Weitere Informationen finden Sie unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installieren des AzureADPreview-Moduls

1. Öffnen Sie Windows PowerShell als Administrator.
2. Wenn Sie eine frühere Version des AzureADPreview-Moduls oder des AzureAD-Moduls installiert haben, deinstallieren Sie diese, indem Sie eine der folgenden Aktionen ausführen:

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
    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Administratorkonto und -kennwort an.  
2. Führen Sie die folgenden Schritte aus, um eine Liste aller Soft-Deleted Microsoft 365-Gruppen anzuzeigen, die sich noch im 30-tägigen Aufbewahrungszeitraum befinden. Verwenden Sie den Parameter **-All $True**, wenn Sie über viele Gruppen verfügen.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Suchen Sie die Gruppe, die Sie wiederherstellen möchten, und notieren Sie sich die ID.
4. Führen Sie die folgenden Schritte aus, um die Gruppe wiederherzustellen, wobei [Id] die Gruppen-ID ist.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Gruppe erfolgreich wiederhergestellt wurde, wobei [Id] die Gruppen-ID ist.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Es kann bis zu 24 Stunden dauern, bis der Wiederherstellungsvorgang abgeschlossen ist. danach werden das Team und die dem Team zugeordneten Inhalte, einschließlich der Registerkarten und Kanäle, in Teams angezeigt.
