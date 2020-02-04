---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-12_

Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand-Datenbankinstanz des beständigen Chat Servers her, und stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.

Führen Sie die folgenden Schritte aus, indem Sie SQL Server Management Studio verwenden, das mit der primären Datenbankinstanz für beständigen Chat verbunden ist:

1.  Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.

2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.

3.  Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.

4.  Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.

5.  Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.

6.  Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.

7.  Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie einen lokalen Pfad zu dem Ordner ein (Beispiel: c\\: Sicherung)** . (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.

    
    </div>

8.  Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.

9.  Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.

10. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.

11. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.

12. Klicken Sie auf **verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.

13. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.

14. Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.

15. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.

16. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

17. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.

18. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.

19. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.

20. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an, und klicken Sie auf **OK**. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

21. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.

</div>

<span> </span>

</div>

</div>

</div>

