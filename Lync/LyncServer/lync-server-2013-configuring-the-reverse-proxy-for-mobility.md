---
title: 'Lync Server 2013: Konfigurieren des Reverseproxys für Mobilität'
TOCTitle: Konfigurieren des Reverseproxys für Mobilität
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690011(v=OCS.15)
ms:contentKeyID: 49293784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-20_

Wenn Sie die AutoErmittlung für die Clients mobiler Geräte verwenden möchten, müssen Sie eine neue Webveröffentlichungsregel für den Reverseproxy erstellen oder eine vorhandene bearbeiten, ganz gleich, ob Sie die Listen der alternativen Antragstellernamen für die Reverseproxyzertifikate aktualisieren oder nicht.

Wenn Sie HTTPS für anfängliche Lync Server 2013-AutoErmittlungsdienst-Anforderungen verwenden und die Listen der alternativen Antragstellernamen für die Reverseproxyzertifikate aktualisieren möchten, müssen Sie das aktualisierte öffentliche Zertifikat dem SSL-Listener (Secure Sockets Layer) auf dem Reverseproxy zuweisen. Ausführliche Informationen zu den erforderlichen Einträgen für die alternativen Antragstellernamen finden Sie unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Dann müssen Sie den bestehenden Listener für die externen Webdienste bearbeiten oder eine neue Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erstellen. Wenn Sie nicht bereits eine Webveröffentlichungsregel für die externe Lync Server 2013-Webdienste-URL für den Front-End-Pool haben, müssen Sie auch dafür eine Regel veröffentlichen.


> [!NOTE]
> Die Veröffentlichungsregel und der Listener für Reverseproxys können sowohl für die externen Webdienste als auch für den AutoErmittlungsdienst gelten, solange das dem Listener zugewiesene Zertifikat jeweils den erforderlichen Antragstellernamen und den alternativen Antragstellernamen für beides enthält. Ausführliche Informationen zur Standardkonfiguration des Weblisteners und die Veröffentlichungsregel finden Sie unter <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverseproxyservern für Lync Server 2013</A>.



Wenn Sie HTTP für die anfänglichen AutoErmittlungsdienst-Anforderungen verwenden möchten, damit die alternativen Antragstellernamen für den Reverseproxy nicht aktualisiert werden müssen, müssen Sie eine Webveröffentlichungsregel für Port 80 erstellen oder bearbeiten.

Die Vorgehensweisen in diesem Abschnitt beschreiben, wie die neuen Webveröffentlichungsregeln in Microsoft Forefront Threat Management Gateway 2010 für die automatische Ermittlung erstellt oder bearbeitet werden können.


> [!NOTE]
> Bei diesen Vorgehensweisen wird vorausgesetzt, dass die Standard Edition von Forefront Threat Management Gateway (TMG) 2010 installiert ist. Wenn Sie einen anderen Reverseproxy verwenden, sind die Vorgänge ähnlich, müssen jedoch der Dokumentation für das Drittanbieterprodukt zugeordnet werden.



## So erstellen Sie eine Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL

1.  Klicken Sie auf **Start** , zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG** . Klicken Sie auf **Forefront TMG-Verwaltung** .

2.  Erweitern Sie im linken Bereich **ServerName** , klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie** , zeigen Sie auf **Neu** und klicken Sie dann auf **Website-Veröffentlichungsregel** .

3.  Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "LyncErmittlungURL").

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** .

7.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** unter **Interner Sitename** den vollqualifizierten Domänennamen (FQDN) für den Directorpool (zum Beispiel lyncdir01.contoso.local) ein. Wenn Sie eine Regel für die externe Webdienste-URL auf dem Front-End-Pool erstellen, geben Sie die VIP-Adresse des Hardwaregeräts für den Lastenausgleich (HLB) vor dem Front-End-Pool ein.

8.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Pfad (optional)** als Pfad zu dem zu veröffentlichenden Ordner **/\*** ein, und wählen Sie dann **Ursprünglichen Hostheader anstelle des Standortnamens weiterleiten** aus.

9.  Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:
    
      - Wählen Sie unter **Anforderungen annehmen für:** den Eintrag **Diesen Domänennamen** aus.
    
      - Geben Sie im Feld **Öffentlicher Name** den Namen **lyncdiscover.** *\<sipdomain\>* (die externe AutoErmittlungsdienst-URL) ein. Wenn Sie eine Regel für die externe Webdienste-URL im Front-End-Poolerstellen, geben Sie den externen Webdienste-FQDN im Front-End-Pool ein (z. B. "lyncwebextpool01.contoso.com").
    
      - Geben Sie im Feld **Pfad** **/\*** ein.

10. Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** den vorhandenen SSL-Listener mit dem aktualisierten öffentlichen Zertifikat aus.

11. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, aber direkte Authentifizierung des Clients** .

12. Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.

13. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel und klicken Sie dann auf **Fertig stellen** .

14. Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.

15. Führen Sie auf der Registerkarte **An** die folgenden Schritte aus:
    
      - Wählen Sie **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** aus.
    
      - Wählen Sie **Ursprung der Anforderungen scheint der Forefront TMG-Computer zu sein** aus.

16. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver** aus.
    
      - Wählen Sie **Anforderungen an HTTP-Port umleiten** aus und geben Sie als Portnummer **8080** ein.
    
      - Wählen Sie **Anforderungen an SSL-Port umleiten** aus und geben Sie als Portnummer **4443** ein.

17. Klicken Sie auf **OK** .

18. Klicken Sie im Detailbereich auf **Übernehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

19. Klicken Sie auf **Regel testen** , um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

## So bearbeiten Sie eine bestehende Webveröffentlichungsregel zum Hinzufügen des externen AutoErmittlungsdienst-SAN und der -URL

1.  Klicken Sie auf **Start** , zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG** . Klicken Sie auf **Forefront TMG-Verwaltung** .
    

    > [!IMPORTANT]
    > Sie müssen die Bearbeitung für jede Veröffentlichungsregel und jeden Listener wiederholen. Typischerweise handelt es sich dabei um jeweils eine Regel und einen Listener für die Front-End-Pools sowie für die optionalen Directors- oder Director-Pools, falls Sie diese bereitgestellt haben.



2.  Erweitern Sie im linken Bereich **ServerName** , klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie** , und klicken Sie auf die entsprechende Regel. Klicken Sie auf der Registerkarte **Aufgaben** auf **Ausgewählte Regel bearbeiten** .

3.  Wählen Sie auf der Registerkarte **Öffentlicher Name** unter **Regel gilt für** den Eintrag **Anforderungen für die folgenden Websites** aus.

4.  Klicken Sie auf **Hinzufügen** , geben Sie den Namen des neuen AutoErmittlungs-Standorts ein (beispielsweise "lyncdiscover.contoso.com") und klicken Sie auf **OK** .

5.  Klicken Sie auf der Registerkarte **Listener** auf **Zertifikat auswählen** , und weisen Sie den hinzugefügten AutoErmittlungs-SAN-Einträgen das neue Zertifikat zu. Schließen Sie die Listener- und Webveröffentlichungs-Eigenschaften.

6.  Klicken Sie im Detailbereich auf **Übernehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

7.  Klicken Sie auf **Regel testen** , um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

## So erstellen Sie eine Webveröffentlichungsregel für Port 80

1.  Klicken Sie auf **Start** , zeigen Sie auf **Programme** und dann auf **Microsoft Forefront TMG** . Klicken Sie auf **Forefront TMG-Verwaltung** .

2.  Erweitern Sie im linken Bereich **ServerName** , klicken Sie mit der rechten Maustaste auf **Firewallrichtlinie** , zeigen Sie auf **Neu** und klicken Sie dann auf **Website-Veröffentlichungsregel** .

3.  Geben Sie auf der Seite **Willkommen** einen Anzeigenamen für die neue Veröffentlichungsregel ein (z. B. "Lync AutoErmittlung (HTTP)").

4.  Wählen Sie auf der Seite **Regelaktion auswählen** die Option **Zulassen** aus.

5.  Wählen Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** aus.

6.  Wählen Sie auf der Seite **Sicherheit der Serververbindung** die Option **Nicht sichere Verbindungen verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** aus.

7.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** unter **Interner Sitename** die VIP-Adresse des Hardwaregeräts für den Lastenausgleich (HLB) vor dem Front-End-Pool ein.

8.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Pfad (optional)** als Pfad zu dem zu veröffentlichenden Ordner **/\*** ein, und wählen Sie dann **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten, der im Feld für den internen Sitenamen angegeben ist** aus.

9.  Führen Sie auf der Seite **Details des öffentlichen Namens** folgende Schritte aus:
    
      - Wählen Sie unter **Anforderungen annehmen für:** den Eintrag **Diesen Domänennamen** aus.
    
      - Geben Sie im Feld **Öffentlicher Name** den Namen **lyncdiscover.** *\<sipdomain\>* (die externe AutoErmittlungsdienst-URL) ein.
    
      - Geben Sie im Feld **Pfad** **/\*** ein.

10. Wählen Sie auf der Seite **Weblistener auswählen** im Feld **Weblistener** einen Weblistener aus, oder erstellen Sie mit dem Assistenten für neue Weblistenerdefinition einen neuen Weblistener.

11. Klicken Sie auf der Seite **Authentifizierungsdelegierung** auf **Keine Delegierung, keine direkte Authentifizierung des Clients** .

12. Wählen Sie auf der Seite **Benutzersatz** die Option **Alle Benutzer** aus.

13. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Einstellungen für die Webveröffentlichungsregel und klicken Sie dann auf **Fertig stellen** .

14. Doppelklicken Sie in der Forefront TMG-Liste der Webveröffentlichungsregeln auf die neue Regel, die Sie soeben hinzugefügt haben, um **Eigenschaften** zu öffnen.

15. Konfigurieren Sie auf der Registerkarte **Bridging** Folgendes:
    
      - Wählen Sie **Webserver** aus.
    
      - Wählen Sie **Anforderungen an HTTP-Port umleiten** aus und geben Sie als Portnummer **8080** ein.
    
      - Stellen Sie sicher, dass **Anforderungen an SSL-Port umleiten** nicht ausgewählt ist.

16. Klicken Sie auf **OK** .

17. Klicken Sie im Detailbereich auf **Übernehmen** , um die Änderungen zu speichern und die Konfiguration zu aktualisieren.

18. Klicken Sie auf **Regel testen** , um zu überprüfen, ob die neue Regel korrekt eingerichtet ist.

19. Stellen Sie sicher, dass die externe AutoErmittlungsdienst-URL für keine andere Webveröffentlichungsregel definiert ist.

## Siehe auch

#### Konzepte

[Einrichten von Reverseproxyservern für Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)

