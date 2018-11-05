---
title: Bereitstellen eines Lync Server 2013-Pilotpools
TOCTitle: Bereitstellen eines Lync Server 2013-Pilotpools
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205144(v=OCS.15)
ms:contentKeyID: 49295017
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen eines Lync Server 2013-Pilotpools

 

_**Letztes Änderungsdatum des Themas:** 2013-11-22_

Einer der ersten Schritte, die für die Migration zu Lync Server 2013 erforderlich sind, umfasst das Bereitstellen eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Lync Server 2013 mit Ihrer Lync Server 2010-Bereitstellung. Bei der Koexistenz handelt es sich um einen vorübergehenden Zustand, der so lange andauert, bis Sie alle Benutzer und Pools nach Lync Server 2013 verschoben haben.

Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten dieselben Funktionen und Arbeitslasten in Ihrem Lync Server 2013-Pilotpool bereitstellen, die bereits in Ihrem Lync Server 2010-Pool vorhanden sind. Wenn Sie den Archivierungsserver, Monitoring-Server oder System Center Operations Manager zum Archivieren oder Überwachen der Lync Server 2010-Umgebung bereitgestellt haben und Sie die Archivierung oder Überwachung in der Migration fortsetzen möchten, müssen Sie diese Funktionen auch in der Pilotumgebung bereitstellen. Mit der Version, die sie zum Archivieren oder Überwachen der Lync Server 2010-Umgebung bereitgestellt haben, werden die Daten in der Lync Server 2013-Umgebung nicht erfasst.


> [!NOTE]
> Im nachfolgenden Verfahren werden Funktionen und Einstellungen erläutert, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für den Pilotpool berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Schritte finden Sie im Bereitstellungshandbuch für <A href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server&nbsp;2013</A>.



**So stellen Sie einen Lync Server 2013-Pilotpool bereit**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Erweitern Sie die Struktur, bis Sie zu den **Enterprise Edition-Front-End-Pools** von **Lync Server 2013** gelangen.

3.  Klicken Sie mit der rechten Maustaste auf **Enterprise Edition-Front-End-Pools** , und wählen Sie die Option **Neuer Front-End-Pool** aus.
    
    ![Topologie-Generator – Serverpoolauswahl (Untermenü)](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topologie-Generator – Serverpoolauswahl (Untermenü)")

4.  Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool ein. Beim Definieren Ihres Pilotpools können Sie die Bereitstellung eines Enterprise Edition- Front-End-Pools oder eines Standard Edition-Servers festlegen. Für Lync Server 2013 müssen die Features Ihres Pilotpools nicht mit der Bereitstellung im Legacypool übereinstimmen.
    

    > [!WARNING]
    > Der FQDN des Pools oder Servers, den Sie für die Pilotbereitstellung definieren, muss eindeutig sein. Er darf nicht mit dem Namen des derzeit bereitgestellten Lync Server 2010-Pools oder eines anderen derzeit bereitgestellten Servers übereinstimmen.

    
    ![Definieren von FQDN in Assistent für neuen Front-End-Pool (Seite)](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Definieren von FQDN in Assistent für neuen Front-End-Pool (Seite)")

5.  Aktivieren Sie auf der Seite **Funktionen auswählen** die Kontrollkästchen für die gewünschten Funktionen dieses Front-End-Pools. Wenn Sie beispielsweise nur Funktionen für Chat und Anwesenheit bereitstellen, aktivieren Sie das Kontrollkätchen „Konferenzen“, um Chatnachrichten mit mehreren Teilnnehmern zuzulassen. Sie würden in diesem Fall jedoch nicht die Kontrollkästchen "Einwahlkonferenzen (PSTN)", "Enterprise-VoIP" oder "Anrufsteuerung" aktivieren, da sich diese auf VoIP-, Video- und Zusammenarbeitskonferenzfunktionen beziehen. Weitere Informationen zum Auswählen von Funktionen finden Sie unter [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.
    
    ![Front-End-Pool – Auswählen von Funktionen (Seite)](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool – Auswählen von Funktionen (Seite)")

6.  Wir empfehlen, auf der Seite **Verbundene Serverrollen auswählen** den Vermittlungsserver mit Lync Server 2013 zu verbinden. Beim Zusammenführen einer Topologie der Vorversion mit Lync Server 2013 muss zuerst der Lync Server 2010- Vermittlungsserver verbunden werden. Nach dem Zusammenführen der Topologien und dem Konfigurieren des Lync Server 2013- Vermittlungsserver können Sie entscheiden, ob Sie den verbundenen Vermittlungsserver, beibehalten oder ihn in einen eigenständigen Server umwandeln, wenn Sie die Vermittlungsserver-Rolle später im Bereitstellungsprozess an Lync Server 2013 verschieben.
    
    ![Front-End-Pool – Auswählen verbundener Serverrollen (Seite)](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool – Auswählen verbundener Serverrollen (Seite)")

7.  Wählen Sie während der Bereitstellung des Pilotpools auf der Seite **Serverrollen diesem Front-End-Pool zuordnen** nicht die Option **Edgepool zur Verwendung durch die Medienkomponente dieses Front-End-Pools auswählen** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert.
    
    ![Zuordnen von Serverrollen zu Front-End-Server (Seite)](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Zuordnen von Serverrollen zu Front-End-Server (Seite)")

8.  Klicken Sie auf der Seite **Server für Office Web Apps auswählen** auf **Neu** , und geben Sie den FQDN des Anwendungsservers an.
    
    ![Definieren von FQDN für neuen Office Online-Server, Eigenschaften](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren von FQDN für neuen Office Online-Server, Eigenschaften")

9.  Wählen Sie auf der Seite **SQL Server-Speicher für Archivierung definieren** beim Definieren des SQL Server-Speichers für die Lync Server-Archivierung und -Überwachung die SQL Server-Instanz aus, die sie zuvor für Lync Server 2013 erstellt haben.
    
    ![Definieren der Archivierung für SQL Server-Speicher (Seite)](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definieren der Archivierung für SQL Server-Speicher (Seite)")

10. Klicken Sie zum Veröffentlichen der Topologie mit der rechten Maustaste auf den Knoten **Lync Server**, und klicken Sie dann auf **Topologie veröffentlichen** .
    
    ![Topologie-Generator mit einer konfigurierten Topologie](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topologie-Generator mit einer konfigurierten Topologie")

11. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen** .

Informationen zur Installation einer lokalen Kopie des Konfigurationsspeichers und zum Starten der erforderlichen Dienste finden Sie unter [Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.


