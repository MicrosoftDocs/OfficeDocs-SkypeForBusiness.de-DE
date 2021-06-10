---
title: Archivieren oder Löschen eines Teams in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: In diesem Artikel erfahren Sie, wie Sie ein Team in einem Ordner archivieren Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97cce8577c2d3c23e097f5e3bf5d819d51a16b10
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856364"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivieren oder Löschen eines Teams in Microsoft Teams

Im Laufe der Zeit wird ein in Microsoft Teams erstelltes Team möglicherweise nicht mehr verwendet, oder Sie möchten ein Team am Ende eines Projekts archivieren oder löschen. Als Administrator von Microsoft Teams führen Sie die in diesem Artikel beschriebenen Schritte aus, um ein Team, das nicht mehr benötigt wird, zu archivieren oder zu löschen.

Wenn Sie ein Team archivieren, werden alle Aktivitäten für dieses Team eingestellt. Durch Archivierung eines Teams werden auch die privaten Kanäle im Team und die zugehörigen Websitesammlungen archiviert.  Sie können aber weiterhin Mitglieder hinzufügen oder entfernen und Rollen aktualisieren, und Sie können weiterhin alle Teamaktivitäten in standardmäßigen und privaten Kanälen, Dateien und Chats anzeigen.

Wenn Sie ein Team löschen, werden auch Teamaktivitäten in standardmäßigen und privaten Kanälen (einschließlich zugeordneter Websitesammlungen), Dateien und Chats gelöscht.

> [!IMPORTANT]
> Archivierte Teams können reaktiviert werden, aber Sie können ein gelöschtes Team nicht unmittelbar wiederherstellen. Erwägen Sie zuerst die Archivierung des Teams, und verschieben Sie den Löschvorgang, bis Sie sicher sind, dass Sie das Team nicht mehr benötigen.

## <a name="archive-a-team"></a>Archivieren eines Teams

Gehen folgendermaßen Sie vor, um ein Team zu archivieren. Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Wählen Sie im Admin **Center** Teams aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **Archivieren** aus. Die folgende Warnmeldung wird angezeigt.

    ![Screenshot der Teams-Archivierungsmeldung](media/teams-archive-message.png)

4. Um zu verhindern, dass Personen den Inhalt der SharePoint-Website und der Wiki-Registerkarte bearbeiten, die dem Team zugeordnet ist, wählen Sie Die **SharePoint-Website** für Teammitglieder schreibgeschützt machen aus. (Teams können diese Inhalte weiterhin bearbeiten.)
5. Wählen Sie **Archivieren** aus, um das Team zu archivieren. Der Status des Teams wird in **Archiviert** geändert.

## <a name="make-an-archived-team-active"></a>Aktivieren eines archivierten Teams

Führen Sie die folgenden Schritte aus, um ein archiviertes Team wieder zu aktivieren.

1. Wählen Sie im Admin **Center** Teams aus.
2. Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3. Wählen Sie **Archivierung aufheben** aus. Der Status des Teams wird in **Aktiv** geändert.

## <a name="delete-a-team"></a>Löschen eines Teams

Wenn das Team in Zukunft nicht mehr benötigt wird, dann können Sie es löschen, anstatt es zu archivieren. Führen Sie folgende Schritte aus, um ein Team zu löschen.

1.  Wählen Sie im Admin **Center** Teams aus.
2.  Wählen Sie ein Team aus, indem Sie auf den Teamnamen klicken.
3.  Wählen Sie **Löschen** aus. Eine Bestätigungsmeldung wird angezeigt.
4.  Wählen Sie **Löschen** aus, um das Team endgültig zu löschen.

## <a name="restore-a-deleted-team"></a>Wiederherstellen eines gelöschten Teams

Gehen Sie wie folgt vor, um ein gelöschtes Team wiederherzustellen, indem Sie Microsoft 365 Gruppe wiederherstellen, die dem Team zugeordnet ist. Durch das Wiederherstellen Microsoft 365 Gruppe für ein Team werden Teaminhalte wiederhergestellt, einschließlich Registerkarten, Standardkanälen, privaten Kanälen und zugehörigen Websitesammlungen.

Standardmäßig wird eine gelöschte Microsoft 365 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe wiederherstellen können. Weitere Informationen finden Sie unter [Wiederherstellen einer gelöschten Gruppe.](/microsoft-365/admin/create-groups/restore-deleted-group)

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

### <a name="restore-the-deleted-microsoft-365-group"></a>Wiederherstellen der gelöschten Microsoft 365 Gruppe

1. Stellen Sie eine Verbindung mit Azure AD her, indem Sie Folgendes ausführen:
    ```PowerShell
    Connect-AzureAD
    ```
    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Administratorkonto und -kennwort an.  
2. Führen Sie die folgenden Schritte aus, um eine Liste aller Microsoft 365, die noch innerhalb des Aufbewahrungszeitraums von 30 Tagen liegen, angezeigt. Verwenden Sie den Parameter **-All $True**, wenn Sie über viele Gruppen verfügen.
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