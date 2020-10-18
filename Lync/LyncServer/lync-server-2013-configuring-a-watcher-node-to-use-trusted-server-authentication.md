---
title: Konfigurieren eines Watcher-Knotens für die Verwendung der vertrauenswürdigen Server Authentifizierung
description: Konfigurieren eines Watcher-Knotens für die Verwendung der vertrauenswürdigen Server Authentifizierung.
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
ms.openlocfilehash: 247d628f936808a01780c7adc497342baedbbecb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576311"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>Konfigurieren eines Watcher-Knotens in lync Server 2013 zur Verwendung der vertrauenswürdigen Server Authentifizierung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Wenn sich Ihr Watcher-Knoten-Computer innerhalb des Umkreisnetzes befindet, können die Administrationsaufgaben zur Beibehaltung eines einzelnen Zertifikats anstelle zahlreicher Kennwörter für Benutzerkonten mithilfe der Trusted Server-Authentifizierung stark reduziert werden.

Der erste Schritt bei der Konfiguration der Trusted Server-Authentifizierung ist die Erstellung eines Pools vertrauenswürdiger Anwendungen zum Hosten des Watcher-Knoten-Computers. Nach der Erstellung des Pools vertrauenswürdiger Anwendungen müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten erstellen, die als vertrauenswürdige Anwendungen ausgeführt werden sollen.

<div>


> [!NOTE]
> Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die als Teil der lync Server 2013 als vertrauenswürdiger Status ausgeführt wird, aber kein integrierter Bestandteil des Produkts ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.



</div>

Öffnen Sie zum Erstellen eines vertrauenswürdigen Anwendungspools die lync Server 2013-Verwaltungsshell, und führen Sie einen Befehl wie den folgenden aus:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> Ausführliche Informationen zu den Parametern, die im vorherigen Befehl verwendet werden, geben Sie an der lync Server-Verwaltungsshell Eingabeaufforderung Folgendes ein:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

Konfigurieren Sie nach der Erstellung des Pools vertrauenswürdiger Anwendungen, den Watcher-Knoten-Computer für die Ausführung synthetischer Transaktionen als vertrauenswürdige Anwendung. Verwenden Sie dazu das **New-CsTrustedApplication**-Cmdlet und einen Befehl wie den folgenden:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Wenn der vorstehende Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wurde, führen Sie "Enable-CsTopology" aus, um sicherzustellen, dass die Änderungen wirksam werden:

    Enable-CsTopology

Nach Ausführung von "Enable-CsTopology" wird empfohlen, den Computer neu zu starten.

Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie an der lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes ein:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten

Jeder Watcher-Knoten muss mit dem lync Server-Bereitstellungs-Assistenten ein Standardzertifikat zugewiesen sein.

**So weisen Sie ein Standardzertifikat zu**

1.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **lync Server**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.

2.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren** , und klicken Sie dann unter der Überschrift **Anforderung, installieren oder Zuweisen eines Zertifikats**auf **Ausführen** .
    
    <div>
    

    > [!NOTE]
    > Wenn die Schaltfläche <STRONG>Ausführen</STRONG> deaktiviert ist, müssen Sie möglicherweise zunächst unter <STRONG>Lokalen Konfigurationsspeicher installieren</STRONG> auf <STRONG>Ausführen</STRONG> klicken.

    
    </div>

3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie bereits ein Zertifikat besitzen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf **Standard** und anschließend auf **Zuweisen**. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
      - Wenn Sie ein Zertifikat für die Verwendung als Standardzertifikat anfordern müssen, klicken Sie auf **Anforderung**, und folgen Sie den Schritten im Zertifikatanforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>Installieren und Konfigurieren eines Watcher-Knotens

Nachdem Sie den Watcher-Knoten-Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei "Watchernode.msi" ausführen. (Sie müssen Watchernode.msi auf einem Computer ausführen, auf dem sowohl die Operations Manager-Agent-Dateien als auch die lync Server 2013-Kernkomponenten installiert sind.)

**So installieren und konfigurieren Sie einen Watcher-Knoten**

1.  Öffnen Sie das lync Server-Verwaltungsshell, indem Sie auf **Start**, auf **Alle Programme**, auf **lync Server**und dann auf **lync Server-Verwaltungsshell**klicken.

2.  Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (geben Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode.msi an):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > Sie können "Watchernode.msi" auch aus einem Befehlsfenster ausführen. Um ein Befehlsfenster zu öffnen, klicken Sie auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie auf <STRONG>Als Administrator ausführen</STRONG>. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben vorstehenden Befehl ein.

    
    </div>

Beachten Sie, dass beim Namen/Wertpaar im vorstehenden Befehl "Authentication=TrustedServer" Groß-/Kleinschreibung beachtet wird. Geben Sie es genau wie angezeigt ein. Bei der Ausführung des folgenden Befehls tritt ein Fehler auf, weil nicht die richtige Folge von Klein- und Großbuchstaben verwendet wird:

C: \\ Tools \\Watchernode.msi Authentication = trustedserver

Sie können den TrustedServer-Modus nur auf Computern verwenden, die sich im Umkreisnetzwerk befinden. Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Kennwörter für Testbenutzer auf dem Computer beibehalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

