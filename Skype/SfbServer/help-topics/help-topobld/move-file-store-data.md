---
title: Dateispeicher Daten in einen neuen Dateispeicher in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Wenn Sie den Dateiserver entfernen möchten, der derzeit als Dateispeicher für Ihre Skype for Business Server 2015-Bereitstellung fungiert, oder wenn Sie weitere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215586"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Dateispeicher Daten in einen neuen Dateispeicher in Skype for Business Server 2015

Wenn Sie den Dateiserver entfernen möchten, der derzeit als Dateispeicher für Ihre Skype for Business Server 2015-Bereitstellung fungiert, oder wenn Sie weitere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen, müssen Sie zuerst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:

1. Beenden Sie die Skype for Business Server 2015 Dienste, die den Dateispeicher verwenden, den Sie entfernen möchten.

2. Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, um den neuen Dateispeicher für Ihre Bereitstellung zur Verfügung zu stellen.

3. Verschiebt die Daten in den neuen Dateispeicher.

4. Starten Sie die Server oder Dienste neu.

5. Entfernen Sie optional den alten Dateifreigabe-und Datei Ordner.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher

1. Melden Sie sich an einem Computer als Mitglied der RTCUniversersalServerAdmins-oder CsServerAdministrator-Gruppe an, in der die Skype for Business Server 2015, Verwaltungs Tools installiert sind.

2. Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4. Wählen Sie für jeden Directorpool, Director, Standard Edition-Server und Front-End-Pool, der den zu entfernenden Dateispeicher verwendet, den Server oder den Pool aus, klicken Sie auf **Aktion**, und klicken Sie dann auf **alle Dienste beenden**.

5. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

6. Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology-Generator**.

7. Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und führen Sie die folgenden Schritte aus:

8. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

9. Klicken Sie in **Eigenschaften bearbeiten**unter **Zuordnungen**unter **Dateispeicher**auf **neu**.

10. Geben Sie in **neue Dateispeicher definieren**unter **Dateiserver-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers ein. Geben Sie unter **Dateifreigabe**den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **OK**.

     > [!IMPORTANT]
     > In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert. Sie definieren Sie nur einmal, nicht für jeden Server. Vor dem Veröffentlichen der Topologie müssen Sie auf dem definierten Dateiserver die definierte Dateifreigabe erstellen. Ausführliche Informationen finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Führen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, folgende Schritte aus:

12. Klicken Sie mit der rechten Maustaste auf den Server oder den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

13. Wählen Sie in **Eigenschaften bearbeiten**unter **Zuordnungen**im **Dateispeicher**die neue Dateifreigabe aus, und klicken Sie dann auf **OK**.

14. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die Skype for Business Server-Bereitstellung bei Bedarf aus. Ausführliche Informationen finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Starten einer Eingabeaufforderung: Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann cmd.exe ein.

16. Geben Sie an der Befehlszeile Folgendes ein:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Der Schalter/s kopiert Dateien, Verzeichnisse und Unterverzeichnisse. Der/XF-Schalter überspringt alle Dateien mit dem Namen "Meeting. Active". In aktuellen Versionen von "robocopy.exe" mit dem /MT-Switch ist die Kopiergeschwindigkeit durch die Verwendung mehrerer Threads deutlich höher. Verwenden Sie für den Parameter/Log-Switch einen Verzeichnispfad und einen Namen der Protokolldatei in Form von C:\Logfiles\log.txt. Mit dieser Option wird eine Protokolldatei mit Vorgängen am benannten Speicherort erstellt.

17. Klicken Sie nach Abschluss der Datenkopie in lync Server-Systemsteuerung auf **Topologie**, und klicken Sie dann auf **Status**.

18. Wählen Sie für jeden Server oder Pool, in dem Sie Dienste beendet haben, den Server oder Pool aus, klicken Sie auf **Aktion**und dann auf **alle Dienste starten**.

19. Entfernen Sie den alten Datenspeicher aus der Topologie, und veröffentlichen Sie dann die Topologie. Ausführliche Informationen finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Optional) Melden Sie sich als Mitglied der Gruppe der lokalen Administratoren oder der Gruppe "Domänen-Admins" am Computer an, der den eben von Ihnen entfernten Dateispeicher enthält, und entfernen Sie dann die alte Dateifreigabe sowie das Verzeichnis.

## <a name="see-also"></a>Siehe auch

[Erneutes Zuweisen eines Servers an einen anderen Dateispeicher](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Entfernen eines Dateispeichers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
