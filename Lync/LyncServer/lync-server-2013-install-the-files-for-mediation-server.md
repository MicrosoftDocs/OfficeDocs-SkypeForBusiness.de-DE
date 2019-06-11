---
title: 'Lync Server 2013: Installieren der Dateien für den Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installieren der Dateien für den Vermittlungsserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-06_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als lokaler Administrator beim Server angemeldet sein und ein Domänenbenutzerkonto verwenden, das mindestens Mitglied der Gruppe „RTCUniversalReadOnlyAdmins“ ist.

Führen Sie die Schritte in diesem Thema aus, um den Bereitstellungs-Assistenten für lync Server 2013 auszuführen, um die Dateien für den Vermittlungsserver auf einem Computer zu installieren, den Sie einem Mediationsserver Pool hinzugefügt haben, als Sie den Pool mithilfe von Topologie-Generator definiert und veröffentlicht haben. Wenn Sie den Mediationsserver für Dateien installieren, können Sie auch das für jeden Computer in einem vermittlungsserverpool erforderliche Zertifikat installieren und zuweisen.

Wenn Sie auf dieser Website bereits Vermittlungsserver bereitgestellt haben, die sich auf den Front-End-Pools oder dem Standard Edition-Server befinden, können Sie dieses Thema überspringen und stattdessen die [Konfiguration von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)fortsetzen.

<div>


> [!NOTE]  
> In diesem Thema wird davon ausgegangen, dass Sie bereits einen eigenständigen vermittlungsserverpool definiert und veröffentlicht haben, wie unter <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013</A> beschrieben und <A href="lync-server-2013-publish-the-topology.md">Veröffentlichen der Topologie in lync Server 2013</A> in der Bereitstellung Dokumentation, und Sie haben überprüft, ob die Computer im vermittlungsserverpool die Voraussetzungen erfüllen, die unter <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Voraussetzungen für Enterprise-VoIP in lync Server 2013</A> und <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013</A>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>So installieren Sie die Dateien für einen eigenständigen Vermittlungsserverpool

1.  Klicken Sie auf dem Installationsmedium mit der \<rechten Maustaste\>auf Installationsmedien**\\Setup\\amd64\\Setup. exe**, und klicken Sie dann auf **als Administrator ausführen**.

2.  Klicken Sie auf der Seite **Installationsspeicherort** auf **OK**.

3.  Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich stimme zu** und klicken Sie anschließend auf **OK**. (Dieser Schritt ist erforderlich, um fortfahren zu können.)

4.  Klicken Sie auf der Seite mit dem Bereitstellungs- **Assistenten von lync Server 2010** auf **lync Server System installieren oder aktualisieren**.

5.  Klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.

6.  Übernehmen Sie auf der Seite **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** die Standardeinstellung **Direkt aus zentralem Verwaltungsspeicher abrufen** und klicken Sie auf **Weiter**.

7.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.

8.  Klicken Sie neben **Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten**auf **Ausführen**, und klicken Sie dann auf **weiter**.

9.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als **Abgeschlossen** angezeigt wird, klicken Sie auf **Fertig stellen**.

10. Klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**. Folgen Sie den Anweisungen auf dem Bildschirm und übernehmen Sie die Standardeinstellungen. Da der Vermittlungsserver ein Zertifikat benötigt, müssen Sie **Schritt 3** zweimal ausführen: einmal zum Ausstellen und noch einmal zum Zuweisen des erforderlichen Zertifikats.

11. Wenn das Zertifikat ordnungsgemäß ausgestellt und zugewiesen wurde, klicken Sie neben **Schritt 4: Dienste starten** auf **Ausführen** und folgen Sie den Anweisungen auf dem Bildschirm.

12. Wenn **Schritt 4** erfolgreich abgeschlossen wurde, starten Sie den Server neu und melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ an.

13. Überprüfen Sie auf dem Computer, auf dem Sie die lync Server-Systemsteuerung ausführen, auf der Seite **Topologie** der lync Server-Systemsteuerung, dass der Dienststatus des Vermittlungsservers als grünes Häkchen angezeigt wird. Wenn ein rotes X angezeigt wird, wählen Sie den Vermittlungsserver aus. Klicken Sie im Menü **Aktion** auf **Alle Dienste starten**.

Wenn Sie dem vermittlungsserverpool mehr als einen Computer hinzugefügt haben, führen Sie die Schritte in diesem Verfahren auf allen anderen Computern im vermittlungsserverpool aus. Wenn Sie keine Dateien für den Vermittlungsserver für andere Computer installieren müssen, führen Sie die Verfahren unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) aus, um die Einstellungen für die trunk-Verbindung zwischen diesem vermittlungsserverpool zu konfigurieren (oder aller Mediation Server an einer Website) und deren Peer.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

