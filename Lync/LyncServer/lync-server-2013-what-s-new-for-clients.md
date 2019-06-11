---
title: 'Lync Server 2013: Neue Funktionen für Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Neue Funktionen für Clients in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

Microsoft lync 2013 verfügt über eine neu gestaltete Benutzeroberfläche und wichtige neue Features. Für Administratoren ist der Client jetzt im Office-Setupprogramm enthalten und bietet einen optimierten Ansatz zum Bereitstellen von Office und zum Anpassen von Clients in Ihrer Organisation.

<div>


> [!NOTE]  
> Eine illustrierte Ansicht der Benutzeroberflächen Updates für lync 2013 finden Sie unter "Neuerungen in lync 2013" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integration in Office-Setup

Der lync 2013-Client und das Online Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung innerhalb des Outlook-Messaging-und-Zusammenarbeits-Clients unterstützt, sind jetzt im Office 2013-Setup Programm enthalten.

In früheren Versionen von lync und Office Communicator könnten Sie die Windows Installer-Eigenschaften verwenden, um die Office-Installation anzupassen und zu steuern. Da lync 2013 in das Office-Setup integriert ist, können Sie die folgenden Methoden zum Anpassen von lync 2013-Setup verwenden:

  - Verwenden des Office-Anpassungstools

  - Verwenden von "config. xml" zum Ausführen von Installationsaufgaben

  - Verwenden von Setup-Befehlszeilenoptionen

<div>


> [!NOTE]  
> Das lync 2013-Setupprogramm deinstalliert keine früheren Versionen von lync oder Office Communicator. Der lync 2013-Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert



</div>

Ausführliche Informationen finden Sie unter [Bereitstellen von lync-Clients in lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Bereitstellung von Gruppenrichtlinien

Da lync 2013 jetzt in Office-Setup enthalten ist, hat sich die Methode zum Bereitstellen von lync-Gruppenrichtlinieneinstellungen geändert. In früheren Versionen von lync und Office Communicator könnten Sie die Gruppenrichtlinieneinstellungen mithilfe von Communicator. adm definieren, während Sie in lync 2013 nun die administrativen Vorlagen für lync und ADML verwenden können, die zusammen mit der Office-Gruppenrichtlinie bereitgestellt werden. Administrative Vorlagen.

Ausführliche Informationen finden Sie unter [Gruppenrichtlinieneinstellungen für lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Outlook-Scheduling-Add-in-Updates

Das Online Besprechungs-Add-in für lync 2013 umfasst Besprechungs Einladungs Anpassungen und neue Besprechungsoptionen.

  - Administratoren können die Besprechungseinladungen der Organisation anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL für eine rechtliche Verzichtserklärung oder einen benutzerdefinierten Fußzeilentext hinzufügen. Ausführliche Informationen finden Sie unter [Anpassen des Online Besprechungs-Add-Ins in lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Mit den Steuerelementen für neue Teilnehmer-stumm Schaltungen können Besprechungsorganisatoren Konferenzen planen, für die Teilnehmer-Audio und-Videostandard mäßig stumm geschaltet sind.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in für virtuelle Desktop Infrastruktur

Der lync 2013-Client unterstützt jetzt Audio und Video in einer VDI-Umgebung (Virtual Desktop Infrastructure). Ein Benutzer kann ein Audio-oder Videogerät (beispielsweise ein Headset oder eine Kamera) an den lokalen Computer (beispielsweise einen Thin-Client oder einen neu gezielten Computer) anschließen. Der Benutzer kann eine Verbindung mit dem virtuellen Computer herstellen, sich beim lync 2013-Client anmelden, der auf dem virtuellen Computer ausgeführt wird, und an Echtzeit-Audio-und Videokommunikation teilnehmen, als ob der Client lokal ausgeführt wird. Die folgenden Features werden in einer virtuellen Desktopumgebung unterstützt:

  - Geräteintegration für Audio und Video, einschließlich der folgenden:
    
      - Anrufsteuerungen vom Gerät aus
    
      - Anwesenheitsintegration auf dem Gerät
    
      - Mehrere HID-Unterstützung (Human Interface Device)

  - Support für Standort und Notfalldienste.

  - Unterstützung für alle lync-Modalitäten, einschließlich Chat, Audio, Video, Anwendungsfreigabe, Desktopfreigabe, PowerPoint-Freigabe, Whiteboard und Dateiübertragung.

  - Unterstützung für Audio-und Videoanrufe in persönlichen anrufen und Konferenzgesprächen.

Informationen zum Bereitstellen des VDI-Plug-Ins finden Sie unter [Bereitstellen des lync-VDI-Plug-ins in lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Video Verbesserungen

Mehrere neue Features verbessern die Videoqualität für Konferenzteilnehmer erheblich.

  - Das Video wird durch die Flächen Erkennung und das intelligente Framing verbessert, sodass das Video eines Teilnehmers verschoben wird, damit es im Rahmen zentriert bleibt.

  - HD-Video wird jetzt in zweier-und mehr Parteien-Konferenzen unterstützt. Benutzer können Auflösungen bis zu HD 1080p erleben.

  - Teilnehmer können aus verschiedenen Besprechungs Layouts auswählen: in der Katalogansicht werden die Bilder oder Videos aller Teilnehmer angezeigt. Sprecher Ansicht zeigt den Besprechungsinhalt und nur das Video oder Bild des aktuellen Sprechers an; Die Präsentationsansicht zeigt nur den Besprechungsinhalt an. In der Kompaktansicht werden nur die Besprechungs Steuerelemente angezeigt.

  - Mit dem neuen Katalog Feature können Teilnehmer gleichzeitig mehrere Video-Feeds sehen. Wenn die Konferenz mehr als fünf Teilnehmer umfasst, werden in der obersten Zeile Video Feeds von nur den aktivsten Teilnehmern angezeigt, und Bilder werden für die anderen Teilnehmer angezeigt.

  - Teilnehmer können die Video Fixierung verwenden, um eine oder mehrere der verfügbaren Video Feeds auszuwählen, damit Sie jederzeit sichtbar sind.

  - Referenten können die Video-Spotlight-Funktion verwenden, um den Videofeed einer Person auszuwählen, damit jeder Teilnehmer an der Besprechung diesen Teilnehmer nur sieht.

</div>

<div>

## <a name="chat-room-integration"></a>Chatroom-Integration

Lync 2013 integriert nun die Features, die zuvor vom lync 2010-Gruppen-Chat bereitgestellt wurden. Ein separater Gruppen-Chat-Client ist nicht mehr erforderlich.

  - In lync 2013 können Benutzer nach Chatrooms suchen, Chatrooms zu Ihren Kontakten hinzufügen, Chatroom-Aktivitäten überwachen sowie Nachrichten lesen und senden.

  - Benutzer können Themen Feeds erstellen, damit Sie benachrichtigt werden, wenn jemand in einem Chatroom einen Beitrag hinzufügt, der bestimmte Stichwörter enthält.

  - Auf der Seite neue Optionen für beständigen **Chat** können Benutzer Benachrichtigungs Benachrichtigungen und Sounds festlegen, die gelten, wenn Personen Nachrichten in ihren Chatrooms Posten.

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App-Updates

Lync Web App ist der webbasierte Konferenz Client für lync Server 2013-Besprechungen. In dieser Version bietet das Hinzufügen von Computer-Audio und-Video zu lync Web App eine vollständige Besprechungs Erfahrung für jeden, der keinen lync-Client lokal installiert hat. Besprechungsteilnehmer können auf alle Funktionen für die Zusammenarbeit und Freigabe sowie auf alle Besprechungssteuerelemente für Referenten zugreifen.

Wenn ein Benutzer versucht, an einer Besprechung teilzunehmen, aber keinen lokal installierten Client hat, wird lync Web App geöffnet. Wenn Sie weitere Optionen für die Teilnahme an der Besprechung zulassen möchten, können Sie die Seite "Besprechungsteilnahme" konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren der Besprechungsteilnahme Seite in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in der Bereitstellungsdokumentation.

Aufgrund der Verbesserungen bei lync Web App ist eine aktualisierte Version von Attendee für lync Server 2013 nicht verfügbar. Lync Web App ist der bevorzugte Client für Teilnehmer außerhalb Ihrer Organisation. Es ist keine lokale Clientinstallation erforderlich, auch wenn für Audio-, Video-und Freigabefunktionen ein Plug-in bei der ersten Verwendung installiert werden muss.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Updates für lync 2013 für mobile Clients

Neben erweiterten Anwesenheits-, Kontakt-und Chatfunktionen bieten lync 2013 Mobile-Clients jetzt sprach-und Videoanrufe über das Internet und Mobilfunk-Datenverbindungen. Mit einem einzigen Antippen des besprechungslinks in einem Kalenderelement können mobile Benutzer an lync-sprach-und Videobesprechungen teilnehmen. Weitere Informationen zu mobilen lync 2013-Clients finden Sie unter [Planen mobiler Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013-Benutzeroberflächen Updates

<div>

## <a name="accessibility-updates"></a>Updates für Barrierefreiheit

Lync 2013 umfasst mehrere neue Barrierefreiheitsfeatures.

  - Lync 2013 unterstützt eine Auflösung mit einem höheren dpi-Wert, sodass Benutzer Text und Grafiken für 125% und 150% Punkte pro Zoll skalieren können.

  - Lync bietet Unterstützung für hohen Kontrast, damit die Benutzeroberfläche bei Verwendung mit Designs mit hohem Kontrast in Windows voll funktionsfähig bleibt.

  - Lync bietet mehr als 100 Tastenkombinationen, damit Benutzer ohne Maus auf wichtige Funktionen zugreifen können. Beispielsweise können Benutzer ALT + C drücken, um einen Anruf anzunehmen, oder ALT + I, um ihn zu ignorieren, ohne die Tab-Taste oder den Fokus setzen zu müssen. Durch Drücken von (alt + Q) wird ein Anruf beendet (STRG + N) startet OneNote, und (Alt + T) öffnet das Menü Extras.

  - Die umfassende Unterstützung für die Sprachausgabe in lync 2013 stellt sicher, dass alle Benachrichtigungen, eingehenden Anfragen und Sofortnachrichten laut vorgelesen werden, wenn eine Sprachausgabe aktiviert ist.

</div>

<div>

## <a name="presence-while-sharing"></a>Anwesenheit während der Freigabe

Wenn lync erkennt, dass ein Benutzer freigegeben wird, weist lync dem Benutzer automatisch einen Präsentations Anwesenheitsstatus zu. Dieser Status blockiert alle eingehenden Kommunikationen, es sei denn, dem Absender wird die private Beziehung Arbeitsgruppe zugeordnet. Wenn der Benutzer die Freigabefunktion vollständig auf einem sekundären Monitor verwendet, weist lync keinen Präsentations Anwesenheitsstatus zu.

</div>

<div>

## <a name="conversation-window-updates"></a>Updates für Unterhaltungsfenster

Das neu gestaltete Unterhaltungsfenster bietet schnelleren Zugriff auf wichtige Funktionen.

  - Mit dem neuen Feature "Tabbed-Konversationen" können Benutzer nun alle Ihre Chat-und Chatrooms in einem Unterhaltungsfenster aufbewahren. Über die Registerkarten auf der linken Seite des Unterhaltungsfensters können Benutzer einfach zwischen allen aktiven Konversationen navigieren.

  - Benutzer können eine einzelne Konversation in einem separaten Fenster öffnen und dann die Größe des Fensters ändern. Sie können das Fenster auch wieder in das Haupt Unterhaltungsfenster einbringen.

  - Lync 2013 öffnet die Unterhaltungen eines Benutzers erneut, wenn sich der Benutzer anmeldet und sich wieder bei lync anmeldet.

  - Benutzer können jeder Unterhaltung Schnellchat-, Video-, Programmfreigabe-, Desktopfreigabe-oder Webkonferenz Tools (Whiteboard, Besprechungsnotizen, freigegebene Notizbücher und Anlagen) hinzufügen.

  - In einer Besprechung, in der Videos oder Inhalte freigegeben werden, können Benutzer das Besprechungs Video oder freigegebene Inhalte herausspringen und dann die Größe des Fensters ändern.

</div>

<div>

## <a name="lync-main-window-updates"></a>Updates für das Hauptfenster von lync

Das neue optimierte aussehen behält vertraute Funktionen wie das aktuelle Feature " **What es Happening Today?** ", die Statusauswahl und die **Einstellung "Standort** Auswahl" bei.

  - Wenn Chatrooms aktiviert sind, wird den Benutzern auf **** der lync-Hauptseite ein neues Symbol für Chatrooms angezeigt. Mit dem **** Symbol Chatrooms können Benutzer schnell auf Ihre Chatrooms und Filter zugreifen.

  - Benutzer können auf die Ansichtssymbole klicken, um zur Ansicht **Kontakte** , **chatroomansicht** , **Konversations** Ansicht oder **Telefon** Ansicht zu wechseln.

  - Wenn Benutzer zu Exchange 2013 migriert wurden, können Sie ein Bild mit höherer Auflösung hochladen.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Kontakte anzeigen und Visitenkarten Updates

Lync 2013 bietet Benutzern unterschiedliche Möglichkeiten zum Anzeigen von Kontakten und Gruppen in der Ansicht " **Kontakte** ".

  - Mit dem neuen Unified Contact Store können die Benutzer nach dem Migrieren der lync-Kontakte von Benutzern zu Exchange 2013 auf Ihre Kontakte aus lync 2013, Outlook oder Outlook Web App zugreifen und diese verwalten, und Ihre Favoriten bleiben synchronisiert. Wenn ein Benutzer beispielsweise einen Kontakt zu den Favoriten in Outlook hinzufügt, wird der Kontakt in der Gruppe Favoriten in lync 2013 angezeigt.

  - Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzugefügt und konfiguriert haben, können Benutzer Kontakte von XMPP-basierten Partnern für Sofortnachrichten und Anwesenheitsinformationen hinzufügen.

  - Ein neuer **Kontakt hinzufügen, der nicht in meiner Organisation enthalten ist** , bietet Benutzern eine einfache Möglichkeit zum Hinzufügen von Personen, die sich außerhalb der Organisation befinden.

  - Eine neue Gruppe " **Favoriten** " ermöglicht Benutzern das Erstellen einer Liste von Personen, die Benutzer am häufigsten kontaktieren, um schnelleren Zugriff zu erhalten.

  - Benutzer können die Seite neue **Kontaktlisten** Optionen verwenden, um auszuwählen, wie Benutzer Kontakte sortieren und anzeigen möchten. Benutzer können eine erweiterte, zweizeilige Ansicht auswählen, in der die Bilder von Kontakten angezeigt werden, oder eine verkürzte einzeilige Ansicht. Benutzer können Kontakte auch alphabetisch oder nach Verfügbarkeit sortieren.

</div>

<div>

## <a name="conferencing-updates"></a>Konferenz Updates

Lync 2013 bietet mehrere Verbesserungen für Konferenzfeatures.

  - Je nach Art der Besprechung können Benutzer die Zielgruppe jetzt stumm schalten und die Videofreigabe beim Planen der Besprechung zulassen oder blockieren. Diese Optionen sind auf der Seite " **Besprechungsoptionen** " verfügbar und werden für größere Besprechungen mit mehr als 20 Teilnehmern empfohlen.

  - Einfach zu verwendende Audiosteuerungen im Besprechungsraum ermöglichen dem Benutzer die Steuerung von Audiooptionen, wie Stummschaltung, Stummschaltung, Gerätewechsel usw.

  - Beim Freigeben von Programmen können Benutzer mehrere Programme auswählen, die Sie freigeben möchten, wenn Sie mit mehr als einem Programm arbeiten müssen.

  - Benutzer können jetzt Präsentationen mit Videoclips hochladen, indem Sie die PowerPoint-Datei hochladen und mit der Maus auf die Folie zeigen, um Videosteuerelemente wie Wiedergabe-, Pause-und Audiosteuerungen anzuzeigen.

  - Während einer Besprechung können Benutzer eine andere offene Unterhaltung mit der Besprechung zusammenführen, indem Sie im Menü **Weitere Optionen** (**.**..) die Option **diesen Anruf zusammenführen** verwenden.

  - Um die Namen der Teilnehmer anzuzeigen, können Benutzer mit der Maus auf die Schaltfläche **Teilnehmer anzeigen** zeigen oder auf **Teilnehmerliste anzeigen** klicken, um das Panel in der Besprechung anzudocken.

  - Je nach Besprechungstyp können Benutzer aus verschiedenen Inhalts-und Teilnehmer Ansichten auswählen.

  - Besprechungsaufzeichnungen werden automatisch in einem Format gespeichert, das in Windows Media Player (MP4) wiedergegeben wird. Benutzer können die Datei ganz einfach für beliebige Personen freigeben oder mithilfe der Funktion " **veröffentlichen** " im Aufzeichnungs-Manager die Aufzeichnung an einem freigegebenen Speicherort Posten.

  - OneNote ermöglicht neue Möglichkeiten für die Zusammenarbeit an einer Besprechung. Während einer Besprechung können Benutzer Notizen mit OneNote für die persönliche Verwendung nach der Besprechung erstellen oder freigegebene Notizbücher und die gemeinsame Bearbeitung mit Besprechungsteilnehmern in Echtzeit verwenden. Alle Teammitglieder können auf die freigegebenen Notizen zugreifen, um Informationen beizusteuern, Ideen zu Brainstorming oder die Notizbuchseiten als virtuelles Whiteboard zu verwenden. In der Besprechung freigegebene Personen und Inhalte werden den Notizen automatisch hinzugefügt.

  - Benutzer können mithilfe von " **Inhalte freigeben" und "Besprechungs Aktivitäten leiten** " am unteren Rand des Besprechungsraums zwischen Inhaltstypen wechseln. Benutzer können auch das Menü **Präsentationsinhalte verwalten** verwenden, um auszuwählen, welche Inhalte freigegeben werden sollen.

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

