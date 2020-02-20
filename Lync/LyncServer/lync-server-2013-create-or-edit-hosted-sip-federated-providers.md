---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8be79e53b0215cdfabd89e9d66f7c9e417ba40e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Hosted Provider Instant Messaging (im)-Konnektivität ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von gehosteten Anbietern bereitgestellt werden, einschließlich der Microsoft Office 365 und lync online.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers des Anbieters sowie der Standardüberprüfungsstufe **Benutzern nur die Kommunikation mit den Personen in ihren Kontaktlisten erlauben, die diesen Anbieter verwenden** konfiguriert.

Verwenden Sie zum Erstellen oder Bearbeiten von gehosteten Anbietern das folgende Verfahren:

<div>

## <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff ** und dann auf **SIP-Partnerverbundanbieter**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **Neu** und anschließend auf **Gehosteter Anbieter**.

5.  Wenn Sie in der Liste der gehosteten Anbieter einen Eintrag bearbeiten müssen, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partnerverbundanbieter bearbeiten** können Sie folgende Einstellungen eingeben oder bearbeiten:
    
      - **Kommunikation mit diesem Anbieter**   aktivieren Wenn Sie diese Einstellung auswählen, wird die Kommunikation mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   eine erforderliche Eigenschaft geben Sie den Namen des Anbieters ein, der in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Zugriffs-Edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienst des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt und nur dann geändert werden, wenn der gehostete Anbieter eine Änderung am FQDN des Zugriffs-Edgediensts beim gehosteten Anbieter vornimmt.
    
      - **Standard Überprüfungsebene:**   die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Die Auswahl der Option **Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet** entfernt die Einschränkung, dass Sie eine Kontaktanfrage erhalten und angenommen haben müssen. Diese Einstellung hat keine Auswirkungen darauf, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Einstellungen konfiguriert haben, klicken Sie auf **Commit**, um zu speichern oder auf **Abbrechen**, um die Änderungen zu verwerfen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

