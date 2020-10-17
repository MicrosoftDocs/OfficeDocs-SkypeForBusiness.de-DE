---
title: 'Lync Server 2013: Einrichten SQL Server Protokollversands für die primäre Datenbank des beständigen Chat Servers'
description: 'Lync Server 2013: Einrichten SQL Server Protokollversands für die primäre Datenbank des Servers für beständigen Chat.'
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554261"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Einrichten SQL Server Protokollversands in lync Server 2013 für die primäre Datenbank des beständigen Chat Servers

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-12_

Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung zur sekundären Protokollversand-Datenbankinstanz des beständigen Chat Servers her, und vergewissern Sie sich, dass SQL Server-Agent aktiv ist.

Führen Sie die folgenden Schritte aus, um SQL Server Management Studio zu verwenden, das mit der primären Datenbankinstanz für beständigen Chat verbunden ist:

1.  Stellen Sie sicher, dass der SQL Server-Agent aktiv ist.

2.  Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, und klicken Sie auf **Eigenschaften**.

3.  Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.

4.  Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.

5.  Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.

6.  Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.

7.  Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner in das Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie einen lokalen Pfad zum Ordner ein (Beispiel: c: \\ Sicherung)** . (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn das SQL Server Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.

    
    </div>

8.  Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.

9.  Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan**, und passen Sie den Zeitplan für den SQL Server-Agent nach Bedarf an.

10. Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus, und klicken Sie dann auf **OK**.

11. Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.

12. Klicken Sie auf **verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.

13. Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.

14. Wählen Sie auf der Registerkarte **sekundäre Datenbank initialisieren** die Option **Ja, generieren Sie eine vollständige Sicherung der primären Datenbank, und stellen Sie Sie in der sekundären Datenbank wieder her (und erstellen Sie die sekundäre Datenbank, falls Sie nicht vorhanden ist)**.

15. Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.

16. Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan**, und passen Sie den Zeitplan für den SQL Server-Agent nach Bedarf an. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

17. Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.

18. Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.

19. Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.

20. Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an. Klicken Sie zum Anpassen des Zeitplans für Ihre Installation auf **Zeitplan**, passen Sie den Zeitplan für SQL Server-Agent nach Bedarf an, und klicken Sie auf **OK**. Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.

21. Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.

</div>

<span> </span>

</div>

</div>

</div>

