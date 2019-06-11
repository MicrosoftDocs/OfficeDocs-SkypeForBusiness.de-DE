---
title: Überprüfen der Lync Server 2010-Umgebung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Überprüfen der Lync Server 2010-Umgebung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Bevor Sie lync Server 2013 in einem koexistenzstatus mit lync Server 2010 bereitstellen, müssen Sie sicherstellen, dass die lync Server 2010-Dienste konfiguriert und gestartet wurden. Es ist wichtig, die wichtigsten Dienste und Features zu identifizieren, die in ihrer Legacyumgebung vorhanden sind, bevor ein lync Server 2013-Pilot Pool bereitgestellt wird. Bevor Sie Microsoft lync Server 2013 xmpp in einem koexistenzstatus mit einer älteren XMPP-Bereitstellung bereitstellen, müssen Sie überprüfen, ob die Legacy-XMPP-Dienste konfiguriert und gestartet wurden, und ermitteln, welchen Partnerverbund Partner die Legacy-XMPP-Konfiguration unterstützt. Die Überprüfung Ihrer Legacy-lync Server 2010-Bereitstellung umfasst Folgendes:

  - Überprüfen, ob die lync Server 2010-Dienste gestartet wurden

  - Überprüfen der Topologie und der Benutzer in lync Server 2010

  - Überprüfen der Einstellungen für den Verbund und den Edgeserver

  - Überprüfen von XMPP-Diensten und Verbundpartnern

**Überprüfen, ob die lync Server 2010-Dienste gestartet wurden**

1.  Navigieren Sie vom lync Server 2010-Front-End-Server zum Applet\\Dienste für administrative Tools.

2.  Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:
    
    ![Liste der Dienste, die auf dem Front-End-Server ausgeführt werden] (images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste der Dienste, die auf dem Front-End-Server ausgeführt werden")

**Überprüfen der lync Server 2010-Topologie in der lync Server-Systemsteuerung**

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.

2.  Öffnen Sie die lync Server-Systemsteuerung.

3.  Wählen Sie **Topologie**aus. Überprüfen Sie, ob die verschiedenen Server in ihrer lync Server 2010-Bereitstellung aufgelistet sind.
    
    ![Lync Server 2010-Seite "Systemsteuerung"] (images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010-Seite \"Systemsteuerung\"")

**So überprüfen Sie lync Server 2010-Benutzer in der lync Server-Systemsteuerung**

1.  Öffnen Sie die lync Server-Systemsteuerung.

2.  Wählen Sie **Benutzer** aus, und klicken Sie dann auf **Suchen**.

3.  Überprüfen Sie, ob die Spalte des **registrierungspools** auf den lync Server 2010-Pool für jeden aufgelisteten Benutzer verweist.
    
    ![Lync Server 2010-System] Steuerung mit Einträgen für Benutzer (images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010-System") Steuerung mit Einträgen für Benutzer

**So überprüfen Sie die Edge-und Federation-Einstellungen von lync Server 2010**

1.  Starten Sie den Topologie-Generator.

2.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**.

3.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie mit dem standardmäßigen tbxml-Dateityp.

4.  Erweitern Sie den lync Server 2010-Knoten, um die verschiedenen Server Rollen in der Bereitstellung anzuzeigen.

5.  Wählen Sie den Websiteknoten aus, und überprüfen Sie, ob ein **Standort Verbund-Routen Zuordnungs** Wert festgesetzt ist.
    
    ![Topologie-Generator, Website Verbund Route] (images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topologie-Generator, Website Verbund Route")

6.  Wählen Sie als nächstes den Standard Edition-Server oder Enterprise Edition-Front-End-Pool aus. Ermitteln Sie, ob ein Edge-Pool für Medien unter **Zuordnungen**konfiguriert wurde.
    
    ![Topologie-Generator mit Servern und Pools] (images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topologie-Generator mit Servern und Pools")

7.  Wählen Sie abschließend den Edge-Pool aus, und ermitteln Sie, ob unterhalb des **nächsten Hop-Auswahlbereichs**ein nächster Hop-Pool konfiguriert ist.
    
    ![Topologie-Generator, Auswahl des nächsten Hops] (images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topologie-Generator, Auswahl des nächsten Hops")

**Überprüfen der Konfiguration von Legacy-XMPP-Verbundpartnern**

1.  Navigieren Sie vom Legacy-XMPP-Server zum Applet Dienste\\für Verwaltungs Tools.

2.  Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewayserver gestartet wurde.
    
    ![Office Communications Server-XMPP] -Gatewaydienst (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server-XMPP") -Gatewaydienst

</div>

<span> </span>

</div>

</div>

</div>

