---
title: Konfigurieren eines Watcher-Knotens zur Verwendung der vertrauenswürdigen Server Authentifizierung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Konfigurieren eines Watcher-Knotens in lync Server 2013 zur Verwendung der vertrauenswürdigen Server Authentifizierung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Wenn sich Ihr Watcher-Knoten Computer im Umkreisnetzwerk befindet, kann mithilfe der vertrauenswürdigen Server Authentifizierung die Verwaltungs Steuern erheblich reduziert werden, um ein einzelnes Zertifikat statt zahlreicher Benutzerkonten Kennwörter zu verwalten.

Der erste Schritt bei der Konfiguration der vertrauenswürdigen Server Authentifizierung ist das Erstellen eines vertrauenswürdigen Anwendungspools zum Hosten des Watcher-Knoten Computers. Nachdem der vertrauenswürdige Anwendungspool erstellt wurde, müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten so konfigurieren, dass Sie als vertrauenswürdige Anwendung ausgeführt werden.

<div>


> [!NOTE]
> Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, der der vertrauenswürdige Status für die Ausführung als Teil von lync Server 2013 zugewiesen ist, aber kein integrierter Teil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.



</div>

Zum Erstellen eines vertrauenswürdigen Anwendungspools öffnen Sie die lync Server 2013-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Details zu den im vorhergehenden Befehl verwendeten Parametern geben Sie an der Eingabeaufforderung der lync Server-Verwaltungsshell Folgendes ein:<BR>Get-Help New-CsTrustedApplicationPool-Full | Weitere



</div>

Konfigurieren Sie nach dem Erstellen des vertrauenswürdigen Anwendungspools den Watcher-Knoten Computer, um synthetische Transaktionen als vertrauenswürdige Anwendung auszuführen. Dies erfolgt mithilfe des Cmdlets **New-CsTrustedApplication** und eines Befehls ähnlich wie hier:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Wenn der vorhergehende Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wurde, führen Sie Enable-CsTopology aus, um sicherzustellen, dass die Änderungen wirksam werden:

    Enable-CsTopology

Nach dem Ausführen von enable-CsTopology empfehlen wir, den Computer neu zu starten.

Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie Folgendes an der Eingabeaufforderung der lync Server-Verwaltungsshell ein:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten

Für jeden Watcher-Knoten muss ein Standardzertifikat mit dem lync Server-Bereitstellungs-Assistenten zugewiesen sein.

**So weisen Sie ein Standardzertifikat zu**

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **lync Server**, und klicken Sie dann auf **lync Server-Bereitstellungs-Assistent**.

2.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren** , und klicken Sie dann unter der Überschrift **anfordern, installieren oder Zertifikat zuweisen**auf **Ausführen** .
    
    <div>
    

    > [!NOTE]
    > Wenn die Schaltfläche <STRONG>Ausführen</STRONG> deaktiviert ist, müssen Sie möglicherweise zuerst auf <STRONG>Ausführen</STRONG> unter <STRONG>lokalen Konfigurationsspeicher installieren</STRONG>klicken.

    
    </div>

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie bereits über ein Zertifikat verfügen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf **Standard** , und klicken Sie dann auf **zuweisen**. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
      - Wenn Sie ein Zertifikat anfordern müssen, um das Standardzertifikat zu verwenden, klicken Sie auf **anfordern** , und führen Sie dann die Schritte im Zertifikat Anforderungs-Assistenten aus, um dieses Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserverzertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installieren und Konfigurieren eines Watcher-Knotens

Nachdem Sie den Watcher-Knoten Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei Watchernode. msi ausführen. (Sie müssen Watchernode. msi auf einem Computer ausführen, auf dem sowohl die Operations Manager-Agentendateien als auch die Hauptkomponenten von lync Server 2013 installiert sind.)

**So installieren und konfigurieren Sie einen Watcher-Knoten**

1.  Öffnen Sie die lync Server-Verwaltungsshell, indem Sie auf **Start**klicken, auf **Alle Programme**klicken, auf **lync Server**und dann auf **lync Server-Verwaltungsshell**klicken.

2.  Geben Sie in der lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (geben Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode. msi an):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Sie können Watchernode. msi auch über ein Befehlsfenster ausführen. Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG> und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben vorhergehenden Befehl ein.

    
    </div>

Beachten Sie, dass das Name-Wert-Paar in der vorhergehenden Befehls Authentifizierung = TrustedServer die Groß-/Kleinschreibung beachtet. Sie müssen es genau wie gezeigt eingeben. Der folgende Befehl schlägt fehl, da er nicht das richtige Buchstaben Gehäuse verwendet:

C:\\Tools\\Watchernode. msi Authentication = trustedserver

Sie können den TrustedServer-Modus nur für Computer verwenden, die sich im Umkreisnetzwerk befinden. Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Testbenutzer Kennwörter auf dem Computer verwalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

