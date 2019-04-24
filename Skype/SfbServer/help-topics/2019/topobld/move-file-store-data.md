---
title: Move-Dateispeicherdaten in einen neuen Dateispeicher in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wenn müssen Sie den Dateiserver entfernen, der derzeit fungiert als den Dateispeicher für Ihre Skype für Business Server-Bereitstellung ist oder wenn Sie andere vornehmen müssen Änderungen, die die aktuelle Datei vornehmen würden nicht verfügbar speichern, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:'
ms.openlocfilehash: 0f9552e9de66924524ef2ac5c66d125689061b88
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202317"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Move-Dateispeicherdaten in einen neuen Dateispeicher in Skype für Business Server

Wenn müssen Sie den Dateiserver entfernen, der derzeit fungiert als den Dateispeicher für Ihre Skype für Business Server-Bereitstellung ist oder wenn Sie andere vornehmen müssen Änderungen, die die aktuelle Datei vornehmen würden nicht verfügbar speichern, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:

1. Fahren Sie den Skype für Business Server-Dienste, die den Dateispeicher zu verwenden, den Sie entfernen möchten.

2. Definieren Sie des Dateispeichers im Topologie-Generator, und veröffentlichen Sie die Änderungen der neuen Dateispeicher für Ihre Bereitstellung zur Verfügung zu stellen.

3. Verschieben Sie die Dateien in den neuen Dateispeicher.

4. Starten Sie die Server bzw. Dienste neu.

5. Optional können Sie die alte Dateifreigabe und den Dateiordner entfernen.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher

1. Melden Sie sich an einem Computer als Mitglied der Gruppe RTCUniversersalServerAdmins oder CsServerAdministrator, auf dem die Skype für Business Server Administrative Tools installiert sind.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 

4. Wählen Sie für jede Director-Pool, Director, Standard Edition-Server und Front-End-Pool, den Dateispeicher verwendet, den Sie entfernen möchten den Server oder Pool, klicken Sie auf **Aktion**und klicken Sie dann auf **alle Dienste beenden**.

5. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

6. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.

7. Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:

8. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf **Eigenschaften bearbeiten **. 

9. Klicken Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** und unter **Dateispeicher** auf **Neu**.

10. Geben Sie in **Neuen Dateispeicher definieren** unter **Dateiserver-FQDN** den vollqualifizierten Domänennamen (FQDN) des Dateiservers ein. Geben Sie unter **Dateifreigabe** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.

     > [!IMPORTANT]
     > Dieser Schritt definiert einen neuen Dateispeicher für die Verwendung im Topologie-Generator. Die Definition erfolgt nur einmal, nicht für jeden Server. Bevor Sie die Topologie veröffentlichen, müssen Sie die definierte Dateifreigabe auf dem definierten Dateiserver erstellen. Einzelheiten finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:

12. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf **Eigenschaften bearbeiten **.

13. Wählen Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** in **Dateispeicher** die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.

14. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann die Skype für Business Server-Bereitstellungs-Assistenten aus, je nach Bedarf. Weitere Einzelheiten finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Starten Sie eine Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie cmd.exe.

16. Geben Sie an der Befehlszeile Folgendes ein:

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Der Switch „/S“ kopiert Dateien, Verzeichnisse und Unterverzeichnisse. Der Switch „/XF“ überspringt alle Dateien mit dem Namen „Meeting.Active“. Aktuelle Versionen von „robocopy.exe“ mit dem Switch „/MT“ erhöhen die Kopiergeschwindigkeit erheblich, da mehrere Threads verwendet werden. Verwenden Sie für die Option Befehlszeilenoption/log zusammen einen Directory Pfad und Protokolldateien Dateinamen in Form von C:\Logfiles\log.txt. Mit diesem Switch wird eine Protokolldatei der Vorgänge an dem benannten Speicherort erstellt.

17. Wenn das Kopieren der Daten in Lync Server-Systemsteuerung abgeschlossen ist, klicken Sie auf **Topologie**, und klicken Sie dann auf **Status**.

18. Wählen Sie für jeden Server oder Pool, für den Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion** und dann auf **Alle Dienste starten**.         

19. Entfernen Sie den alten Dateispeicher aus der Topologie und veröffentlichen Sie dann die Topologie. Einzelheiten finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Optional) Melden Sie sich bei dem Computer, der den soeben entfernten Dateispeicher enthält, als Mitglied der lokalen Administratorgruppe oder der Domänenadministratorgruppe an, und entfernen Sie dann die alte Dateifreigabe und das Verzeichnis.

## <a name="see-also"></a>Siehe auch

[Erneutes Zuweisen eines Servers auf einen anderen Dateispeicher](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Entfernen eines Dateispeichers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
