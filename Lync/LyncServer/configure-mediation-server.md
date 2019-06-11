---
title: Konfigurieren des Vermittlungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Konfigurieren des Vermittlungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

In diesem Verfahren werden die Schritte zum Konfigurieren des lync Server 2013-Pools für die Verwendung des lync Server 2013-Vermittlungsservers und nicht des Legacy Office Communications Server 2007 R2-Vermittlungsservers erläutert.

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. Es ist auch möglich, die richtigen Administratorrechte und-Berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter Delegieren von Setup Berechtigungen in der Standard Edition-Server-oder Enterprise Edition-Server Bereitstellungsdokumentation. Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.

<div>


> [!NOTE]  
> Aktuelle Informationen zum Auffinden qualifizierter PSTN-Gateways, IP-PBX-Dienste und SIP-Trunking-Diensten, die mit lync Server 2013 funktionieren, finden Sie unter "Microsoft Unified Communications <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Open Interoperability Program" unter.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>So konfigurieren Sie den Vermittlungs Server mithilfe des Topologie-Generators

1.  Öffnen Sie eine vorhandene Topologie aus dem Topologie-Generator.

2.  Navigieren Sie im linken Bereich zu **PSTN-Gateways**.

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie dann auf **neues IP/PSTN-Gateway**.

4.  Füllen Sie die Seite **neues IP/PSTN-Gateway definieren** mit den folgenden Informationen aus:
    
      - Geben Sie den FQDN oder die IP-Adresse des Gateways ein. Der FQDN des Gateways ist erforderlich, wenn das Gateway das TLS-Protokoll verwendet.
    
      - Übernehmen Sie den Standardwert des **Überwachungs-Ports für IP/PSTN-Gateway** , oder geben Sie den neuen Abhör-Port ein, wenn er geändert wurde.
    
      - Setzen Sie das **SIP-Transport Protokoll**.

5.  Navigieren Sie im linken Bereich zum **Enterprise Edition-Front-End-Pool** oder zum **Standard Edition-Server**.

6.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Stellen Sie unter **Mediation Server**die **Abhör Anschlüsse**ein.

8.  Ordnen Sie anschließend das neu erstellte PSTN-Gateway zu, indem Sie es auswählen und auf **Hinzufügen**klicken.

9.  Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem höchsten Knoten aus.

10. Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **weiter**.

11. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.

<div>


> [!NOTE]  
> Es ist wichtig, dass Sie das nächste Thema durchführen, die <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">VoIP-Routen ändern, um den neuen lync Server 2013-Vermittlungsserver zu verwenden</A> , um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver verweisen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

