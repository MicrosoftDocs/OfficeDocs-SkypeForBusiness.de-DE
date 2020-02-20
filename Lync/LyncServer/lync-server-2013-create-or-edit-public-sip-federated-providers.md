---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51e31c731270bc0e3e25da712db5aff9137d84b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Die Verbindung mit öffentlichen Instant Messaging-Verbindungen ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Sofortnachrichten-Dienstanbietern bereit\!gestellt werden, einschließlich Windows Live Messenger, Yahoo und AOL.

Lync Server 2013 hat öffentliche Anbieter Konfigurationen für America Online, Windows Live und Yahoo\! und AOL. Jeder öffentliche Anbieter ist mit dem vollqualifizierten Domänennamen des Edgeservers für den jeweiligen Anbieter sowie mit der Standardüberprüfungsstufe **Benutzer können nur mit Personen in ihrer Liste 'Kontakte' kommunizieren, die diesen Anbieter verwenden** konfiguriert.

In der Standardeinstellung ist kein öffentlicher Anbieter aktiviert. Bevor Sie die öffentlichen Anbieter aktivieren, sollten Sie zunächst die Lizenzvereinbarung und die Bereitstellungsmaßnahmen abschließen. Es ist möglich, die Anbieter vor Abschluss der Lizenzvereinbarung und der Bereitstellungsmaßnahmen zu aktivieren. Benutzer können jedoch nicht mit Kontakten dieser Anbieter kommunizieren, bevor die Vorbereitungsmaßnahmen nicht abgeschlossen sind. Ausführliche Informationen zur Lizenzierung und Bereitstellung öffentlicher Anbieter finden Sie unter [configure Policies to Control Public User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Mit den folgenden Verfahren können Sie öffentliche Anbieter erstellen oder bearbeiten:

<div>

## <a name="to-create-or-edit-public-providers"></a>So erstellen oder bearbeiten Sie öffentliche Anbieter

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **SIP-Partneranbieter**.

4.  Wenn Sie einen öffentlichen Anbieter erstellen möchten, klicken Sie auf **Neu** und dann auf **Öffentlicher Anbieter**.

5.  Um einen Eintrag aus der Liste der öffentlichen Anbieter zu bearbeiten, wählen Sie einen öffentlichen Anbieter aus, klicken auf **Bearbeiten** und dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Partneranbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder ändern:
    
      - **Kommunikation mit diesem Anbieter**   aktivieren beim Auswählen dieser Einstellung wird Chat mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   eine erforderliche Eigenschaft geben Sie den Namen des Anbieters ein, der in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Zugriffs-Edgedienst (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Zugriffs-Edgedienst des Anbieters ein, den Sie konfigurieren. Diese Informationen werden als Standardelement bereitgestellt und sollten nur geändert werden, wenn der öffentliche Anbieter eine Änderung am FQDN des Zugriffs-Edgedienst beim öffentlichen Anbieter vornimmt.
    
      - **Standard Überprüfungsebene:**   die Standardeinstellung **ermöglicht Benutzern die Kommunikation mit Personen in Ihrer Kontaktliste, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        Durch Auswählen von **Benutzer können mit allen Benutzern mit diesem Anbieter kommunizieren** wird die Einschränkung entfernt, dass eine Kontakteinladung empfangen und angenommen worden sein muss. Diese Einschränkung hat keine Auswirkungen darauf, welche Benutzer aus dem Netzwerk des öffentlichen Anbieters mit Ihnen Kontakt aufnehmen können.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, klicken Sie auf **Commit**, um die Änderungen zu speichern, oder auf **Abbrechen**, um die Änderungen zu verwerfen.

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

