---
title: 'Lync Server 2013: Neue Funktionen für Clients'
TOCTitle: Neue Funktionen für Clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204933(v=OCS.15)
ms:contentKeyID: 49294128
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen für Clients in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Microsoft Lync 2013 weist eine neu gestaltete Benutzeroberfläche sowie wichtige neue Funktionen auf. Administratoren finden den Client jetzt im Setupprogramm von Office integriert. Dies sorgt für eine einfachere Bereitstellung von Office und erleichtert die Anpassung von Clients in Ihrer Organisation.


> [!NOTE]
> Eine illustrierte Ansicht der Aktualisierungen der Lync 2013-Benutzeroberfläche finden Sie in "Neuigkeiten in Lync 2013" unter <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.



## Integration in das Setup von Office

Der Lync 2013-Client und das Onlinebesprechungs-Add-In für Lync 2013, das die Verwaltung von Besprechungen im Outlook-Client für Messaging und Collaboration unterstützt, sind jetzt im Setupprogramm von Office 2013 integriert.

In früheren Versionen von Lync und Office Communicator war es möglich, die Installation von Office mithilfe von Windows Installer-Eigenschaften zu kontrollieren und anzupassen. Da Lync 2013 jetzt im Setup von Office integriert ist, können Sie das Setup von Lync 2013 jetzt wie folgt anpassen:

  - Verwenden des Office-Anpassungstools

  - Verwenden der Datei "config.xml" zur Durchführung von Installationsaufgaben

  - Verwenden der Befehlszeilenoptionen für das Setup


> [!NOTE]
> Frühere Versionen von Lync oder von Office Communicator werden vom Setupprogramm von Lync 2013 nicht deinstalliert. Der Lync 2013-Client wird parallel zu anderen Lync- oder Office Communicator-Clients installiert.



Ausführliche Informationen finden Sie unter [Bereitstellen von Lync-Clients](lync-server-2013-deploying-lync-clients.md).

## Bereitstellung von Gruppenrichtlinien

Da Lync 2013 jetzt im Setup von Office integriert ist, werden auch die Einstellungen von Lync-Gruppenrichtlinien auf andere Weise bereitgestellt. In früheren Versionen von Lync und von Office Communicator wurden die Einstellungen für Gruppenrichtlinien mit der Datei "Communicator.adm" definiert. Im Gegensatz dazu verwenden Sie in Lync 2013 nun die administrativen Vorlagendateien (ADMX und ADML) von Lync, die zusammen mit den administrativen Vorlagendateien für die Office-Gruppenrichtlinie bereitgestellt werden.

Ausführliche Informationen finden Sie unter [Gruppenrichtlinieneinstellungen für Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

## Updates für das Planungs-Add-In von Outlook

Der Onlinebesprechungs-Add-In für Lync 2013 ermöglicht das Anpassen von Besprechungseinladungen und stellt darüber hinaus weitere Besprechungsoptionen bereit.

  - Administratoren können die Besprechungseinladungen ihrer Organisation durch Hinzufügen eines Logos, einer Support-URL, einer URL für den rechtlichen Haftungsausschluss oder eines benutzerdefinierten Fußzeilentexts anpassen. Nähere Informationen finden Sie unter [Anpassen des Onlinebesprechungs-Add-Ins](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Neue Teilnehmersteuerelemente ermöglichen Besprechungsorganisatoren das Planen von Konferenzen, in denen die Audio- und Videofunktionen von Teilnehmern standardmäßig stummgeschaltet sind.

## Virtual Desktop Infrastructure-Plug-In

Der Lync 2013-Client unterstützt jetzt Audio- und Videofunktionen in einer VDI-Umgebung (Virtual Desktop Infrastructure). Benutzer können Audio- oder Videogeräte (z. B. ein Headset oder eine Kamera) an den lokalen Computer (z. B. an einen Thin-Client oder einen Computer mit veränderter Bereitstellung) anschließen. Obwohl der Client lokal ausgeführt wird, können Benutzer eine Verbindung mit der virtuellen Maschine herstellen, sich beim Lync 2013-Client anmelden, der auf der virtuellen Maschine ausgeführt wird, und in Echtzeit an der Audio- und Videokommunikation teilnehmen.

  - Geräteintegration für Audio- und Videofunktionen, einschließlich der folgenden:
    
      - Anrufsteuerung mit dem Gerät
    
      - Anwesenheitsintegration auf dem Gerät
    
      - Unterstützung mehrerer HIDs (Human Interface Device, Eingabegeräte)

  - Unterstützung von Standort- und Notrufdiensten

  - Unterstützung für alle Lync-Modalitäten, einschließlich Sofortnachrichten, Audio- und Videofunktionen, Anwendungsfreigaben, Desktopfreigaben, PowerPoint-Freigaben, Whiteboards und Dateiübertragungen.

  - Audio- und Videounterstützung bei Einzel- und Konferenzanrufen

Informationen zur Bereitstellung des VDI-Plug-Ins finden Sie unter [Bereitstellen des Lync VDI-Plug-Ins in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

## Videoerweiterungen

Die Videoerfahrung für Konferenzteilnehmer wurde durch die Einführung neuer Funktionen signifikant verbessert.

  - Dank Gesichtserkennung und des intelligenten Framings kann sich das Videofenster des Teilnehmers an Bewegungen anpassen, und der Benutzer bleibt im Mittelpunkt.

  - High-Definition-Videos werden jetzt in Anrufen mit zwei Teilnehmern und in Konferenzen mit mehreren Teilnehmern mit einer Auflösung bis HD 1080P unterstützt.

  - Teilnehmer können auch unterschiedlichen Besprechungslayouts auswählen: Galerienansicht (zeigt Bilder oder Videos aller Teilnehmer an), Sprecheransicht (zeigt den Besprechungsinhalt und nur das Bild oder Video des aktuellen Sprechers an), Präsentationsansicht (zeigt nur den Besprechungsinhalt an), Kompaktansicht (zeigt nur die Besprechungssteuerelemente an).

  - In der neuen Galerieansicht können Benutzer mehrere Videofeeds gleichzeitig anzeigen. Bei Konferenzen mit mehr als fünf Teilnehmern, werden nur die Videofeeds der aktivsten Teilnehmer in der obersten Zeile angezeigt, die anderen Teilnehmer werden jeweils mit einem Bild angezeigt.

  - Teilnehmer können Videos auch verankern, sodass einer oder mehrere Videofeeds die ganze Zeit über angezeigt werden.

  - Referenten können mithilfe einer Spotlightfunktion den Videofeed einer bestimmten Version auswählen, sodass alle Teilnehmer in der Besprechung nur diesen Teilnehmer sehen.

## Chatroomintegration

Funktionen, die früher von Lync 2010-Gruppenchat bereitgestellt wurden, sind jetzt in Lync 2013 integriert. Ein separater Client für Gruppenchats ist nicht mehr erforderlich.

  - Benutzer können in Lync 2013 nach Chatrooms suchen, ihren Kontakten Chatrooms hinzufügen, Chatroomaktivitäten überwachen und Nachrichten lesen und schreiben.

  - Benutzer können Themenfeeds erstellen, um benachrichtigt zu werden, wenn in einem ihrer Chatrooms ein Beitrag mit bestimmten Stichwörtern veröffentlicht wird.

  - Die neue Seite mit Optionen für den **Beständigen Chat** ermöglicht Benutzern das Festlegen von Benachrichtigungen und akustischen Signalen, wenn andere Benutzer Nachrichten in ihren Chatrooms veröffentlichen.

## Lync Web App-Updates

Lync Web App ist der webbasierte Konferenzclient für Lync Server 2013-Besprechungen. In dieser Version wird durch die Ergänzung der Audio- und Videofunktionen für Computer in Lync Web App eine umfassende Besprechungsfunktionalität angeboten, die von einem lokalen Lync-Client nicht bereitgestellt werden kann. Besprechungsteilnehmer können auf alle Funktionen für die Zusammenarbeit und Freigabe sowie auf alle Besprechungssteuerelemente des Referenten zugreifen.

Wenn ein Benutzer einer Besprechung beitreten möchte, jedoch nicht über einen lokal installierten Client verfügt, wird die Lync Web App geöffnet. Wenn Sie weitere Optionen für den Beitritt zu einer Besprechung zulassen möchten, können Sie die Konfiguration der Seite für den Besprechungsbeitritt bearbeiten. Weitere Informationen finden Sie in der Bereitstellungsdokumentation unter [Konfigurieren der Seite für den Besprechungsbeitritt in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

Aufgrund der Erweiterungen von Lync Web App ist keine aktualisierte Version von Teilnehmer für Lync Server 2013 verfügbar. Teilnehmer außerhalb Ihrer Organisation sollten daher Lync Web App als Client verwenden. Eine lokale Clientinstallation ist nicht erforderlich. Zur Verwendung der Audio-, Video- und Freigabeoptionen muss lediglich ein Plug-In bei der erstmaligen Verwendung installiert werden.

## Lync 2013 für Aktualisierungen mobiler Clients

Neben verbesserten Anwesenheits-, Kontakt- und Chatfunktionen bieten Lync 2013 Mobile-Clients jetzt auch Video- und Sprachanrufe über das Internet und mobile Datenverbindungen. Durch einmaliges Aufrufen des Besprechungslinks in einem Kalenderelement können Benutzer von mobilen Geräten an Lync-VoIP- und Videobesprechungen teilnehmen. Weitere Informationen zu Lync 2013 Mobile-Clients finden Sie unter [Planung für mobile Clients](lync-server-2013-planning-for-mobile-clients.md).

## Updates für die Lync 2013-Benutzeroberfläche

## Updates für die Eingabehilfen

Lync 2013 beinhaltet mehrere neue Funktionen für die Eingabehilfen.

  - Lync 2013 unterstützt eine hohe DPI-Auflösung, sodass Benutzer Texte und Grafiken bis zu 125 % bzw. 150 % des DPI-Werts (Dots Per Inch, Punkte pro Zoll) skalieren können.

  - Lync unterstützt hohe Kontraste, sodass die Benutzeroberfläche auch in Verbindung mit Designs von Windows verwendet werden kann, die über einen hohen Kontrast verfügen, ohne dass es zu Problemen kommt.

  - Mehr als 100 Tastenkombinationen erlauben Benutzern von Lync den Zugriff auf wichtige Funktionen auch ohne Maus. Beispielsweise kann ein Anruf durch Drücken der ALT-TASTE+C angenommen werden, und mit ALT-TASTE+I können Anrufe ignoriert werden, dabei ist es nicht erforderlich die TAB-TASTE zu betätigen oder den Fokus zu ändern. Mit der ALT-TASTE+Q wird ein Anruf beendet, mit der STRG-TASTE+N wird OneNote gestartet, und die ALT-TASTE+T öffnet das Menü "Extras".

  - Die umfassende Unterstützung der Sprachausgabe in Lync 2013 stellt sicher, dass alle Benachrichtigungen, eingehenden Anforderungen sowie alle Sofortnachrichten bei Aktivierung der entsprechenden Option laut vorgelesen werden.

## Anwesenheit bei Freigabe

Wenn Lync erkennt, dass ein Benutzer eine Freigabe aktiviert hat, wird ihm vom Lync automatisch der Anwesenheitsstatus "Präsentation" zugewiesen. Dieser Status blockiert die gesamte eingehende Kommunikation, es sei denn, dem Absender wird der Status "Beschäftigt" zugewiesen. Wenn die Freigabefunktion vom Benutzer ausschließlich auf einem sekundären Monitor verwendet wird, wird der Anwesenheitsstatus "Präsentation" von Lync nicht zugewiesen.

## Updates für das Fenster "Unterhaltung"

Das neu gestaltete Fenster "Unterhaltung" bietet jetzt noch schnelleren Zugriff auf wichtige Funktionen.

  - Dank der neuen Unterhaltungsfunktion mit Registerkarten können Benutzer jetzt alle Sofortnachrichten und Chatrooms in einem Unterhaltungsfenster nutzen. Die Registerkarten werden an der linken Seite des Fensters "Unterhaltung" angezeigt und ermöglichen eine schnelle und bequeme Navigation zwischen allen aktiven Unterhaltungen.

  - Benutzer können eine individuelle Unterhaltung in ein separates Fenster ausgliedern und anschließend die Größe dieses Fensters anpassen. Das Fenster kann außerdem wieder in das Fenster "Unterhaltung" eingegliedert werden.

  - Die Unterhaltungen eines Benutzers werden von Lync 2013 wieder geöffnet, wenn sich der Benutzer abmeldet und dann erneut bei Lync anmeldet.

  - Benutzer können jeder Unterhaltung umgehend Sofortnachrichten, Videos, Programmfreigaben, Desktopfreigaben oder Webkonferenztools (Whiteboards, Besprechungsnotizen, Notizbuchfreigaben und Anlagen) hinzufügen.

  - In einer Besprechung, in der Videos oder Inhalte geteilt werden, können Benutzer die Videos oder Inhalte in ein separates Fenster ausgliedern und die Größe dieses Fensters anpassen.

## Updates für das Hauptfenster von Lync

Der neue und modernisierte Look ermöglicht auch weiterhin den Zugriff auf bekannte Funktionen wie das Feld **Notiz eingeben** , die Statusauswahl und die Auswahl **Standort festlegen** .

  - Wenn Chatrooms aktiviert wurden, wird Benutzern auf der Hauptseite von Lync das neue Symbol **Chatrooms** angezeigt. Über das Symbol **Chatrooms** können Benutzer rasch auf ihre Chatrooms und Filter zugreifen.

  - Durch Klicken auf die Ansichtssymbole können Benutzer zwischen der Ansicht **Kontakte** , der Ansicht **Chatrooms** , der Ansicht **Konversationen** und der Ansicht **Telefon** wechseln.

  - Wenn Benutzer zu Exchange 2013 migriert wurden, können Sie ein hochauflösendes Bild hochladen.

## Updates für die Ansicht "Kontakte" und die Visitenkarte

Lync 2013 bieten Benutzern unterschiedliche Möglichkeiten zum Anzeigen von Kontakten und Gruppen in der Ansicht **Kontakte** .

  - Mithilfe des neuen einheitlichen Kontaktspeichers können Benutzer nach der Migration ihrer Lync-Kontakte zu Exchange 2013 über Lync 2013, Outlook oder Outlook Web App auf Ihre Kontakte zugreifen und diese verwalten. Alle Favoriten bleiben dabei synchronisiert. Angenommen, ein Benutzer fügt seinen Favoriten in Outlook einen Kontakt hinzu. Der Kontakt wird nun in der Gruppe "Favoriten" im Lync 2013 angezeigt.

  - Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzugefügt und konfiguriert haben, können Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten- und Präsenzfunktionen hinzufügen.

  - Mit der neuen Funktion **Kontakt außerhalb der Organisation hinzufügen** können Benutzer auf einfache Weise andere Benutzer außerhalb ihrer Organisation hinzufügen.

  - Die neue Funktion **Favoriten** ermöglicht Benutzern das Erstellen einer Liste von Personen, die am häufigsten von Benutzern kontaktiert werden, um schnell darauf zugreifen zu können.

  - Auf der neuen Optionsseite **Kontaktliste** können Benutzer angeben, wie Benutzer sortiert und angezeigt werden sollen. Zur Auswahl stehen eine erweiterte zweizeilige Ansicht mit Kontaktbildern oder eine kompakte einzeilige Ansicht. Die Liste kann alphabetisch oder nach Verfügbarkeit sortiert werden.

## Updates für Konferenzen

Lync 2013 bietet zahlreiche Verbesserungen für die Konferenzfunktionen.

  - In Abhängigkeit vom Besprechungstyp können Benutzer jetzt das Publikum stummschalten und die Videofreigabe zulassen oder blockieren, wenn sie die Besprechung planen. Diese Optionen sind auf der Seite **Besprechungsoptionen** verfügbar und sollten bei großen Besprechungen ab 20 Personen verwendet werden.

  - Benutzerfreundliche Audiosteuerelemente im Besprechungsraum ermöglichen Benutzern das Kontrollieren der Audiooptionen wie "Stummschalten", "Stummschaltung aufheben" oder "Gerät ändern".

  - Beim Freigeben von Programmen können Benutzer bei Bedarf mehrere Programme für eine Freigabe auswählen.

  - Benutzer können jetzt Präsentationen mit Videoclips hochladen, indem Sie die entsprechende PowerPoint-Datei hochladen und mit der Maus auf die Folie zeigen, um die Videosteuerelemente wie Wiedergabe oder Pause und die Audiosteuerelemente anzuzeigen.

  - Benutzer können aus Besprechungen heraus eine andere geöffnete Unterhaltung mit der Besprechung zusammenführen, indem sie die Option **Diesen Anruf zusammenführen mit** im Menü **Weitere Optionen** ( **…** ) verwenden.

  - Benutzer können mit der Maus auf die Schaltfläche **Teilnehmer anzeigen** zeigen, um die Namen der Teilnehmer anzuzeigen. Benutzer können auch auf **Teilnehmerliste anzeigen** klicken, um den Bereich in der Besprechung zu verankern.

  - In Abhängigkeit vom Besprechungstyp können Benutzer aus mehreren Inhalts- und Teilnehmeransichten auswählen.

  - Besprechungen werden automatisch in einem Format aufgezeichnet, das im Windows Media Player wiedergegeben werden kann (MP4). Aufgezeichnete Dateien können auf einfache Weise mit anderen Benutzern geteilt werden. Mithilfe der Funktion **Veröffentlichen** im Aufzeichnungs-Manager können Aufzeichnungen darüber hinaus an freigegebenen Speicherorten abgelegt werden.

  - OneNote bietet neue Wege der Zusammenarbeit in einer Besprechung. Während der Besprechung können sich Benutzer mit OneNote Notizen machen. Ferner besteht die Möglichkeit, freigegebene Notizbücher zu verwenden, in die auch andere Besprechungsteilnehmer ihre Notizen in Echtzeit eintragen können. Alle Teammitglieder können auf die freigegebenen Notizen zugreifen und Informationen ergänzen, eigene Ideen einbringen oder die Notizbuchseiten als virtuelles Whiteboard nutzen. Personen und freigegebene Inhalte in der Besprechung werden automatisch den Notizen hinzugefügt.

  - Mit der Funktion **Inhalt freigeben und Besprechungsaktivitäten leiten** unten im Besprechungsraum können Benutzer zwischen den einzelnen Inhaltstypen wechseln. Darüber hinaus können Benutzer im Menü **Präsentationsinhalt verwalten** die Inhalte auswählen, die sie freigeben möchten.

## Siehe auch

#### Weitere Ressourcen

[Planen von Clients in Lync Server 2013](lync-server-2013-planning-for-clients.md)

