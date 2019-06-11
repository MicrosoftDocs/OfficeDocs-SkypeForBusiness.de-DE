---
title: 'Lync Server 2013: Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbdc22f2e877d7dafc8f52506d77312730ab428
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Die Instant Messaging-Konnektivität (im) des gehosteten Anbieters ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chatnachrichten für die Kommunikation mit Benutzern von Chat Diensten, die von gehosteten Anbietern bereitgestellt werden, einschließlich Microsoft Office 365 und lync online.

Jeder gehostete Anbieter ist mit dem vollqualifizierten Domänennamen für den Edge-Server des Anbieters konfiguriert, und die Standard Überprüfungsstufe **ermöglicht Benutzern, nur mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden**.

Gehen Sie wie folgt vor, um gehostete Anbieter zu erstellen oder zu bearbeiten:

<div>

## <a name="to-create-or-edit-hosted-providers"></a>So erstellen oder bearbeiten Sie gehostete Anbieter

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **SIP-Verbund Anbieter**.

4.  Wenn Sie einen neuen gehosteten Anbieter erstellen müssen, klicken Sie auf **neu** , und klicken Sie dann auf **gehosteter Anbieter**.

5.  Wenn Sie einen Eintrag aus der Liste der gehosteten Anbieter bearbeiten möchten, wählen Sie einen gehosteten Anbieter aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

6.  Auf der Seite **SIP-Verbund Anbieter bearbeiten** können Sie die folgenden Einstellungen eingeben oder bearbeiten:
    
      - **Aktivieren der Kommunikation mit diesem Anbieter**   durch Auswählen dieser Einstellung wird die Kommunikation mit den Benutzern dieses Anbieters aktiviert.
    
      - **Anbietername:**   eine erforderliche Eigenschaft, geben Sie den Namen des Anbieters ein, wie er in der Liste der SIP-Verbund Anbieter wiedergegeben wird.
    
      - **Access Edge Service (FQDN):**   eine erforderliche Eigenschaft, geben Sie den vollqualifizierten Domänennamen des Access Edge-Diensts des gehosteten Anbieters ein, den Sie konfigurieren. Diese Informationen sollten vom gehosteten Anbieter bereitgestellt werden und sollten nur geändert werden, wenn der gehostete Anbieter eine Änderung an dem FQDN des Access Edge-Diensts beim gehosteten Anbieter vornimmt.
    
      - **Standard Überprüfungsstufe:**   die Standardeinstellung, die es **Benutzern ermöglicht, mit Personen in Ihrer Kontaktliste zu kommunizieren, die diesen Anbieter verwenden** , beschränkt die Kommunikation auf Kontakte, die Sie akzeptiert haben und die sich in Ihrer Kontaktliste befinden.
        
        **Wenn Sie Benutzern erlauben, mit allen Personen zu kommunizieren, die diesen Anbieter verwenden, wird** die Einschränkung entfernt, die Sie erhalten haben und eine Kontakt Einladung akzeptieren müssen. Diese Einstellung beschränkt nicht, wer Sie aus dem Netzwerk des gehosteten Anbieters kontaktieren kann.

7.  Wenn Sie die Konfiguration der Einstellungen abgeschlossen haben, **** klicken Sie zum Speichern auf übernehmen, oder klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

