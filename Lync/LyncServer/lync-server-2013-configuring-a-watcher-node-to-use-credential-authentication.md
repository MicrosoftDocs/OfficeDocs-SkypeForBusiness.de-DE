---
title: 'Lync Server 2013: Konfigurieren eines Watcher-Knotens zur Verwendung der Authentifizierung von Anmeldeinformationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3746042e0fbf6c7342dd19085f563440b26bb0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Konfigurieren eines Watcher-Knotens zur Verwendung der Authentifizierung von Anmeldeinformationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Wenn sich Ihr Watcher-Knoten Computer außerhalb des Umkreisnetzwerks befindet, müssen Sie ein etwas anderes Verfahren ausführen, um diesen Watcher-Knoten so zu konfigurieren, dass synthetische Transaktionen ausgeführt werden. Insbesondere sollten Sie keinen vertrauenswürdigen Anwendungspool und eine vertrauenswürdige Anwendung erstellen, und Sie müssen ein Zertifikat installieren, mit dem der Watcher-Knoten Benachrichtigungen an einen Computer im Umkreisnetzwerk senden kann. Das bedeutet, dass Sie zwei getrennte Aufgaben ausführen müssen:

  - Aktualisieren der Mitgliedschaft in der RTC Local-Gruppe "nur-Lese-Administratoren" des Computers

  - Installieren der Watcher-Knoten-Konfigurationsdateien

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der lokalen RTC-Administratorgruppe "schreibgeschützt"

Wenn sich der Watcher-Knoten außerhalb des Umkreisnetzwerks befindet, müssen Sie das Netzwerkdienstkonto der Gruppe "RTC Local Read-only" auf dem Watcher-Knoten Computer hinzufügen. Führen Sie dazu das folgende Verfahren auf dem Watcher-Knoten aus:

1.  Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie dann auf **Verwalten**.

2.  Erweitern Sie im Server-Manager **Konfiguration**, erweitern Sie **lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Doppelklicken Sie im Bereich Gruppen auf **RTC Local Read-Only-Administratoren**.

4.  Klicken Sie im Dialogfeld **Eigenschaften von RTC Local nur-Lese-Administratoren** auf **Hinzufügen**.

5.  Klicken Sie im Dialogfeld **Benutzer, Computer, Dienstkonten oder Gruppen auswählen** auf **Speicherorte**.

6.  Wählen Sie im Dialogfeld **Speicherorte** den Namen des Watcher-Knoten Computers aus, und klicken Sie dann auf **OK**.

7.  Geben Sie im Feld Geben Sie die **zu wählenden Objektnamen ein den Namen** **Netzwerkdienst**ein, und klicken Sie dann auf **OK**.

8.  Klicken Sie im Dialogfeld **Eigenschaften von RTC-schreibgeschützten Administratoren** auf **OK**, und schließen Sie dann **Server-Manager**.

Starten Sie den Monitorknotencomputer neu.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installieren der Watcher-Knoten-Konfigurationsdateien

Nachdem der Watcher-Knoten Computer neu gestartet wurde, besteht der nächste Schritt darin, die Datei Watchernode. msi auszuführen. Um diese Datei auszuführen, öffnen Sie die lync Server 2013-Verwaltungsshell, indem Sie auf **Start**klicken, auf **Alle Programme**klicken, auf **lync Server 2013**und dann auf **lync Server-Verwaltungsshell**klicken. Geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (stellen Sie sicher, dass Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode. msi angeben):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Wie bereits erwähnt, kann Watchernode. msi auch über ein Befehlsfenster ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG> und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>. Wenn das Befehlsfenster geöffnet wird, geben Sie den gleichen Befehl wie zuvor gezeigt ein.



</div>

Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

