---
title: Überprüfen der lync Server 2010 Umgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a162c51dabf88231edc7fb5a5f5372a9f29d8687
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Überprüfen der lync Server 2010 Umgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Bevor Sie lync Server 2013 im koexistenzstatus mit lync Server 2010 bereitstellen, müssen Sie überprüfen, ob lync Server 2010 Dienste konfiguriert und gestartet wurden. Es ist wichtig, wichtige Dienste und Features zu identifizieren, die in ihrer Vorgänger Umgebung vorhanden sind, bevor Sie einen lync Server 2013-Pilot Pool bereitstellen. Bevor Sie Microsoft lync Server 2013 xmpp in einem koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die älteren XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welcher Verbundpartner von der älteren XMPP-Konfiguration unterstützt wird. Die Überprüfung Ihrer Legacy-lync Server 2010-Bereitstellung umfasst Folgendes:

  - Überprüfen, ob die lync Server 2010 Dienste gestartet wurden

  - Überprüfen der Topologie und der Benutzer in lync Server 2010.

  - Überprüfen der Partnerverbund- und Edgeservereinstellungen

  - Überprüfen der XMPP-Dienste und Verbundpartner

**Überprüfen, lync Server 2010 Dienste gestartet wurden**

1.  Navigieren Sie im lync Server 2010 Front-End-Server zum Applet Dienste für administrative\\Tools.

2.  Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
    ![Liste der auf Front-End-Server ausgeführten Dienste](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste der auf Front-End-Server ausgeführten Dienste")

**Überprüfen der lync Server 2010 Topologie in lync Server-Systemsteuerung**

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe RTCUniversalServerAdmins oder der Administratorrolle CsAdministrator oder CsUserAdministrator ist, am Front-End-Server an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Wählen Sie **Topologie** aus. Stellen Sie sicher, dass die verschiedenen Server in ihrer lync Server 2010-Bereitstellung aufgeführt sind.
    
    ![Lync Server 2010-topologieseite "Systemsteuerung"](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010-topologieseite "Systemsteuerung"")

**So überprüfen Sie lync Server 2010 Benutzer in lync Server-Systemsteuerung**

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Wählen Sie **Benutzer** aus, und klicken Sie dann auf **Suchen**.

3.  Stellen Sie sicher, dass die Spalte **Registrierungspool** für jeden aufgelisteten Benutzer auf den lync Server 2010 Pool zeigt.
    
    ![Lync Server 2010 Systemsteuerung, die Benutzer auflistet](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Systemsteuerung, die Benutzer auflistet")

**So überprüfen Sie lync Server 2010 Edge-und Verbund Einstellungen**

1.  Starten Sie den Topologie-Generator.

2.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.

3.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.

4.  Erweitern Sie den Knoten lync Server 2010, um die verschiedenen Server Rollen in der Bereitstellung anzuzeigen.

5.  Wählen Sie den Knoten Website aus, und überprüfen Sie, ob ein **Standort Verbund-Routen Zuordnungs** Wert festgelegt ist.
    
    ![Topologie-Generator, Standort Verbund Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topologie-Generator, Standort Verbund Route")

6.  Wählen Sie anschließend den Standard Edition Server- oder Enterprise Edition-Front-End-Pool aus. Bestimmen Sie, ob unter **Zuordnungen** ein Edgepool für Medien konfiguriert wurde.
    
    ![Topologie-Generator mit Servern und Pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topologie-Generator mit Servern und Pools")

7.  Wählen Sie schließlich den Edgepool aus, und identifizieren Sie, ob für **Auswahl für nächsten Hop** ein nächster Hoppool konfiguriert ist.
    
    ![Topologie-Generator, Auswahl des nächsten Hops](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topologie-Generator, Auswahl des nächsten Hops")

**Überprüfen der XMPP-Verbundpartnerkonfiguration der Vorversion**

1.  Navigieren Sie auf dem vorversions-XMPP-Server\\zum Applet Dienste für administrative Tools.

2.  Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.
    
    ![Office Communications Server XMPP-Gatewaydienst](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP-Gatewaydienst")

</div>

<span> </span>

</div>

</div>

</div>

