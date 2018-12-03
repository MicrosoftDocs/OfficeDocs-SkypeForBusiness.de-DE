---
title: Konfigurieren des Vermittlungsservers
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Konfigurieren des Vermittlungsservers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

In diesem Verfahren werden die Schritte zum Konfigurieren des Lync Server 2013 Pools für die Verwendung des Lync Server 2013 Vermittlungsservers anstelle der Vorversion Office Communications Server 2007 R2 Mediation Server verwenden.

Erfolgreich veröffentlichen, aktivieren oder Deaktivieren einer Topologie, die beim Hinzufügen oder Entfernen einer Serverrolle, Sie sollte als ein Benutzer ein Mitglied der Gruppen RTCUniversalServerAdmins und Domänen-Admins angemeldet sein. Es ist auch möglich, die richtigen Administratorrechte und Berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Weitere Informationen hierzu finden Sie unter Delegate Setup Permissions in der Standard Edition-Server oder Enterprise Edition-Server-Dokumentation zur Bereitstellung. Für weitere konfigurationsänderungen ist nur die Mitgliedschaft in der Gruppe RTCUniversalServerAdmins ist erforderlich.

<div>


> [!NOTE]  
> Aktuelle Informationen über das Auffinden von qualifizierten PSTN-Gateways, IP-PBXs und SIP-Trunking-Diensten, die mit Lync Server 2013 arbeiten, finden Sie unter "Microsoft Unified Communications Open Interoperability Program" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>So konfigurieren Sie Mediation Server Using Topologie-Generator

1.  Öffnen Sie eine vorhandene Topologie Topologie-Generator.

2.  Navigieren Sie im linken Bereich zu **PSTN-Gateways**.

3.  Mit der rechten Maustaste **PSTN-Gateways**, und klicken Sie dann auf **Neues IP/PSTN-Gateway**.

4.  Führen Sie die Seite **Neues IP/PSTN-Gateway definieren** die folgenden Informationen ein:
    
      - Geben Sie das Gateway-FQDN oder die IP-Adresse ein. Der FQDN des Gateways ist erforderlich, wenn das Gateway TLS-Protokoll verwendet wird.
    
      - Akzeptieren Sie den Standardwert des **Überwachungsport für IP/PSTN-Gateway** , oder geben Sie den neuen Überwachungsport ein, falls er geändert wurde.
    
      - Legen Sie die **Sip-Transportprotokoll fest**.

5.  Navigieren Sie im linken Bereich der **Enterprise Edition-Front-End-Pool** oder **Standard Edition-Server**.

6.  Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

7.  Klicken Sie unter **Vermittlungsserver**die **Überwachungsports**festgelegt.

8.  Ordnen Sie im nächsten Schritt das neu erstellte PSTN-Gateway, indem Sie es markieren und auf **Hinzufügen**.

9.  Wählen Sie im **Topologie-Generator**den obersten Knoten **Lync Server**aus.

10. Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.

11. Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.

<div>


> [!NOTE]  
> Es ist wichtig, schließen Sie das nächste Thema <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Ändern VoIP-Routen für die neue Lync Server 2013-Vermittlungsservers verwenden</A> , um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver zeigen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

