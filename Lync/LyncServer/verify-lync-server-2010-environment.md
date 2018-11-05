---
title: Überprüfen der Lync Server 2010-Umgebung
TOCTitle: Überprüfen der Lync Server 2010-Umgebung
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205231(v=OCS.15)
ms:contentKeyID: 49295278
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Lync Server 2010-Umgebung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Vor der Bereitstellung von Lync Server 2013 zusammen mit Lync Server 2010 müssen Sie überprüfen, ob Lync Server 2010-Dienste konfiguriert und gestartet wurden. Wichtige Dienste und Features in Ihrer Vorversionsumgebung müssen unbedingt identifiziert werden, bevor Sie einen Lync Server 2013-Pilotpool bereitstellen. Vor der Bereitstellung von Microsoft Lync Server 2013 XMPP zusammen mit einer XMPP-Vorversionsbereitstellung müssen Sie überprüfen, ob die XMPP-Vorversionsdienste konfiguriert und gestartet wurden, sowie feststellen, welcher Verbundpartner von der XMPP-Vorversionskonfiguration unterstützt wird. Die Überprüfung der Lync Server 2010-Vorversionsbereitstellung beinhaltet Folgendes:

  - Überprüfen, ob die Lync Server 2010-Dienste gestartet sind

  - Überprüfen der Topologie und der Benutzer in Lync Server 2010

  - Überprüfen der Partnerverbund- und Edgeservereinstellungen

  - Überprüfen der XMPP-Dienste und Verbundpartner

**Überprüfen, ob die Lync Server 2010-Dienste gestartet sind**

1.  Navigieren Sie auf dem Lync Server 2010-Front-End-Server zum Applet **Dienste** in **Verwaltung** .

2.  Stellen Sie sicher, dass auf dem Front-End-Server die folgenden Dienste ausgeführt werden:
    
    ![Liste der Dienste, die auf Front-End-Server ausgeführt werden](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste der Dienste, die auf Front-End-Server ausgeführt werden")

**Überprüfen der Lync Server 2010-Topologie in der Lync Server-Systemsteuerung**

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Wählen Sie **Topologie** aus. Überprüfen Sie, ob die verschiedenen Server in Ihrer Lync Server 2010-Bereitstellung aufgeführt werden.
    
    ![Lync Server 2010-Systemsteuerung – Topologie (Seite)](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010-Systemsteuerung – Topologie (Seite)")

**So überprüfen Sie Lync Server 2010-Benutzer in der Lync Server-Systemsteuerung**

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Wählen Sie **Benutzer** aus, und klicken Sie dann auf **Suchen** .

3.  Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** für jeden aufgeführten Benutzer auf den Lync Server 2010-Pool verweist.
    
    ![Lync Server 2010-Systemsteuerung mit Auflistung von Benutzern](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010-Systemsteuerung mit Auflistung von Benutzern")

**So überprüfen Sie die Edge- und Partnerverbundeinstellungen für Lync Server 2010**

1.  Starten Sie den Topologie-Generator.

2.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen** aus.

3.  Wählen Sie einen Dateinamen aus, und speichern Sie die Topologie als standardmäßigen TBXML-Dateityp.

4.  Erweitern Sie den Lync Server 2010-Knoten, um die verschiedenen Serverrollen in der Bereitstellung anzuzeigen.

5.  Wählen Sie den Knoten Standort aus, und überprüfen Sie, ob ein Wert für **Zuweisung der Partnerverbundroute des Standorts** festgelegt ist.
    
    ![Topologie-Generator: Partnerverbundroute des Standorts](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topologie-Generator: Partnerverbundroute des Standorts")

6.  Wählen Sie anschließend den Standard Edition Server- oder Enterprise Edition-Front-End-Pool aus. Bestimmen Sie, ob unter **Zuordnungen** ein Edgepool für Medien konfiguriert wurde.
    
    ![Topologie-Generator mit Servern und Pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topologie-Generator mit Servern und Pools")

7.  Wählen Sie schließlich den Edgepool aus, und identifizieren Sie, ob für **Auswahl für nächsten Hop** ein nächster Hoppool konfiguriert ist.
    
    ![Topologie-Generator, nächsten Hop auswählen](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topologie-Generator, nächsten Hop auswählen")

**Überprüfen der XMPP-Verbundpartnerkonfiguration der Vorversion**

1.  Navigieren Sie auf dem XMPP-Vorversionsserver zum Applet Verwaltungstools\\Dienste .

2.  Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.
    
    ![Office Communications Server: XMPP-Gatewaydienst](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server: XMPP-Gatewaydienst")

