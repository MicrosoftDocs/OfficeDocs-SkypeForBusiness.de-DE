---
title: 'Lync Server 2013: Verwenden des Webportals zur Verwaltung des Lync-Raumsystems'
TOCTitle: Verwenden des Webportals zur Verwaltung des Lync-Raumsystems
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden des Webportals zur Verwaltung des Lync-Raumsystems in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-11-10_

Nach der Bereitstellung von LRS auf dem Server können Sie den Status aller LRS-Räume überprüfen, indem Sie sich von einem Browser beim Webportal für die Verwaltung des Lync-Raumsystems anmelden.

## Anmelden

1.  Navigieren Sie zu der folgenden URL:
    
    https://\<fe-server\>/lrs

2.  Geben Sie die Anmeldeinformationen für das LRSSupport-Konto oder ein Konto ein, das der Sicherheitsgruppe "LRSSupportAdminGroup" hinzugefügt wurde.

![Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm für das Webportal zur Verwaltung des Lync-Raumsystems")

## Übersichtsseite für das Verwaltungsportal des Lync-Raumsystems

Die Übersichtsseite stellt die folgenden Informationen für alle LRS-Räume bereit, die auf dem Server bereitgestellt werden:

  - **Tag**   Der benutzerdefinierte Name, den der Administrator an den Raum vergibt. Das Tag kann im Portal festgelegt werden, indem Sie auf den Raumnamen klicken.

  - **Integrität**   Der Integritätsstatus des Raums, der vom aggregierten Integritätsstatus des Raums abgeleitet und unter dem Abschnitt für die Integrität der Seite mit den Raumeinstellungen angezeigt wird.

  - **Nächste Besprechung**   Das Datum und die Uhrzeit, zu denen die nächste Besprechung geplant ist.

  - **LRS-Version, Hersteller, Modell**   Diese Werte sind in LRS voreingestellt. Je nach Hersteller können diese Felder auch leer sein.

  - **Letzte Aktualisierung**   Zeigt die letzte Zeit an, zu der die Webseite aktualisiert wurde.

![Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Zusammenfassungsansicht für das Webportal zur Verwaltung des Lync-Raumsystems")

## LRS-Rauminformationen

Im Abschnitt zu den Rauminformationen des Portals können Sie individuelle LRS-Räume anzeigen und konfigurieren. Hier finden Sie vier Abschnitte zu Einstellungen, Details, Protokollierung und Integrität.

## Einstellungen

Im Abschnitt zu den Einstellungen können Sie das Kennwort, das Tag für den Raum und die Standardlautstärke für den Raum festlegen. Wenn Sie diese Einstellungen konfigurieren, werden die Änderungen erst repliziert, nachdem Sie die LRS-Konsole neu gestartet haben.

![Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Einstellungen für das Webportal zur Verwaltung des Lync-Raumsystems")

## Beschreibung

Im Abschnitt zu den Details wird eine schreibgeschützte Zusammenfassung zu den Einstellungen des LRS-Raums bereitgestellt, darunter die Zeit der letzten Aktualisierung, letzte Updates, Wartung und Kalibrierung, Standardeinstellungen für Lautsprecher, Mikrofon und Rufton, Version, SIP-URI, Anzahl der Bildschirme und Details zu jedem Bildschirm, Status und Aktivität.

![Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Detailansicht für das Webportal zur Verwaltung des Lync-Raumsystems")

## Protokollierung

Im Abschnitt zur Protokollierung können Sie remote Protokolle erfassen und sie an einem angegebenen Standort speichern. Sie können außerdem die LRS-Konsole (LRS-Benutzeroberfläche) oder das gesamte System neu starten.

![Protokollierung für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Protokollierung für das Webportal zur Verwaltung des Lync-Raumsystems")

## Integrität

Der Abschnitt zur Integrität stellt eine visuelle Anzeige der Integrität der Lync Server-Verbindung, des Audiogeräts, des Videogeräts, des Resilienzstatus und des Bildschirmgeräts bereit.

![Integrität für das Webportal zur Verwaltung des Lync-Raumsystems](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integrität für das Webportal zur Verwaltung des Lync-Raumsystems")

## Weitere Hinweise zum Webportal für die Verwaltung


> [!NOTE]
> <UL>
> <LI>
> <P>Aus Sicherheitsgründen werden Sie im Webportal für die Verwaltung automatisch alle 15 Minuten abgemeldet.</P>
> <LI>
> <P>Änderungen an Einstellungen werden erst angewendet, wenn das LRS-System neu gestartet wurde.</P>
> <LI>
> <P>Benachrichtigungen an das Webportal für die LRS-Verwaltung bleiben erhalten, d. h. sie werden nicht entfernt.</P>
> <LI>
> <P>Benachrichtigungen werden erst angezeigt, nachdem Sie die Seite aktualisiert haben.</P>
> <LI>
> <P>Der Status von LRS-Räumen wird angezeigt, nachdem Sie die Seite aktualisiert haben.</P>
> <LI>
> <P>Wenn das Kennwort für das LRSApp-Konto abläuft, können Sie den Status der Räume nicht sehen. Konfigurieren Sie das LRSAppuser-Kontokennwort so, dass es niemals abläuft, oder stellen Sie sicher, dass Sie das Kennwort kurz vor dem Ablaufzeitpunkt aktualisieren.</P>
> <LI>
> <P>Das Webportal für die LRS-Verwaltung wird nur für lokale Bereitstellungen unterstützt.</P></LI></UL>



## Problembehandlung

## Warum kann ich mich nicht beim Webportal für die Verwaltung anmelden?

  - Wenn Sie https://localhost/lrs öffnen, können Sie die Anmeldeseite sehen, aber wenn Sie Ihre Anmeldeinformationen eingeben, ist keine Anmeldung möglich. In diesem Fall müssen Sie https://FQDNofFEserver/lrs öffnen, um sich beim Webportal für die Verwaltung anzumelden.

  - Wenn sich der Computer, von dem Sie auf das Webportal für die Verwaltung zugreifen, in einer Arbeitsgruppe befindet, funktioniert "http://" nicht. Verwenden Sie stattdessen "https".

## Warum kann ich LRS im Webportal für die Verwaltung nicht sehen?

  - Stellen Sie sicher, dass Sie LRS-Konten in Ihrer Bereitstellung haben und diese nach den Empfehlungen für die Bereitstellung des Webportals für die LRS-Verwaltung erstellt werden. Stellen Sie sicher, dass die LRS-Konten über "Enable-CsMeetingRoom", nicht über "Enable-CsUser" auf dem Lync-Server bereitgestellt werden.

  - Wenn Sie LRS-Konten erstellt haben und die Konten im Webportal für die Verwaltung nicht sehen können, erfassen Sie die Serverprotokolle mit dem Lync Server-Protokollierungstool mit ausgewählter Komponente **MeetingPortal** und senden Sie diese dann an Ihren LRS-Supportkontakt.

## Warum kann ich den Status von LRS im Webportal für die Verwaltung nicht sehen?

  - Stellen Sie sicher, dass für das LRSApp-Benutzerkonto SIP aktiviert ist.

  - Wenn Sie weiterhin Probleme haben, erfassen Sie die Datei **Trace.log** im LRS-System von D:\\Tracing\\LRSAdminLogs\\ und senden Sie diese an Ihren LRS-Supportkontakt.

