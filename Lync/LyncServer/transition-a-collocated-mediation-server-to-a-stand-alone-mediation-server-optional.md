---
title: Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Umstieg auf einen bereitstehenden Vermittlungsserver zu einem eigenständigen Vermittlungsserver (optional)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Führen Sie das folgende Verfahren aus, um den Vermittlungsserver, der sich auf dem Standard Edition-Server oder-Front-End-Pool befindet, zu einem eigenständigen Vermittlungsserver für eine Bereitstellung mit einem einzelnen Standort zu wechseln.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>So wechseln Sie einen kombinierten Vermittlungsserver zu einem eigenständigen Vermittlungsserver

1.  Öffnen Sie eine vorhandene Topologie aus dem Topologie-Generator.

2.  Navigieren Sie im linken Bereich zu **Mediations Pools**.

3.  Klicken Sie mit der rechten Maustaste auf **Mediation Pools** , und wählen Sie **neuer Vermittlungs Server**aus.

4.  Geben Sie auf der Seite **neuen Mediations Pool definieren** den FQDN des neuen Vermittlungs Server Pools an. Wählen Sie außerdem aus, ob dieser Pool ein Einzelserver-oder ein Pool mit mehreren Servern sein soll, und klicken Sie dann auf **weiter**.

5.  Wählen Sie den Front-End-Serverpool des nächsten Hop aus, an den der neue Vermittlungsserver eingehende Anrufe weiterleiten soll, und klicken Sie dann auf **weiter**.

6.  Wählen Sie den von dem Vermittlungs Server zu verwendenden Edge-Pool aus, und klicken Sie auf **weiter**.

7.  Ordnen Sie auf der Seite **PSTN-Gateways angeben** das vorherige PSTN-Gateway dem Vermittlungs Server zu. Wählen Sie das Gateway aus, und klicken Sie dann auf **Hinzufügen**.

8.  Klicken Sie auf **Fertig stellen** , um den Assistenten zum **Definieren eines neuen Mediations Pools** zu schließen.

9.  Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.

10. Wählen Sie im Bereich **Aktionen** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.

11. Führen Sie die Schritte unter [Installieren des Servers für Mediations Dateien in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in der Bereitstellungsdokumentation aus, um die Dateien auf dem neuen Vermittlungsserver zu installieren.

12. Nachdem die Dateien auf dem Vermittlungs Server installiert wurden, kehren Sie zu Topology Builder zurück, und navigieren Sie im linken Bereich zum Pool.

13. Klicken Sie mit der rechten Maustaste auf den Pool, und wählen Sie **Eigenschaften bearbeiten**aus.

14. Deaktivieren Sie unter **Mediation Server**das Kontrollkästchen für **Mediation Server aktiviert** , und klicken Sie dann auf **OK**.

15. Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server 2013**aus.

16. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.

</div>

</div>

<span> </span>

</div>

</div>

</div>

