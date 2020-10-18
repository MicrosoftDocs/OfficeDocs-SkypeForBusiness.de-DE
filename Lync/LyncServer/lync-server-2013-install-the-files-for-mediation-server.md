---
title: 'Lync Server 2013: Installieren der Dateien für Vermittlungsserver'
description: 'Lync Server 2013: Installieren Sie die Dateien für Vermittlungsserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574071"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installieren der Dateien für Vermittlungsserver in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-06_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie am Server mindestens als lokaler Administrator und als Domänenbenutzer angemeldet sein, der mindestens Mitglied der Gruppe RTCUniversalReadOnlyAdmins ist.

Führen Sie die Schritte in diesem Thema aus, um lync Server 2013-Bereitstellungs-Assistenten auszuführen, um die Dateien für Vermittlungsserver auf einem Computer zu installieren, den Sie einem Vermittlungsserver Pool hinzugefügt haben, als Sie den Pool mithilfe des Topologie-Generators definiert und veröffentlicht haben. Bei der Installation von Dateien Vermittlungsserver müssen Sie auch das für jeden Computer in einem Vermittlungsserver-Pool erforderliche Zertifikat installieren und zuweisen.

Wenn Sie auf dieser Website bereits Vermittlungsserver in den Front-End-Pools oder Standard Edition-Server bereitgestellt haben, können Sie dieses Thema überspringen und stattdessen mit der [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortfahren.

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen Vermittlungsserver-Pool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Vermittlungsserver in Topology Builder in lync Server 2013</A> beschrieben, und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellungsdokumentation und dass Sie <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">sicher</A>gestellt haben, dass die Computer im Vermittlungsserver Pool die Voraussetzungen erfüllen, die unter " <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP</A> in lync Server 2013"



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>So installieren Sie die Dateien für einen eigenständigen Vermittlungsserver Pool

1.  Klicken Sie auf dem Installationsmedium mit der rechten Maustaste auf \<installation media\> ** \\ Setup \\ amd64 \\Setup.exe**, und klicken Sie dann auf **als Administrator ausführen**.

2.  Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.

3.  Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich akzeptiere**, und klicken Sie dann auf **OK**. (Erforderlich, um den Vorgang fortzusetzen.)

4.  Klicken Sie auf der Seite **lync Server 2010-Bereitstellungs-Assistenten** auf **lync Server System installieren oder aktualisieren**.

5.  Klicken Sie neben **Schritt 1: lokalen Konfigurationsspeicher installieren**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.

6.  Übernehmen Sie auf der Seite **lokales Replikat von zentraler Verwaltungsspeicher konfigurieren** den Standard **Abruf direkt aus der zentraler Verwaltungsspeicher**, und klicken Sie dann auf **weiter**.

7.  Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.

8.  Klicken Sie neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen**, und klicken Sie dann auf **weiter**.

9.  Wenn der Aufgabenstatus als **abgeschlossen**angezeigt wird, klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Fertig stellen**.

10. Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm, und akzeptieren Sie die Standardeinstellungen. Für den Vermittlungsserver ist ein Zertifikat erforderlich, und Sie führen **Schritt 3** zweimal aus: einmal, um das erforderliche Zertifikat auszustellen und es erneut zuzuweisen.

11. Wenn das Zertifikat ausgestellt und ordnungsgemäß zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten**auf **Ausführen**, und folgen Sie dann den Anweisungen auf dem Bildschirm.

12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu, und melden Sie sich als Mitglied der Admins-Gruppe am Server an.

13. Überprüfen Sie auf dem Computer, auf dem Sie lync Server-Systemsteuerung durchführen, auf der Seite **Topologie** von lync Server-Systemsteuerung, ob der Dienststatus der Vermittlungsserver als grünes Häkchen angezeigt wird. Wenn stattdessen ein rotes X angezeigt wird, wählen Sie das Vermittlungsserver aus. Klicken Sie im Menü **Aktion** auf **alle Dienste starten**.

Wenn Sie dem Vermittlungsserver Pool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im Vermittlungsserver-Pool aus. Wenn Sie keine Dateien für Vermittlungsserver für andere Computer installieren müssen, befolgen Sie die Verfahren unter Konfigurieren von [Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) , um Einstellungen für die trunkverbindung zwischen diesem Vermittlungsserver Pool (oder allen Vermittlungsservern an einem Standort) und seinem Peer zu konfigurieren.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

