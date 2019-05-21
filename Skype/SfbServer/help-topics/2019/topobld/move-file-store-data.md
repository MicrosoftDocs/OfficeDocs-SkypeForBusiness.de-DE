---
title: Verschieben von dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht mehr verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:'
ms.openlocfilehash: e065ab7a14f76df33ddfa0ade26561c486edb050
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288690"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Verschieben von dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server

Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht mehr verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Dann müssen Sie folgende Schritte ausführen:

1. Beenden Sie die Skype for Business Server-Dienste, die den Dateispeicher verwenden, den Sie entfernen möchten.

2. Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, damit der neue Dateispeicher für Ihre Bereitstellung zur Verfügung steht.

3. Verschieben Sie die Dateien in den neuen Dateispeicher.

4. Starten Sie die Server bzw. Dienste neu.

5. Optional können Sie die alte Dateifreigabe und den Dateiordner entfernen.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher

1. Melden Sie sich bei einem Computer als Mitglied der RTCUniversersalServerAdmins-oder CsServerAdministrator-Gruppe an, in der der Skype for Business-Server, Verwaltungs Tools installiert sind.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Topologie ** und dann auf **Status**. 

4. Wählen Sie für jeden Director-Pool, Director, Standard Edition-Server und Front-End-Pool, der den zu entfernenden Dateispeicher verwendet, den Server oder Pool aus, klicken Sie auf **Aktion**, und klicken Sie dann auf **alle Dienste beenden**.

5. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

6. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topology Builder**.

7. Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:

8. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf **Eigenschaften bearbeiten **. 

9. Klicken Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** und unter **Dateispeicher** auf **Neu**.

10. Geben Sie in **Neuen Dateispeicher definieren** unter **Dateiserver-FQDN** den vollqualifizierten Domänennamen (FQDN) des Dateiservers ein. Geben Sie unter **Dateifreigabe** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.

     > [!IMPORTANT]
     > In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert. Die Definition erfolgt nur einmal, nicht für jeden Server. Bevor Sie die Topologie veröffentlichen, müssen Sie die definierte Dateifreigabe auf dem definierten Dateiserver erstellen. Einzelheiten finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:

12. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie auf **Eigenschaften bearbeiten **.

13. Wählen Sie in **Eigenschaften bearbeiten** unter **Zuordnungen** in **Dateispeicher** die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.

14. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Bereitstellungs-Assistenten von Skype for Business Server nach Bedarf aus. Weitere Einzelheiten finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Starten Sie eine Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann cmd. exe ein.

16. Geben Sie an der Befehlszeile Folgendes ein:

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Der Switch „/S“ kopiert Dateien, Verzeichnisse und Unterverzeichnisse. Der Switch „/XF“ überspringt alle Dateien mit dem Namen „Meeting.Active“. Aktuelle Versionen von „robocopy.exe“ mit dem Switch „/MT“ erhöhen die Kopiergeschwindigkeit erheblich, da mehrere Threads verwendet werden. Verwenden Sie für den/Log-Schalter einen Verzeichnispfad und einen Protokolldateinamen in Form von C:\Logfiles\log.txt. Mit diesem Switch wird eine Protokolldatei der Vorgänge an dem benannten Speicherort erstellt.

17. Klicken Sie nach Abschluss der Datenkopie in der lync Server-Systemsteuerung auf **Topologie**, und klicken Sie dann auf **Status**.

18. Wählen Sie für jeden Server oder Pool, für den Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion** und dann auf **Alle Dienste starten**.         

19. Entfernen Sie den alten Dateispeicher aus der Topologie und veröffentlichen Sie dann die Topologie. Einzelheiten finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Optional) Melden Sie sich bei dem Computer, der den soeben entfernten Dateispeicher enthält, als Mitglied der lokalen Administratorgruppe oder der Domänenadministratorgruppe an, und entfernen Sie dann die alte Dateifreigabe und das Verzeichnis.

## <a name="see-also"></a>Siehe auch

[Erneutes Zuweisen eines Servers zu einem anderen Dateispeicher](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Entfernen eines Dateispeichers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
