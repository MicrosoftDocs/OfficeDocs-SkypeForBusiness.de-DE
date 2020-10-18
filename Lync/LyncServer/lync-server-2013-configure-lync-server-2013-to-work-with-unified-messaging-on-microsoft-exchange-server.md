---
title: 'Lync Server 2013: Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Exchange Server'
description: 'Lync Server 2013: Konfigurieren Sie lync Server 2013 für die Zusammenarbeit mit Unified Messaging in Exchange Server.'
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
ms.openlocfilehash: 05ef2902ffc03b14e04b378a2ef18e03c8c58372
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578041"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Exchange Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

_**Letztes Änderungsstand des Themas:** 2013-04-03_

Für diesen Schritt ist das Exchange um Integration Utility (OcsUmUtil.exe) erforderlich. Dieses Tool befindet sich auf dem lync Server 2013-Server in der.. \\ Programmdateien \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ Support Ordner.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Ausführung des Exchange um-Integrationsprogramms

Das Exchange um-Integrations Dienstprogramm muss von einem Benutzerkonto mit den folgenden Merkmalen ausgeführt werden:

  - Mitgliedschaft in der RTCUniversalServerAdmins-und RtcUniversalUserAdmins-Gruppe (einschließlich der Berechtigung zum Lesen Exchange Server Unified Messaging-Einstellungen).

  - Benutzerrechte innerhalb der Domäne zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit).

Wenn Sie das Exchange um-Integrationsprogramm ausführen, werden die folgenden Aufgaben ausgeführt:

  - Erstellt Kontaktobjekte für jede automatische Telefonzentrale und Teilnehmerzugriffsnummer, die von Enterprise-VoIP-Benutzern verwendet werden soll.

  - Überprüft, ob der Name der einzelnen Enterprise-VoIP-Wähleinstellungen mit dem zugehörigen Telefonkontext für Unified Messaging (um)-Wähleinstellungen übereinstimmt. Diese Übereinstimmung ist nur erforderlich, wenn die um-Wähleinstellungen in *einer Exchange-* Version vor Exchange 2010 Service Pack 1 (SP1) ausgeführt werden.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie die folgenden Schritte ausgeführt haben, bevor Sie das Exchange um-Integrationsprogramm ausführen:
> <ul>
> <li><p>Erstellen Sie einen oder mehrere Exchange um Wählpläne, wie in der Exchange-Produktdokumentation beschrieben.</p>
> <p>Informationen zum Microsoft Exchange Server 2010 finden Sie unter &quot; Erstellen eines um-Wähl Plans &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</p>
> <p>Informationen zum Microsoft Exchange Server 2007 Service Pack 1 (SP1) finden Sie unter &quot; Erstellen eines Unified Messaging-SIP-URI-Wähl Plans unter &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</p></li>
> <li><p>Erstellen Sie einen oder mehrere entsprechende lync Server Wählpläne, wie unter <a href="lync-server-2013-create-a-dial-plan.md">Create a Dial Plan in lync Server 2013</a>beschrieben.</p></li>
> <ul><li>Wenn Sie eine Version von Exchange verwenden, die älter als Microsoft Exchange Server 2010 SP1 ist, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der entsprechenden Exchange Unified Messaging (um) SIP-Wähleinstellungen in das Feld <STRONG>einfacher Name</STRONG> von lync Server 2013 Wähleinstellungen eingeben. Wenn Sie Microsoft Exchange Server 2010 SP1 oder das neueste Service Pack verwenden, ist diese Wähl Plan Namen Übereinstimmung nicht erforderlich.</li></ul>
> <li>Erstellen Sie eine automatische Telefonzentrale, und stellen Sie sicher, dass sowohl die Teilnehmerzugriffsnummer als auch die Nummer der automatischen Telefonzentrale im E. 164-Format vorliegen.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>So führen Sie das Exchange um-Integrations Dienstprogramm aus

1.  Öffnen Sie auf einem Front-End-Server eine Eingabeaufforderung, und geben Sie **CD% COMMONPROGRAMFILES% \\ Microsoft lync Server 2013 \\ Support**ein, und drücken Sie dann die EINGABETASTE.

2.  Geben Sie **OcsUmUtil.exe**ein, und drücken Sie dann die EINGABETASTE.

3.  Klicken Sie auf **Daten laden** , um alle vertrauenswürdigen Exchange-Gesamtstrukturen zu finden.

4.  Wählen Sie in der Liste **SIP Dial** Plans einen um-SIP-Wählplan aus, für den Sie Kontaktobjekte erstellen möchten, und klicken Sie dann auf **Hinzufügen**.

5.  Akzeptieren Sie im Feld **Kontakt** die Standardorganisationseinheit, oder klicken Sie auf **Durchsuchen** , um die **OU-Auswahl**zu starten. Wählen Sie im Feld **Organisationseinheiten Auswahl** eine Organisationseinheit aus, und klicken Sie auf **OK**, oder klicken Sie auf **neue OU** erstellen, um eine neue Organisationseinheit unter dem Stamm oder einer anderen ou in der Domäne zu erstellen (beispielsweise "ou = RTC Special Accounts, DC = FourthCoffee, DC = com"), und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Der Distinguished Name (DN) der Organisationseinheit, die Sie ausgewählt oder erstellt haben, wird jetzt im Feld <STRONG>Organisationseinheit</STRONG> angezeigt.

    
    </div>

6.  Akzeptieren Sie im Feld **Name** entweder den Standardnamen für den Wählplan, oder geben Sie einen neuen Anzeigenamen für das Kontaktobjekt ein, das Sie erstellen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie beispielsweise ein Kontaktobjekt für den Teilnehmerzugriff erstellen, nennen Sie es möglicherweise einfach Teilnehmerzugriff.

    
    </div>

7.  Akzeptieren Sie im Feld **SIP-Adresse** entweder die Standard-SIP-Adresse, oder geben Sie eine neue SIP-Adresse ein.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine neue SIP-Adresse eingeben, muss Sie mit <STRONG>SIP beginnen:</STRONG> (also "SIP:" einschließlich des Doppelpunkts).

    
    </div>

8.  Wählen Sie in der Liste **Server oder Pool** die Standard Edition-Server oder Front-End-Pool aus, in der das Kontaktobjekt aktiviert werden soll.
    
    <div>
    

    > [!NOTE]  
    > Vorzugsweise ist der ausgewählte Pool derselbe Pool, in dem Benutzer, die für Enterprise-VoIP und Exchange um aktiviert sind, bereitgestellt werden.

    
    </div>

9.  Wählen Sie in der Liste **Telefonnummer** entweder die Option **Telefonnummer eingeben** oder **diese Pilotnummer aus Exchange um aus** , und geben Sie dann eine Telefonnummer ein.

10. Wählen Sie in der Liste **Kontakttyp** den Kontakttyp aus, den Sie erstellen möchten, und klicken Sie dann auf **OK**.

11. Wiederholen Sie die Schritte 1 bis 10 für weitere Kontaktobjekte, die Sie erstellen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie sollten für jede automatische Telefonzentrale mindestens einen Kontakt erstellen. Wenn Sie externen Zugriff wünschen, benötigen Sie auch einen Teilnehmerzugriffs Kontakt und geben direkte Inward-Wähl Nummern an.

    
    </div>

</div>

Um zu überprüfen, ob die Kontaktobjekte erstellt wurden, öffnen Sie Active Directory Benutzer und Computer, und wählen Sie die Organisationseinheit aus, in der die Objekte erstellt wurden. Die Kontaktobjekte sollten im Detailbereich angezeigt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

