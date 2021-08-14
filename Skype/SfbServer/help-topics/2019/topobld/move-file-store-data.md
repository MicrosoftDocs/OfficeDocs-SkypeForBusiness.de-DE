---
title: Verschieben von Datei Store daten in eine neue Store in Skype for Business Server
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
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen würden, müssen Sie zuerst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:'
ms.openlocfilehash: 4e9a28fa1793e642fbf3407c6a6306a979fa287844a9862a55780f1bd1169f82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342480"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Verschieben von Datei Store daten in eine neue Store in Skype for Business Server

Wenn Sie den Dateiserver entfernen müssen, der derzeit als Dateispeicher für Ihre Skype for Business Server Bereitstellung fungiert, oder wenn Sie andere Änderungen vornehmen müssen, die den aktuellen Dateispeicher nicht verfügbar machen würden, müssen Sie zuerst eine neue Freigabe erstellen. Anschließend müssen Sie die folgenden Schritte ausführen:

1. Fahren Sie die Skype for Business Server Dienste herunter, die den zu entfernenden Dateispeicher verwenden.

2. Definieren Sie den Dateispeicher im Topologie-Generator, und veröffentlichen Sie die Änderungen, um den neuen Dateispeicher für Ihre Bereitstellung verfügbar zu machen.

3. Verschieben Sie die Daten in den neuen Dateispeicher.

4. Starten Sie die Server oder Dienste neu.

5. Entfernen Sie optional die alte Dateifreigabe und den Dateiordner.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>So verschieben Sie Dateispeicherdaten von einem Dateispeicher in einen neuen Dateispeicher

1. Melden Sie sich bei einem Computer als Mitglied der Gruppe "RTCUniversersalServerAdmins" oder "CsServerAdministrator" an, auf dem die Skype for Business Server, Die Verwaltungstools installiert sind.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4. Wählen Sie für jeden Directorpool, Director, Standard Edition Server und Front-End-Pool, der den zu entfernenden Dateispeicher verwendet, den Server oder Pool aus, klicken Sie auf **Aktion** und dann auf **"Alle Dienste beenden".**

5. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

6. Topologie-Generator starten: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server** und dann auf **Skype for Business Server Topologie-Generator.**

7. Wählen Sie einen Server oder Pool aus, der den Dateispeicher verwendet, und gehen Sie wie folgt vor:

8. Klicken Sie mit der rechten Maustaste auf den Server oder Pool, und klicken Sie dann auf **"Eigenschaften bearbeiten".**

9. Klicken Sie unter **"Eigenschaften bearbeiten"** unter **"Zuordnungen"** unter **"Dateispeicher"** auf **"Neu".**

10. Geben Sie unter **"Neuen Datei Store definieren"** unter **"Dateiserver-FQDN"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Dateiservers ein. Geben Sie unter **"Dateifreigabe"** den Ordnernamen für die neue Dateifreigabe ein, und klicken Sie dann auf **"OK".**

     > [!IMPORTANT]
     > In diesem Schritt wird ein neuer Dateispeicher für die Verwendung im Topologie-Generator definiert. Sie definieren sie nur einmal, nicht für jeden Server. Vor dem Veröffentlichen der Topologie müssen Sie auf dem definierten Dateiserver die definierte Dateifreigabe erstellen. Ausführliche Informationen finden Sie unter [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).

11. Gehen Sie für jeden Server oder Pool, der den Dateispeicher verwendet, wie folgt vor:

12. Klicken Sie mit der rechten Maustaste auf den Server oder Pool, und klicken Sie dann auf **"Eigenschaften bearbeiten".**

13. Wählen Sie in **"Eigenschaften bearbeiten"** unter **"Zuordnungen"** im **Dateispeicher** die neue Dateifreigabe aus, und klicken Sie dann auf **"OK".**

14. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Skype for Business Server Bereitstellungs-Assistenten nach Bedarf aus. Ausführliche Informationen finden Sie unter [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).

15. Starten Sie eine Eingabeaufforderung: Klicken Sie auf **"Start",** klicken Sie auf **"Ausführen",** und geben Sie dann cmd.exe ein.

16. Geben Sie an der Befehlszeile Folgendes ein:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Der Schalter "/S" kopiert Dateien, Verzeichnisse und Unterverzeichnisse. Die Option /XF überspringt alle Dateien mit dem Namen "Meeting.Active". In aktuellen Versionen von "robocopy.exe" mit dem /MT-Switch ist die Kopiergeschwindigkeit durch die Verwendung mehrerer Threads deutlich höher. Verwenden Sie für die Option /LOG einen Verzeichnispfad und einen Protokolldateinamen in Form von C:\Logfiles\log.txt. Dieser Switch erstellt eine Protokolldatei von Vorgängen am benannten Speicherort.

17. Klicken Sie nach Abschluss der Datenkopie in der Lync Server-Systemsteuerung auf **"Topologie"** und dann auf **"Status".**

18. Wählen Sie für jeden Server oder Pool, auf dem Dienste beendet wurden, den Server oder Pool aus, klicken Sie auf **"Aktion"** und dann auf **"Alle Dienste starten".**

19. Entfernen Sie den alten Datenspeicher aus der Topologie, und veröffentlichen Sie dann die Topologie. Ausführliche Informationen finden Sie unter [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).

20. (Optional) Melden Sie sich als Mitglied der Gruppe der lokalen Administratoren oder der Gruppe "Domänen-Admins" am Computer an, der den eben von Ihnen entfernten Dateispeicher enthält, und entfernen Sie dann die alte Dateifreigabe sowie das Verzeichnis.

## <a name="see-also"></a>Siehe auch

[Erneutes Zuweisen eines Servers an einen anderen Dateispeicher](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[Entfernen eines Dateispeichers](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))