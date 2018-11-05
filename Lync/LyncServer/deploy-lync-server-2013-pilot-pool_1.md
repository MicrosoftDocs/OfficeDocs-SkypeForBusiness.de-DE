---
title: Bereitstellen des Lync Server 2013-Pilotpools
TOCTitle: Bereitstellen des Lync Server 2013-Pilotpools
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204718(v=OCS.15)
ms:contentKeyID: 49293328
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen des Lync Server 2013-Pilotpools

 

_**Letztes Änderungsdatum des Themas:** 2013-11-22_

Einer der ersten Schritte, die für die Migration zu Lync Server 2013 erforderlich sind, umfasst das Bereitstellen eines Pilotpools. Im Pilotpool testen Sie die Koexistenz von Lync Server 2013 mit Ihrer Office Communications Server 2007 R2-Bereitstellung. Bei der Koexistenz handelt es sich um einen vorübergehenden Zustand, der so lange andauert, bis Sie alle Benutzer und Pools nach Lync Server 2013 verschoben haben.

Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools. Sie sollten in Ihrem Lync Server 2013-Pilotpool dieselben Funktionen und Arbeitsauslastungen bereitstellen wie in Ihrem Office Communications Server 2007 R2-Pool. Wenn Sie den Archivierungsserver, Monitoring Server oder System Center Operations Manager für die Archivierung oder Überwachung Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben und die Archivierung und Überwachung während der Migration fortsetzen möchten, müssen Sie diese Funktionen auch in Ihrer Pilotumgebung bereitstellen. Die von Ihnen bereitgestellte Version zur Archivierung und Überwachung der Office Communications Server 2007 R2-Umgebung erfasst keine Daten in der Lync Server 2013-Umgebung.


> [!NOTE]
> Im nachfolgenden Verfahren werden Funktionen und Einstellungen erläutert, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für den Pilotpool berücksichtigen sollten. In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben. Ausführliche Schritte finden Sie im Bereitstellungshandbuch für <A href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server&nbsp;2013</A>.



**So stellen Sie einen Lync Server 2013-Pilotpool bereit**

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Öffnen Sie den Topologie-Generator, und wählen Sie die Option zur Erstellung einer neuen Topologie aus.

3.  Geben Sie die primäre SIP-Domäne ein.
    
    ![Neue Topologie erstellen, primäre Domäne definieren (Seite)](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Neue Topologie erstellen, primäre Domäne definieren (Seite)")

4.  Fahren Sie mit der Fertigstellung des Assistenten fort, bis Sie zum Assistenten zum **Definieren eines neuen Front-End-Pools** gelangen. Klicken Sie auf "Weiter".

5.  Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool ein. Beim Definieren Ihres Pilotpools können Sie die Bereitstellung eines Enterprise Edition- Front-End-Pools oder eines Standard Edition-Servers festlegen. Für Lync Server 2013 müssen die Features Ihres Pilotpools nicht mit der Bereitstellung im Legacypool übereinstimmen.
    

    > [!WARNING]
    > Der FQDN des Pools oder Servers, den Sie für die Pilotbereitstellung definieren, muss eindeutig sein. Er darf nicht mit dem Namen des derzeit bereitgestellten Office Communications Server 2007 R2-Pools oder eines anderen derzeit bereitgestellten Servers übereinstimmen.

    
    ![FQDN für Front-End-Pool definieren (Seite)](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "FQDN für Front-End-Pool definieren (Seite)")

6.  Legen Sie den Computer fest, der dem Pool hinzugefügt wird.
    
    ![Neuen Front-End-Pool definieren (Dialogfeld)](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Neuen Front-End-Pool definieren (Dialogfeld)")

7.  Aktivieren Sie auf der Seite **Funktionen auswählen** die Kontrollkästchen für die gewünschten Funktionen dieses Front-End-Pools. Wenn Sie beispielsweise nur Funktionen für Chat und Anwesenheit bereitstellen, aktivieren Sie das Kontrollkätchen „Konferenzen“, um Chatnachrichten mit mehreren Teilnnehmern zuzulassen. Sie würden in diesem Fall jedoch nicht die Kontrollkästchen "Einwahlkonferenzen (PSTN)", "Enterprise-VoIP" oder "Anrufsteuerung" aktivieren, da sich diese auf VoIP-, Video- und Zusammenarbeitskonferenzfunktionen beziehen. Weitere Informationen zum Auswählen von Funktionen finden Sie unter [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.
    
    ![Front-End-Pool – Auswählen von Funktionen (Seite)](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool – Auswählen von Funktionen (Seite)")

8.  Wir empfehlen, auf der Seite **Verbundene Serverrollen auswählen** den Vermittlungsserver mit Lync Server 2013 zu verbinden. Beim Zusammenführen einer Topologie der Vorversion mit Lync Server 2013 muss zuerst der Office Communications Server 2007 R2- Vermittlungsserver verbunden werden. Nach dem Zusammenführen der Topologien und dem Konfigurieren des Lync Server 2013- Vermittlungsserver können Sie entscheiden, ob Sie den verbundenen Vermittlungsserver, beibehalten oder ihn in einen eigenständigen Server umwandeln, wenn Sie die Vermittlungsserver-Rolle später im Bereitstellungsprozess an Lync Server 2013 verschieben.
    
    ![Front-End-Pool – Auswählen verbundener Serverrollen (Seite)](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool – Auswählen verbundener Serverrollen (Seite)")

9.  Wählen Sie während der Bereitstellung des Pilotpools auf der Seite **Serverrollen diesem Front-End-Pool zuordnen** nicht die Option **Edgepool zur Verwendung durch die Medienkomponente dieses Front-End-Pools auswählen** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert.
    
    ![Zuordnen von Serverrollen zu Front-End-Server (Seite)](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Zuordnen von Serverrollen zu Front-End-Server (Seite)")

10. Klicken Sie auf der Seite **Server für Office Web Apps auswählen** auf **Neu** , und geben Sie den FQDN des Anwendungsservers an.
    
    ![Definieren von FQDN für neuen Office Online-Server, Eigenschaften](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren von FQDN für neuen Office Online-Server, Eigenschaften")

11. Wählen Sie auf der Seite **SQL Server-Archivierungsspeicher definieren** die zuvor für Lync Server 2013 erstellte SQL Server-Instanz aus.
    
    ![Definieren der Archivierung für SQL Server-Speicher (Seite)](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definieren der Archivierung für SQL Server-Speicher (Seite)")

12. Wählen Sie auf der Seite **SQL Server-Überwachungsspeicher definieren** die zuvor für Lync Server 2013 erstellte SQL Server-Instanz aus. Klicken Sie auf **Fertig stellen**.

13. Klicken Sie im obersten Knoten des Topologie-Generators mit der rechten Maustaste auf **Lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten.** Klicken Sie auf **Einfache URLs**.

14. Aktualisieren Sie die **URL für administrativen Zugriff**.
    
    ![Eigenschaften bearbeiten, einfache URLs (Seite)](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Eigenschaften bearbeiten, einfache URLs (Seite)")
    
    Weitere Informationen zu einfachen URLs finden Sie in der Bereitstellungsdokumentation unter [Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md).

15. Klicken Sie unter **Eigenschaften bearbeiten** auf **Zentraler Verwaltungsserver**.

16. Wählen Sie in der Dropdownliste den Lync Server 2013-Pool aus.
    
    ![Eigenschaften bearbeiten, zentraler Verwaltungsserver (Seite)](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Eigenschaften bearbeiten, zentraler Verwaltungsserver (Seite)")

17. Klicken Sie auf "OK" um die Seite **Eigenschaften bearbeiten** zu schließen.

18. Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus.

19. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen** .

20. Kehren Sie zum Lync Server 2013-Bereitstellungs-Assistenten zurück, und klicken Sie auf **Lync Server-System installieren oder aktualisieren**.
    
    ![Lync Server 2013-Bereitstellungs-Assistent](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013-Bereitstellungs-Assistent")

Informationen zur Installation einer lokalen Kopie des Konfigurationsspeichers und zum Starten der erforderlichen Dienste finden Sie unter [Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.


