---
title: 'Lync Server 2013: Konfigurieren eines Watcher-Knotens zur Verwendung der Anmeldeinformationen-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e05ac48896b50b4b83e4211a5036f6a6d513d43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517689"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Konfigurieren eines Watcher-Knotens für die Verwendung der Anmeldeinformationen-Authentifizierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Wenn Ihr Monitorknotencomputer außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie ein etwas anderes Verfahren anwenden, um diesen Monitorknoten für die Ausführung synthetischer Transaktionen zu konfigurieren. Beachten Sie, dass Sie keinen Pool mit vertrauenswürdigen Anwendungen und keine vertrauenswürdige Anwendung erstellen sollten und ein Zertifikat installieren müssen, über das der Monitorknoten Benachrichtigungen an einen Computer im Umkreisnetzwerk senden kann. Dies bedeutet, dass Sie zwei separate Schritte ausführen müssen:

  - Aktualisieren der Mitgliedschaft für die Gruppe "RTC Local Read-only Administrators Group" des Computers

  - Installieren der Konfigurationsdateien des Monitorknotens

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-only Administrators"

Wenn der Monitorknoten außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie das Netzwerkdienstkonto auf dem Computer mit dem Monitorknoten der Gruppe "RTC Local Read-only Administrators" hinzufügen. Führen Sie dazu für den Monitorknoten die folgenden Schritte aus:

1.  Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Verwalten**.

2.  Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Doppelklicken Sie im Bereich "Gruppen" mit der rechten Maustaste auf **RTC Local Read-only Administrators**.

4.  Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **Hinzufügen**.

5.  Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen**** auf **Standorte**.

6.  Wählen Sie im Dialogfeld **Standorte** den Namen des Monitorknotencomputers aus, und klicken Sie dann auf **OK**.

7.  Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** den Text **Netzwerkdienst** ein, und klicken Sie auf **OK**.

8.  Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **OK**, und schließen Sie den **Server-Manager**.

Starten Sie den Monitorknotencomputer neu.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Installieren der Konfigurationsdateien des Monitorknotens

Nachdem der Monitorknotencomputer neu gestartet wurde, ist der nächste Schritt das Ausführen der Datei "Watchernode.msi". Um diese Datei auszuführen, öffnen Sie die lync Server 2013 Verwaltungsshell, indem Sie auf **Start**und **Alle Programme**klicken, auf **lync Server 2013**und dann auf **lync Server-Verwaltungsshell**klicken. Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (stellen Sie sicher, dass Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Wie bereits erwähnt, kann die Datei "Watchernode.msi" auch über ein Befehlsfenster mit Eingabeaufforderung ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>. Geben Sie den bereits gezeigten Befehl ein, nachdem das Befehlsfenster geöffnet wurde.



</div>

Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann. In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

