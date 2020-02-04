---
title: 'Lync Server 2013: Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Letztes Änderungsdatum des Themas:** 2013-04-03_

Für diesen Schritt ist das Exchange um-Integrations Dienstprogramm (OcsUmUtil. exe) erforderlich. Dieses Tool befindet sich auf dem lync Server 2013-Server in.. \\Programmdateien\\(Common\\files) Microsoft lync\\Server 2013-Support Ordner.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Ausführen des Exchange um-Integrationstools

Das Exchange um-Integrations Dienstprogramm muss von einem Benutzerkonto mit den folgenden Merkmalen ausgeführt werden:

  - Mitgliedschaft in den Gruppen "RTCUniversalServerAdmins" und "RtcUniversalUserAdmins" (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen).

  - Benutzerrechte innerhalb der Domäne, um Kontaktobjekte im angegebenen Organisationseinheitscontainer (OU) zu erstellen.

Wenn Sie das Exchange um-Integrations Dienstprogramm ausführen, führt es die folgenden Aufgaben aus:

  - Erstellt Kontaktobjekte für jede automatische Telefonzentrale und Teilnehmerzugriffsnummer, die von Enterprise-VoIP-Benutzern verwendet werden soll.

  - Überprüft, ob der Name der einzelnen Enterprise-VoIP-Wählpläne dem zugehörigen Unified Messaging-Wähl Plan Telefonkontext entspricht. Dieser Abgleich ist nur erforderlich, wenn der um-Wählplan unter einer *früheren* Exchange-Version als Exchange 2010 Service Pack 1 (SP1) ausgeführt wird.

> [!IMPORTANT]
> Bevor Sie das Exchange um-Integrations Dienstprogramm ausführen, stellen Sie sicher, dass Sie die folgenden Schritte ausgeführt haben:
> <ul>
> <li><p>Erstellen Sie einen oder mehrere Exchange um-Wählpläne, wie in der Exchange-Produktdokumentation beschrieben.</p>
> <p>Informationen zu Microsoft Exchange Server 2010 finden &quot;Sie unter Erstellen&quot; von um- <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>Wähleinstellungen unter.</p>
> <p>Informationen zu Microsoft Exchange Server 2007 Service Pack 1 (SP1) finden &quot;Sie unter Erstellen eines Unified Messaging-SIP-URI&quot; - <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>Wähl Plans unter.</p></li>
> <li><p>Erstellen Sie einen oder mehrere entsprechende lync Server-Wählpläne, wie unter <a href="lync-server-2013-create-a-dial-plan.md">Erstellen eines Wählplans in lync Server 2013</a>beschrieben.</p></li>
> <ul><li>Wenn Sie eine frühere Exchange-Version als Microsoft Exchange Server 2010 SP1 verwenden, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des entsprechenden Exchange Unified Messaging (um) SIP-Wählplans im Feld " <STRONG>einfacher Name</STRONG> " des lync Server 2013-Wählplans eingeben. Wenn Sie Microsoft Exchange Server 2010 SP1 oder das neueste Service Pack verwenden, ist diese Wählplannamens Übereinstimmung nicht erforderlich.</li></ul>
> <li>Erstellen Sie eine automatische Telefonzentrale, und stellen Sie sicher, dass die Nummer des Teilnehmerzugriffs und die Nummer der automatischen Telefonzentrale im E. 164-Format vorliegen.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>So führen Sie das Exchange um-Integrations Dienstprogramm aus

1.  Öffnen Sie auf einem Front-End-Server eine Eingabeaufforderung, und geben Sie **CD% COMMONPROGRAMFILES\\%\\Microsoft lync Server 2013-Unterstützung**ein, und drücken Sie dann die EINGABETASTE.

2.  Geben Sie **OcsUmUtil. exe**ein, und drücken Sie dann die EINGABETASTE.

3.  Klicken Sie auf **Daten laden** , um alle vertrauenswürdigen Exchange-Gesamtstrukturen zu finden.

4.  Wählen Sie in der Liste **SIP-Wählpläne** einen um-SIP-Wählplan aus, für den Sie Kontaktobjekte erstellen möchten, und klicken Sie dann auf **Hinzufügen**.

5.  Übernehmen Sie im Feld **Kontakt** die Standardorganisationseinheit, oder klicken Sie auf **Durchsuchen** , um die **OU-Auswahl**zu starten. Im Feld " **OU-Auswahl** " können Sie eine OU auswählen und auf **OK**klicken, oder Sie können auf **neue Organisations** Einheit erstellen klicken, um eine neue Organisationseinheit unter dem Stamm oder einer anderen ou in der Domäne zu erstellen (beispielsweise "ou = RTC-Sonderkonten, DC = FourthCoffee, DC = com"), und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Der Distinguished Name (DN) der Organisationseinheit, die Sie ausgewählt oder erstellt haben, wird jetzt im Feld <STRONG>Organisationseinheit</STRONG> angezeigt.

    
    </div>

6.  Übernehmen Sie im Feld **Name** entweder den Standardnamen des Wählplans, oder geben Sie einen neuen Anzeigenamen für das zu erstellende Kontaktobjekt ein.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie beispielsweise ein Kontaktobjekt für einen Teilnehmerzugriff erstellen, können Sie ihm einfach nur den Abonnenten Zugriff nennen.

    
    </div>

7.  Übernehmen Sie im Feld **SIP-Adresse** entweder die standardmäßige SIP-Adresse, oder geben Sie eine neue SIP-Adresse ein.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine neue SIP-Adresse eingeben, muss Sie mit <STRONG>SIP:</STRONG> (also "SIP:" einschließlich des Doppelpunkts) beginnen.

    
    </div>

8.  Wählen Sie in der Liste **Server oder Pool** den Standard Edition-Server oder den Front-End-Pool aus, in dem das Kontaktobjekt aktiviert werden soll.
    
    <div>
    

    > [!NOTE]  
    > Vorzugsweise ist der ausgewählte Pool derselbe Pool, in dem Benutzer, die für Enterprise-VoIP aktiviert sind, und Exchange um bereitgestellt werden.

    
    </div>

9.  Wählen Sie in der Liste **Telefonnummer** entweder **Rufnummer eingeben** oder **diese Pilotnummer in Exchange um verwenden aus** , und geben Sie dann eine Telefonnummer ein.

10. Wählen Sie in der Liste **Kontakttyp** den Typ des Kontakts aus, den Sie erstellen möchten, und klicken Sie dann auf **OK**.

11. Wiederholen Sie die Schritte 1 bis 10 für weitere Kontaktobjekte, die Sie erstellen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie sollten für jede automatische Telefonzentrale mindestens einen Kontakt erstellen. Wenn Sie den externen Zugriff wünschen, benötigen Sie außerdem einen Kontakt für den Teilnehmerzugriff und geben direkte Durchwahlnummern (DID) an.

    
    </div>

</div>

Um zu überprüfen, ob die Kontaktobjekte erstellt wurden, öffnen Sie Active Directory-Benutzer und-Computer, und wählen Sie die Organisationseinheit aus, in der die Objekte erstellt wurden. Die Kontaktobjekte sollten im Detailbereich angezeigt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

