---
title: 'Lync Server 2013: Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server'
TOCTitle: Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398193(v=OCS.15)
ms:contentKeyID: 49293206
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für diesen Schritt ist das Exchange UM-Integrationsprogramm (OcsUmUtil.exe) erforderlich. Dieses Tool befindet sich in Lync Server 2013 im Ordner "..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support".

## Ausführen des Exchange UM-Integrationsprogramms

Das Exchange UM-Integrationsprogramm muss mit einem Benutzerkonto ausgeführt werden, das die folgenden Voraussetzungen erfüllt:

  - Mitgliedschaft in den Gruppen "RTCUniversalServerAdmins" und "RtcUniversalUserAdmins" (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen)

  - Benutzerrechte innerhalb der Domäne zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit)

Mit dem Exchange UM-Integrationsprogramm werden die folgenden Aufgaben ausgeführt:

  - Erstellen von Kontaktobjekten für alle Telefonzentralen- und Teilnehmerzugriffsnummern, die von Enterprise-VoIP-Benutzern verwendet werden sollen.

  - Überprüfen der Namen aller Enterprise-VoIP-Wählpläne darauf, ob sie mit dem Telefonkontext der zugehörigen UM (Unified Messaging)-Wähleinstellungen übereinstimmen. Dieser Abgleich ist nur erforderlich, wenn der UM-Wählplan auf einer Exchange-Version *vor* Exchange 2010 Service Pack 1 (SP1) ausgeführt wird.

> [!IMPORTANT]  
> Stellen Sie vor der Ausführung des Exchange UM-Integrationsprogramms Folgendes sicher:
> <ul>
> <li><p>Sie haben einen oder mehrere Sätze mit Exchange UM-Wähleinstellungen erstellt, wie beschrieben in der Exchange-Produktdokumentation.</p>
> <p>Informationen zur Vorgehensweise für Microsoft Exchange Server 2010 finden Sie auf der Seite &quot;Erstellen von UM-Wähleinstellungen&quot; unter <a href="http://go.microsoft.com/fwlink/?linkid=186177" class="uri">http://go.microsoft.com/fwlink/?linkid=186177</a>.</p>
> <p>Informationen zur Vorgehensweise für Microsoft Exchange Server 2007 Service Pack 1 (SP1) finden Sie auf der Seite &quot;Erstellen eines SIP-URI-Wählplans für Unified Messaging&quot; unter <a href="http://go.microsoft.com/fwlink/?linkid=185771" class="uri">http://go.microsoft.com/fwlink/?linkid=185771</a>.</p></li>
> <li><p>Sie haben einen oder mehrere entsprechende Lync Server-Wählpläne erstellt, wie unter <a href="lync-server-2013-create-a-dial-plan.md">Erstellen eines Wählplans in Lync Server 2013</a> beschrieben.</p>
>  
   > Wenn Sie eine Exchange-Version vor Microsoft Exchange Server 2010&nbsp;SP1 verwenden, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des zugehörigen Exchange Unified Messaging (UM)-SIP-Wählplans im Feld <STRONG>Einfacher Name</STRONG> des Lync Server 2013-Wählplans eingeben. Wenn Sie Microsoft Exchange Server 2010 mit SP1 oder dem neuesten Service Pack verwenden, ist dieser Namensabgleich für den Wählplan nicht erforderlich.</li>
>
> <li><p>Sie haben eine automatische Telefonzentrale erstellt und sich vergewissert, dass die Teilnehmerzugriffsnummer und die Nummer der automatischen Telefonzentrale im E.164-Format vorliegen.</p></li>
> </ul>


## So führen Sie das Exchange UM-Integrationsprogramm aus

1.  Öffnen Sie auf einem Front-End-Server eine Eingabeaufforderung, geben Sie folgenden Befehl ein: **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support** , und drücken Sie dann die EINGABETASTE.

2.  Geben Sie **OcsUmUtil.exe** ein, und drücken Sie die EINGABETASTE.

3.  Klicken Sie auf **Daten laden** , um alle vertrauenswürdigen Exchange-Gesamtstrukturen aufzulisten.

4.  Wählen Sie in der Liste **SIP-Wähleinstellungen** die UM-SIP-Wähleinstellungen aus, für die Sie Kontaktobjekte erstellen möchten, und klicken Sie dann auf **Hinzufügen** .

5.  Akzeptieren Sie entweder die Standardorganisationseinheit im Feld **Kontakt** , oder klicken Sie auf **Durchsuchen** , um die Option **Auswahl der Organisationseinheit** zu starten. Im Feld **Auswahl der Organisationseinheit** können Sie eine Organisationseinheit auswählen und auf **OK** klicken, oder Sie können auf **Neue Organisationseinheit erstellen** klicken, um unter dem Stamm oder einer anderen Organisationseinheit in der Domäne eine neue Organisationseinheit anzulegen (z. B. "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"). Klicken Sie anschließend auf **OK** .
    

    > [!NOTE]
    > Der Distinguished Name (DN) der von Ihnen ausgewählten bzw. erstellten Organisationseinheit wird jetzt im Feld <STRONG>Organisationseinheit</STRONG> angezeigt.



6.  Übernehmen Sie entweder den im Feld **Name** angezeigten Standardnamen für die Wähleinstellungen, oder geben Sie einen neuen Anzeigenamen für das zu erstellende Kontaktobjekt ein.
    

    > [!NOTE]
    > Wenn Sie ein Kontaktobjekt für den Teilnehmerzugriff erstellen, können Sie es z.&nbsp;B. einfach "Teilnehmerzugriff" nennen.



7.  Übernehmen Sie im Feld **SIP-Adresse** entweder die Standard-SIP-Adresse, oder geben Sie eine neue Adresse ein.
    

    > [!NOTE]
    > Wenn Sie eine neue SIP-Adresse eingeben, muss diese mit <STRONG>SIP:</STRONG> beginnen (d.&nbsp;h. "SIP:" einschließlich Doppelpunkt).



8.  Wählen Sie in der Liste **Server oder Pool** den Standard Edition-Server oder Front-End-Pool aus, in dem das Kontaktobjekt aktiviert werden soll.
    

    > [!NOTE]
    > Bei dem ausgewählten Pool sollte es sich vorzugsweise um den Pool mit den für Enterprise-VoIP und Exchange UM aktivierten Benutzern handeln.



9.  Wählen Sie in der Liste **Telefonnummer** entweder die Option **Telefonnummer eingeben** oder **Diese Pilotnummer von Exchange UM verwenden** , und geben Sie eine Telefonnummer ein.

10. Wählen Sie in der Liste **Kontakttyp** den zu erstellenden Kontakttyp aus, und klicken Sie auf **OK** .

11. Wiederholen Sie die Schritte 1 bis 10 für alle weiteren zu erstellenden Kontaktobjekte.
    

    > [!NOTE]
    > Sie sollten für jede automatische Telefonzentrale mindestens einen Kontakt erstellen. Falls Sie den externen Zugriff ermöglichen möchten, benötigen Sie außerdem ein Kontaktobjekt für den Teilnehmerzugriff und DID-Nummern (Direct Inward Dial).



Wenn Sie sich vergewissern möchten, dass die Kontaktobjekte erstellt wurden, öffnen Sie das Snap-In **Active Directory-Benutzer und -Computer** und wählen die OU aus, in der die Objekte erstellt wurden. Die Kontaktobjekte sollten im Detailfenster angezeigt werden.

