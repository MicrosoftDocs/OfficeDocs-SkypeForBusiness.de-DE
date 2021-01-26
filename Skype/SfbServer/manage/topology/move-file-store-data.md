---
title: Verschieben von Dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung agiert, oder wenn Sie andere Änderungen vornehmen müssen, die dazu führen, dass der aktuelle Dateispeicher nicht verfügbar ist, müssen Sie zunächst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:'
ms.openlocfilehash: 1ea1f6f038a5d589f9a2c3f480a5c9e589c324f3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816365"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Verschieben von Dateispeicherdaten in einen neuen Dateispeicher in Skype for Business Server

Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server-Bereitstellung agiert, oder wenn Sie andere Änderungen vornehmen müssen, die dazu führen, dass der aktuelle Dateispeicher nicht verfügbar ist, müssen Sie zunächst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:

1. Fahren Sie die Skype for Business Server-Dienste herunter, die den Dateispeicher verwenden, den Sie entfernen möchten.

2. Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, um den neuen Dateispeicher für Ihre Bereitstellung verfügbar zu machen.

3. Verschieben Sie die Daten in den neuen Dateispeicher.

4. Starten Sie die Server oder Dienste neu.

5. Entfernen Sie optional die alte Dateifreigabe und den alten Dateiordner.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher

1. Melden Sie sich bei einem Computer als Mitglied der Gruppe "RTCUniversersalServerAdmins" oder "CsServerAdministrator" an, auf dem die Skype for Business Server-Verwaltungstools installiert sind.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4. Wählen Sie für jeden Directorpool, Director, Standard Edition-Server und Front-End-Pool, der den dateispeicher verwendet, den Sie entfernen möchten, den Server oder Pool aus, klicken Sie auf "Aktion" **und** dann auf "Alle Dienste **beenden".**

5. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

6. Starten Sie den Topologie-Generator: Klicken Sie **auf "Start",**"Alle Programme",  **"Skype for Business Server"** und dann auf **"Skype for Business Server-Topologie-Generator".**

7. Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:

   a. Klicken Sie mit der rechten Maustaste auf den Server oder Pool, und klicken Sie dann **auf "Eigenschaften bearbeiten".**

   b. Klicken **Sie in "Eigenschaften bearbeiten"** unter **"Zuordnungen"** unter **"Dateispeicher"** auf **"Neu".**

   c. Geben Sie in "Neuen **Dateispeicher** definieren" unter **"Dateiserver-FQDN"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers ein. Geben **Sie unter "Dateifreigabe"** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **"OK".**

     > [!IMPORTANT]
     > In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert. Sie definieren es nur einmal, nicht für jeden Server. Vor dem Veröffentlichen der Topologie müssen Sie auf dem definierten Dateiserver die definierte Dateifreigabe erstellen. Ausführliche Informationen finden Sie unter [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

8. Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:

   a. Klicken Sie mit der rechten Maustaste auf den Server oder Pool, und klicken Sie dann auf **Eigenschaften bearbeiten.**

   b. Wählen **Sie in "Eigenschaften bearbeiten"** unter **"Zuordnungen"** im Dateispeicher die neue Dateifreigabe aus, und klicken Sie dann auf **"OK".** 

9. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann bei Bedarf den Skype for Business Server-Bereitstellungs-Assistenten aus. Ausführliche Informationen finden Sie unter [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

10. Starten Sie eine Eingabeaufforderung: Klicken **Sie auf "Start",** klicken **Sie** auf "Ausführen", und geben Sie cmd.exe.

11. Geben Sie an der Befehlszeile Folgendes ein:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Der Switch "/S" kopiert Dateien, Verzeichnisse und Unterverzeichnisse. Der Switch /XF überspringt alle Dateien mit dem Namen "Meeting.Active". In aktuellen Versionen von "robocopy.exe" mit dem /MT-Switch ist die Kopiergeschwindigkeit durch die Verwendung mehrerer Threads deutlich höher. Verwenden Sie für den Switch "/LOG" einen Verzeichnispfad und einen Protokolldateinamen in C:\Logfiles\log.txt. Diese Option erstellt eine Protokolldatei mit Vorgängen am benannten Speicherort.

12. Wenn die Datenkopie abgeschlossen ist, klicken Sie in der Lync Server-Systemsteuerung auf **"Topologie"** und dann auf **"Status".**

13. Wählen Sie für jeden Server oder Pool, auf dem Sie die Dienste beendet haben, den Server oder Pool aus, klicken Sie auf "Aktion" **und** dann auf **"Alle Dienste starten".**

14. Entfernen Sie den alten Datenspeicher aus der Topologie, und veröffentlichen Sie dann die Topologie. Ausführliche Informationen finden Sie unter [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

15. (Optional) Melden Sie sich als Mitglied der Gruppe der lokalen Administratoren oder der Gruppe "Domänen-Admins" am Computer an, der den eben von Ihnen entfernten Dateispeicher enthält, und entfernen Sie dann die alte Dateifreigabe sowie das Verzeichnis.

## <a name="see-also"></a>Siehe auch

[Erneutes Zuweisen eines Servers an einen anderen Dateispeicher](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Entfernen eines Dateispeichers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
