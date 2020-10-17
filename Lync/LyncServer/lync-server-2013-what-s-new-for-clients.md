---
title: 'Lync Server 2013: Neuerungen für Clients'
description: 'Lync Server 2013: What es New for Clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90c1b93666b556c7ce7c4f3d94bea583dbf9b1a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546131"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a>Neuerungen für Clients in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-19_

Microsoft lync 2013 verfügt über eine neu gestaltete Benutzeroberfläche und wichtige neue Features. Für Administratoren ist der Client jetzt im Office-Setupprogramm enthalten und bietet einen optimierten Ansatz für die Bereitstellung von Office und das Anpassen von Clients in Ihrer Organisation.

<div>


> [!NOTE]  
> Eine illustrierte Ansicht der lync 2013 Updates der Benutzeroberfläche finden Sie unter "What es New in lync 2013" unter <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> .



</div>

<div>

## <a name="integration-with-office-setup"></a>Integration in das Setup von Office

Der lync 2013-Client und das Online-Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung über den Outlook-Client für Messaging und Zusammenarbeit unterstützt, sind jetzt sowohl im Office 2013-Setup Programm enthalten.

In früheren Versionen von lync und Office Communicator konnten Sie die Windows Installer-Eigenschaften verwenden, um die Office-Installation anzupassen und zu steuern. Da lync 2013 in Office Setup integriert ist, können Sie die folgenden Methoden zum Anpassen lync 2013 Setups verwenden:

  - Verwenden des Office-Anpassungstools

  - Verwenden der Datei "config.xml" zur Durchführung von Installationsaufgaben

  - Verwenden der Befehlszeilenoptionen für das Setup

<div>


> [!NOTE]  
> Mit dem Setupprogramm für lync 2013 werden frühere Versionen von lync oder Office Communicator nicht deinstalliert. Der lync 2013 Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert.



</div>

Ausführliche Informationen finden Sie unter [Deploying lync Clients in lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Bereitstellung von Gruppenrichtlinien

Da lync 2013 jetzt in Office Setup enthalten ist, wurde die Methode zum Bereitstellen von lync-Gruppenrichtlinieneinstellungen geändert. In früheren Versionen von lync und Office Communicator konnten Sie die Communicator. adm zum Definieren von Gruppenrichtlinieneinstellungen verwenden, während Sie in lync 2013 jetzt die administrativen Vorlagen für lync ADMX und ADML verwenden können, die zusammen mit den administrativen Vorlagen für Office-Gruppenrichtlinien bereitgestellt werden.

Ausführliche Informationen finden Sie unter [Gruppenrichtlinieneinstellungen für lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Updates für das Planungs-Add-In von Outlook

Das Online-Besprechungs-Add-in für lync 2013 umfasst die Anpassung von Besprechungseinladungen und neue Besprechungsoptionen.

  - Administratoren können die Besprechungseinladungen ihrer Organisation durch Hinzufügen eines Logos, einer Support-URL, einer URL für den rechtlichen Haftungsausschluss oder eines benutzerdefinierten Fußzeilentexts anpassen. Ausführliche Informationen finden Sie unter [Anpassen des Online Besprechungs-Add-Ins in lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Neue Teilnehmersteuerelemente ermöglichen Besprechungsorganisatoren das Planen von Konferenzen, in denen die Audio- und Videofunktionen von Teilnehmern standardmäßig stummgeschaltet sind.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Virtual Desktop Infrastructure-Plug-In

Der lync 2013-Client unterstützt jetzt Audio und Video in einer VDI-Umgebung (Virtual Desktop Infrastructure). Ein Benutzer kann ein Audio- oder Videogerät (z. B. ein Headset oder eine Kamera) mit dem lokalen Computer verbinden (z. B. einem Thin-Client oder einem Computer mit neuem Zweck). Der Benutzer kann eine Verbindung mit dem virtuellen Computer herstellen, sich beim lync 2013 Client anmelden, der auf dem virtuellen Computer aktiv ist, und an der Echtzeitübertragung von Audio und Video teilnehmen, als ob der Client lokal betrieben wird. Die folgenden Features werden in einer virtuellen Desktopumgebung unterstützt:

  - Geräteintegration für Audio- und Videofunktionen, einschließlich der folgenden:
    
      - Anrufsteuerung mit dem Gerät
    
      - Anwesenheitsintegration auf dem Gerät
    
      - Unterstützung mehrerer HIDs (Human Interface Device, Eingabegeräte)

  - Unterstützung von Standort- und Notrufdiensten

  - Unterstützung für alle lync-Modalitäten, einschließlich Chat, Audio, Video, Anwendungsfreigabe, Desktopfreigabe, PowerPoint-Freigabe, Whiteboard und Dateiübertragung.

  - Audio- und Videounterstützung bei Einzel- und Konferenzanrufen

Informationen zum Bereitstellen des VDI-Plug-Ins finden Sie unter [Deploying the lync VDI Plug-in in lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Videoerweiterungen

Die Videoerfahrung für Konferenzteilnehmer wurde durch die Einführung neuer Funktionen signifikant verbessert.

  - Dank Gesichtserkennung und des intelligenten Framings kann sich das Videofenster des Teilnehmers an Bewegungen anpassen, und der Benutzer bleibt im Mittelpunkt.

  - High-Definition-Videos werden jetzt in Anrufen mit zwei Teilnehmern und in Konferenzen mit mehreren Teilnehmern mit einer Auflösung bis HD 1080P unterstützt.

  - Teilnehmer können auch unterschiedlichen Besprechungslayouts auswählen: Galerienansicht (zeigt Bilder oder Videos aller Teilnehmer an), Sprecheransicht (zeigt den Besprechungsinhalt und nur das Bild oder Video des aktuellen Sprechers an), Präsentationsansicht (zeigt nur den Besprechungsinhalt an), Kompaktansicht (zeigt nur die Besprechungssteuerelemente an).

  - In der neuen Galerieansicht können Benutzer mehrere Videofeeds gleichzeitig anzeigen. Bei Konferenzen mit mehr als fünf Teilnehmern, werden nur die Videofeeds der aktivsten Teilnehmer in der obersten Zeile angezeigt, die anderen Teilnehmer werden jeweils mit einem Bild angezeigt.

  - Teilnehmer können Videos auch verankern, sodass einer oder mehrere Videofeeds die ganze Zeit über angezeigt werden.

  - Referenten können mithilfe einer Spotlightfunktion den Videofeed einer bestimmten Version auswählen, sodass alle Teilnehmer in der Besprechung nur diesen Teilnehmer sehen.

</div>

<div>

## <a name="chat-room-integration"></a>Chatroomintegration

Lync 2013 integriert nun die Funktionen, die zuvor von lync 2010 Gruppen Chat bereitgestellt wurden. Ein separater Client für Gruppenchats ist nicht mehr erforderlich.

  - In lync 2013 können Benutzer nach Chatrooms suchen, Ihren Kontakten Chatrooms hinzufügen, Chatroom-Aktivitäten überwachen sowie Nachrichten lesen und veröffentlichen.

  - Benutzer können Themenfeeds erstellen, um benachrichtigt zu werden, wenn in einem ihrer Chatrooms ein Beitrag mit bestimmten Stichwörtern veröffentlicht wird.

  - Die neue Seite mit Optionen für den **Beständigen Chat** ermöglicht Benutzern das Festlegen von Benachrichtigungen und akustischen Signalen, wenn andere Benutzer Nachrichten in ihren Chatrooms veröffentlichen.

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App Updates

Lync Web App ist der webbasierte Konferenz Client für lync Server 2013-Besprechungen. In dieser Version bietet das Hinzufügen von Computer-Audio-und-Video zu lync Web App eine umfassende Besprechungs Erfahrung für alle Benutzer, die keinen lync-Client lokal installiert haben. Besprechungsteilnehmer können auf alle Funktionen für die Zusammenarbeit und Freigabe sowie auf alle Besprechungssteuerelemente des Referenten zugreifen.

Wenn ein Benutzer versucht, einer Besprechung beizutreten, jedoch keinen lokal installierten Client hat, wird lync Web App geöffnet. Wenn Sie zusätzliche Optionen für die Teilnahme an der Besprechung zulassen möchten, können Sie die Seite für den besprechungsbeitritt konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.

Aufgrund der Verbesserungen an lync Web App ist eine aktualisierte Version von Attendee für lync Server 2013 nicht verfügbar. Lync Web App ist der bevorzugte Client für Teilnehmer außerhalb Ihrer Organisation. Es ist keine lokale Clientinstallation erforderlich, auch wenn für Audio-, Video-und Freigabefunktionen ein Plug-in bei der ersten Verwendung installiert werden muss.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 für Updates für mobile Clients

Neben erweiterten Anwesenheitsinformationen, Kontakten und Chatfunktionen bieten lync 2013 Mobile Clients jetzt sprach-und Videoanrufe über das Internet und Mobilfunkdaten Verbindungen an. Mit einem einzigen Klick auf den Besprechungslink in einem Kalenderelement können mobile Benutzer an lync-sprach-und-Videobesprechungen teilnehmen. Weitere Informationen zu lync 2013 mobilen Clients finden Sie unter [Planning for Mobile Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013 Updates der Benutzeroberfläche

<div>

## <a name="accessibility-updates"></a>Updates für die Eingabehilfen

Lync 2013 enthält mehrere neue Barrierefreiheitsfunktionen.

  - Lync 2013 unterstützt eine hohe dpi-Auflösung, sodass Benutzer Text und Grafiken für 125% und 150% dots per inch skalieren können.

  - Lync bietet Unterstützung mit hohem Kontrast, sodass die Benutzeroberfläche bei Verwendung von Designs mit hohem Kontrast in Windows voll funktionsfähig bleibt.

  - Lync bietet mehr als 100 Tastenkombinationen, damit Benutzer ohne Maus auf wichtige Funktionen zugreifen können. Beispielsweise kann ein Anruf durch Drücken der ALT-TASTE+C angenommen werden, und mit ALT-TASTE+I können Anrufe ignoriert werden, dabei ist es nicht erforderlich die TAB-TASTE zu betätigen oder den Fokus zu ändern. Mit der ALT-TASTE+Q wird ein Anruf beendet, mit der STRG-TASTE+N wird OneNote gestartet, und die ALT-TASTE+T öffnet das Menü "Extras".

  - Umfangreiche Sprachausgabe Unterstützung in lync 2013 stellt sicher, dass alle Benachrichtigungen, eingehenden Anforderungen und Chatnachrichten laut gelesen werden, wenn eine Sprachausgabe aktiviert ist.

</div>

<div>

## <a name="presence-while-sharing"></a>Anwesenheit bei Freigabe

Wenn lync erkennt, dass ein Benutzer freigegeben wird, weist lync dem Benutzer automatisch einen Präsentations Anwesenheitsstatus zu. Dieser Status blockiert die gesamte eingehende Kommunikation, es sei denn, dem Absender wird der Status "Beschäftigt" zugewiesen. Wenn der Benutzer das Freigabefeature vollständig auf einem sekundären Monitor verwendet, weist lync keinen Präsentations Anwesenheitsstatus zu.

</div>

<div>

## <a name="conversation-window-updates"></a>Updates für das Fenster "Unterhaltung"

Das neu gestaltete Fenster "Unterhaltung" bietet jetzt noch schnelleren Zugriff auf wichtige Funktionen.

  - Dank der neuen Unterhaltungsfunktion mit Registerkarten können Benutzer jetzt alle Sofortnachrichten und Chatrooms in einem Unterhaltungsfenster nutzen. Die Registerkarten werden an der linken Seite des Fensters "Unterhaltung" angezeigt und ermöglichen eine schnelle und bequeme Navigation zwischen allen aktiven Unterhaltungen.

  - Benutzer können eine individuelle Unterhaltung in ein separates Fenster ausgliedern und anschließend die Größe dieses Fensters anpassen. Das Fenster kann außerdem wieder in das Fenster "Unterhaltung" eingegliedert werden.

  - Lync 2013 öffnet die Unterhaltungen eines Benutzers erneut, wenn der Benutzer sich abmeldet und sich an lync anmeldet.

  - Benutzer können jeder Unterhaltung umgehend Sofortnachrichten, Videos, Programmfreigaben, Desktopfreigaben oder Webkonferenztools (Whiteboards, Besprechungsnotizen, Notizbuchfreigaben und Anlagen) hinzufügen.

  - In einer Besprechung, in der Videos oder Inhalte geteilt werden, können Benutzer die Videos oder Inhalte in ein separates Fenster ausgliedern und die Größe dieses Fensters anpassen.

</div>

<div>

## <a name="lync-main-window-updates"></a>Updates des lync-Hauptfensters

Der neue und modernisierte Look ermöglicht auch weiterhin den Zugriff auf bekannte Funktionen wie das Feld **Notiz eingeben**, die Statusauswahl und die Auswahl **Standort festlegen**.

  - Wenn Chatrooms aktiviert sind, wird den Benutzern auf der lync-Hauptseite ein neues Symbol für **Chatrooms** angezeigt. Über das Symbol **Chatrooms** können Benutzer rasch auf ihre Chatrooms und Filter zugreifen.

  - Durch Klicken auf die Ansichtssymbole können Benutzer zwischen der Ansicht **Kontakte**, der Ansicht **Chatrooms**, der Ansicht **Konversationen** und der Ansicht **Telefon** wechseln.

  - Wenn Benutzer zu Exchange 2013 migriert wurden, können Sie ein Bild mit hoher Auflösung hochladen.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Updates für die Ansicht "Kontakte" und die Visitenkarte

Lync 2013 bietet Benutzern unterschiedliche Möglichkeiten zum Anzeigen von Kontakten und Gruppen in der **Kontakt** Ansicht.

  - Nachdem die lync-Kontakte von Benutzern zu Exchange 2013 migriert wurden, können die Benutzer mit dem neuen einheitlichen Kontaktspeicher über lync 2013, Outlook oder Outlook Web App auf Ihre Kontakte zugreifen und diese verwalten, und Ihre Favoriten bleiben synchronisiert. Wenn ein Benutzer beispielsweise einen Kontakt zu den Favoriten in Outlook hinzufügt, wird der Kontakt in der Gruppe Favoriten in lync 2013 angezeigt.

  - Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzugefügt und konfiguriert haben, können Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten- und Präsenzfunktionen hinzufügen.

  - Mit der neuen Funktion **Kontakt außerhalb der Organisation hinzufügen** können Benutzer auf einfache Weise andere Benutzer außerhalb ihrer Organisation hinzufügen.

  - Die neue Funktion **Favoriten** ermöglicht Benutzern das Erstellen einer Liste von Personen, die am häufigsten von Benutzern kontaktiert werden, um schnell darauf zugreifen zu können.

  - Auf der neuen Optionsseite **Kontaktliste** können Benutzer angeben, wie Benutzer sortiert und angezeigt werden sollen. Zur Auswahl stehen eine erweiterte zweizeilige Ansicht mit Kontaktbildern oder eine kompakte einzeilige Ansicht. Die Liste kann alphabetisch oder nach Verfügbarkeit sortiert werden.

</div>

<div>

## <a name="conferencing-updates"></a>Updates für Konferenzen

Lync 2013 bietet mehrere Verbesserungen an den Konferenzfunktionen.

  - In Abhängigkeit vom Besprechungstyp können Benutzer jetzt das Publikum stummschalten und die Videofreigabe zulassen oder blockieren, wenn sie die Besprechung planen. Diese Optionen sind auf der Seite **Besprechungsoptionen** verfügbar und sollten bei großen Besprechungen ab 20 Personen verwendet werden.

  - Benutzerfreundliche Audiosteuerelemente im Besprechungsraum ermöglichen Benutzern das Kontrollieren der Audiooptionen wie "Stummschalten", "Stummschaltung aufheben" oder "Gerät ändern".

  - Beim Freigeben von Programmen können Benutzer bei Bedarf mehrere Programme für eine Freigabe auswählen.

  - Benutzer können jetzt Präsentationen mit Videoclips hochladen, indem Sie die entsprechende PowerPoint-Datei hochladen und mit der Maus auf die Folie zeigen, um die Videosteuerelemente wie Wiedergabe oder Pause und die Audiosteuerelemente anzuzeigen.

  - Benutzer können aus Besprechungen heraus eine andere geöffnete Unterhaltung mit der Besprechung zusammenführen, indem sie die Option **Diesen Anruf zusammenführen mit** im Menü **Weitere Optionen** (**…**) verwenden.

  - Benutzer können mit der Maus auf die Schaltfläche **Teilnehmer anzeigen** zeigen, um die Namen der Teilnehmer anzuzeigen. Benutzer können auch auf **Teilnehmerliste anzeigen** klicken, um den Bereich in der Besprechung zu verankern.

  - In Abhängigkeit vom Besprechungstyp können Benutzer aus mehreren Inhalts- und Teilnehmeransichten auswählen.

  - Besprechungen werden automatisch in einem Format aufgezeichnet, das im Windows Media Player wiedergegeben werden kann (MP4). Aufgezeichnete Dateien können auf einfache Weise mit anderen Benutzern geteilt werden. Mithilfe der Funktion **Veröffentlichen** im Aufzeichnungs-Manager können Aufzeichnungen darüber hinaus an freigegebenen Speicherorten abgelegt werden.

  - OneNote bietet neue Wege der Zusammenarbeit in einer Besprechung. Während der Besprechung können sich Benutzer mit OneNote Notizen machen. Ferner besteht die Möglichkeit, freigegebene Notizbücher zu verwenden, in die auch andere Besprechungsteilnehmer ihre Notizen in Echtzeit eintragen können. Alle Teammitglieder können auf die freigegebenen Notizen zugreifen und Informationen ergänzen, eigene Ideen einbringen oder die Notizbuchseiten als virtuelles Whiteboard nutzen. Personen und freigegebene Inhalte in der Besprechung werden automatisch den Notizen hinzugefügt.

  - Mit der Funktion **Inhalt freigeben und Besprechungsaktivitäten leiten** unten im Besprechungsraum können Benutzer zwischen den einzelnen Inhaltstypen wechseln. Darüber hinaus können Benutzer im Menü **Präsentationsinhalt verwalten** die Inhalte auswählen, die sie freigeben möchten.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Clients in lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

