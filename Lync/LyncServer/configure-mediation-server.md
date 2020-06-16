---
title: Konfigurieren von Vermittlungsserver
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Konfigurieren von Vermittlungsserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

In diesem Verfahren werden die Schritte zum Konfigurieren des lync Server 2013 Pools für die Verwendung der lync Server 2013 Vermittlungsserver anstelle des Legacy-Office Communications Server 2007 R2 Vermittlungsservers erläutert.

To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.

<div>


> [!NOTE]  
> Aktuelle Informationen zur Suche nach qualifizierten PSTN-Gateways, IP-Nebenstellenanlagen und SIP-Trunking-Diensten, die mit lync Server 2013 zusammenarbeiten, finden Sie unter "Microsoft Unified Communications Open Interoperability Program" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>So konfigurieren Sie den Vermittlungsserver mithilfe des Topologie-Generators

1.  Öffnen Sie eine bestehende Topologie im Topologie-Generator.

2.  Navigieren Sie im linken Bereich zu **PSTN-Gateways**.

3.  Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie auf **Neues IP/PSTN-Gateway**.

4.  Geben Sie auf der Seite **Neues IP/PSTN-Gateway definieren** die folgenden Informationen ein:
    
      - Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.
    
      - Übernehmen Sie den Standardwert von **Überwachungsport für das IP/PSTN-Gateway**, oder geben Sie den neuen Überwachungsport ein, falls er geändert wurde.
    
      - Legen Sie das **SIP-Transportprotokoll** fest.

5.  Navigieren Sie im linken Bereich zum **Front-End-Pool der Enterprise Edition** oder zum **Standard Edition-Server**.

6.  Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

7.  Legen Sie unter **Vermittlungsserver** die **Überwachungsports** fest.

8.  Ordnen Sie dann das neu erstellte PSTN-Gateway zu, indem Sie es markieren und auf **Hinzufügen** klicken.

9.  Wählen Sie im **Topologie-Generator** den obersten Knoten **Lync Server** aus.

10. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus, und klicken Sie auf **Weiter**.

11. Klicken Sie nach dem Abschließen des **Veröffentlichungs-Assistenten** auf **Fertig stellen**, um den Assistenten zu schließen.

<div>


> [!NOTE]  
> Es ist wichtig, dass Sie das nächste Thema durchführen, indem Sie <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">VoIP-Routen so ändern, dass die neue lync Server 2013 Vermittlungsserver verwendet</A> wird, um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver hinweisen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

